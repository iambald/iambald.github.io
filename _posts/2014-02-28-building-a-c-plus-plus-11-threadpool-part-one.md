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

C++11 introduced a bunch of new libraries for parallel programming, including the task-level `std::async` and the thread-level `std::thread`. However, for whatever reason, the standard does not include a threadpool. While `std::async` may launch tasks into a threadpool, it is implementation dependent, and may do anything from running tasks sequentially to spawning a new thread for each task. On the other hand, manually managing threads using `std::thread` is tedious and error-prone. A threadpool would offer more control than `std::async`, while being easier and safer than manually managing threads.

So how would we go about designing a threadpool? First, let’s list the features it will need to have. We want the threadpool to be **dynamic**: it should spawn and despawn threads based on load. Also, the pool should be **lightweight**, so it shouldn’t have a master thread assigning tasks or have significant processing or memory overhead. Finally, it should be **configurable** - the pool should allow its parameters, such as the maximum thread count, to be changed while it is running, and automatically adjust to the changes.

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

Next time, we'll take a look at the inner workings of our threadpool. Or, if you're impatient, you can check out the completed code [here](https://github.com/iambald/threadpool).
