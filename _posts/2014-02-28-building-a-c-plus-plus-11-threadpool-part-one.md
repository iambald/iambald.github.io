---
layout: post
title: "Building a C++11 Threadpool, Part One: Design"
modified: 2014-02-28 20:57:07 -0500
category: [coding]
tags: [coding, c++, threadpool]
image:
  feature: 
  credit: 
  creditlink: 
comments: 
share: 
---

C++11 introduced a bunch of new libraries for parallel programming, including the task-level `std::async` and the thread-level `std::thread`. However, for whatever reason, the standard does not include a [threadpool](en.wikipedia.org/wiki/Thread_pool). While `std::async` may launch tasks into a threadpool, it is implementation dependent, and could do anything from spawning a new thread for every task to running everything sequentially. On the other hand, manually managing threads using `std::thread` is tedious and error-prone. A well-designed threadpool offers more control than `std::async`, while being easier and safer than manually managing threads.

Let’s take a look at what we want in a threadpool. Since this is C++, our first consideration should be **performance**. This means minimizing thread-level overhead (what a worker thread has to process to execute a task) as well as program-level overhead. To minimize program-level overhead, we won’t control our threadpool with a master thread, and will instead spread the control across the worker threads. Secondly, our threadpool should be **configurable**.  It should provide reasonable defaults for parameters such as the worker thread limit, and also provide methods to change them. Finally, the threadpool should be **generic**. It should be able to accept and run anything that has `operator()`, including `std::function` objects, lambdas, `std::bind` results, and functors. It should also accept optional arguments to pass to these objects, like `std::bind` does. We will achieve this by templating our `add_task()` method and binding any additional arguments to the function object with `std::forward` and `std::bind`.

Next, let's think about the public interface for the threadpool. The most important function is `add_task()`, which adds a task for the threadpool to execute. It also makes sense to have a `wait()` function, which waits for all tasks to complete. Next, we have the`join()` method, which is subtly different from `wait()` - when `join()` is called, all worker threads will be joined and destroyed, while when `wait()` is called, the worker threads will not be destroyed. Note that `join()` never has to explicitly be called - the destructor of our threadpool will join all worker threads. However, it may be useful for performance tuning. The final non-accessor methods we will expose are `pause()` and `unpause()`. `pause()` will not stop any already executing tasks. However, it will stop worker threads from executing new tasks. `unpause()` will simply allow worker threads to execute new tasks again.

Here's what our interface looks like:

{% highlight c++ linenos %}
class pool {
 public:
    pool();
    ~pool();

    add_task();
    join();
    wait();
    pause();
    unpause();
}

{% endhighlight %}

Next time, we'll take a look at the inner workings of our threadpool and create the helper class `worker_thread`. Or, if you're impatient, you can check out the completed code [here](https://github.com/iambald/threadpool).
