# setTimeout，setInterval，setImmediate，process.nextTick

亿书底层的亿书币，是一个基础层，类似于操作系统，需要持续反复运行。调度和管理各种循环是很关键的部分，在亿书币的源码里，可以看到大量`setImmediate`函数的调用，简单解决了这个问题。为什么不用其他setTimeout，setInterval，process.nextTick等函数呢？它们之间有什么区别？

## 官方文档

访问 [Node.js(官方长期支持版)官方文档][]，我们可以看到，setTimeout，setInterval，setImmediate 这三个函数属于时间（timer)函数，nextTick 属于进程（process）函数。

#### process.nextTick(callback[, arg][, ...])#
https://nodejs.org/dist/latest-v4.x/docs/api/process.html#process_process_nexttick_callback_arg

#### Timers
https://nodejs.org/dist/latest-v4.x/docs/api/timers.html

## 总结

Nodejs的特点是事件驱动，异步I/O产生的高并发，产生此特点的引擎是事件循环，事件被分门别类地归到对应的事件观察者上，比如idle观察者，定时器观察者，I/O观察者等等，事件循环每次循环称为Tick，每次Tick按照先后顺序从事件观察者中取出事件进行处理。

* setTimeout()和setInterval()都是当定时器使用，他们的区别在于后者是重复触发，而且由于时间设的过短会造成前一次触发后的处理刚完成后一次就紧接着触发。由于定时器是超时触发，这会导致触发精确度降低，比如用setTimeout设定的超时时间是5秒，当事件循环在第4秒循到了一个任务，它的执行时间3秒的话，那么setTimeout的回调函数就会过期2秒执行，这就是造成精度降低的原因。并且由于采用红黑树和迭代的方式保存定时器和判断触发，较为浪费性能。

* 使用process.nextTick()所设置的所有回调函数都会放置在数组中，会在下一次Tick时所有的都立即被执行，该操作较为轻量，时间精度高。

* setImmediate()设置的回调函数也是在下一次Tick时被调用，与process.nextTick()的区别在于两点：

  1.他们所属的观察者被执行的优先级不一样，process.nextTick()属于idle观察者,setImmediate()属于check观察者，idle的优先级>check。

  2.setImmediate()设置的回调函数是放置在一个链表中，每次Tick只执行链表中的一个回调。这是为了保证每次Tick都能快速地被执行。
