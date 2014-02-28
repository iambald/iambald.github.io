---
layout: page
permalink: /projects/
title: Projects
description: "Instructions on how to install and customize the Jekyll theme Minimal Mistakes."
tags: [projects]
image:
  feature: texture-feature-02.jpg
  credit: Texture Lovers
  creditlink: http://texturelovers.com
---

<section id="table-of-contents" class="toc">
  <header>
    <h3 >Contents</h3>
  </header>
<div id="drawer" markdown="1">
*  Auto generated table of contents
{:toc}
</div>
</section><!-- /#table-of-contents -->

A list of stuff I've made, in varying stages of development.

## MiniPlay

<figure>
  <a href="https://chrome.google.com/webstore/detail/miniplay/dfddfiedihbijfeacjamchlliogmjjnd" target="_blank"><img src="{{ site.url }}/images/miniplay.jpg"></a>
  <figcaption><a href="https://chrome.google.com/webstore/detail/miniplay/dfddfiedihbijfeacjamchlliogmjjnd" target="_blank" title="MiniPlay">A Chrome extension to control Google Play Music</a>.</figcaption>
</figure>

* Popup controls themed to match Play Music
* Chrome-wide keyboard shortcuts
* Last.fm scrobbling
* Rich notifications
* [Open source](https://github.com/iambald/MiniPlay)

---

## threadpool

A modern threadpool built in modern C++11 to bridge the gap between `std::async` (not enough control) and `std::thread` (too fragile).

{% highlight c++ linenos %}
  threadpool::pool();
  for (auto&& task : tasks) {
    pool.add_task(task);
  }

  pool.wait();
{% endhighlight %}

* Low overhead - no master thread
* Spawn and despawn threads based on load
* Configurable, with sane default parameters
* Supports all function objects, including lambdas
* [Open source](https://github.com/iambald/threadpool)

---

## xkcd Alma Mater Challenge

[A quick and dirty implementation](https://github.com/iambald/Skein) to brute force a Skein hash, built in a few hours. Running on a personal laptop, I hashed billions of potential strings, with the closest hash having 405 bits different than xkcd's, better than Cornell's best effort. That was good for about 150th place and only twenty bits off from the winner, a group of CMU students using a supercomputer.

---

## eva

Software for an autonomous submarine, [Barracuda](http://avbotz.com). Notable features include

* Computer vision, including image segmentation and blob detection
* Robust state system to determine order of tasks
* Path following
* PID controller and Kalman filter to integrate IMU data
* Leak detection


