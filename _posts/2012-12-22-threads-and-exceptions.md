---
layout: post
title: "Threads and Exceptions"
date: 2012-12-22
comments: false
categories:
 - Linux
 - Threads
 - C++
 - Solaris
---
I learned something recently. One should be careful with `catch(...)`. And one should be very careful with `pthread_cancel`.

The catch-all has a limited uses of course, since you usually know the types of exception to expect. However, there is the rare occasion for its use. What I learned is that you must always re-throw the caught exception. If you don't, `pthread_cancel` and `pthread_exit` may break.

The reason is that on Linux, those functions work by throwing a special exception. This exception is special and does not derive from `std::exception`. You must re-throw it. It is possible to catch this exception alone and re-throw. In order to do that, see [this post][1].

[The same logic][2] also implies that when using `pthread_cancel`, you should not use functions which serve as cancellation points in destructors. In other words, it is best not to use `pthread_cancel`.

In summary:
 * When using `catch(...)`, always re-throw.
 * Do not use `pthread_cancel`.
Note: the same does not appear to be true on Solaris.

References: [Ulrich Drepper's blog][1], [Kenneth's blog][2].

[1]: http://udrepper.livejournal.com/21541.html
[2]: http://skaark.wordpress.com/2010/08/26/pthread_cancel-considered-harmful/
