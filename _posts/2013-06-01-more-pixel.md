---
layout: post
title: "More Pixel"
date: 2013-06-01
comments: false
categories:
 - Pixel
 - ChromeOS
---
After more Pixel use, I have encountered two minor issues with easy solutions to share.

Firstly, the clock was off by two hours this morning. Since it was previously correct, and the timezone was set properly, I suspected an underlying NTP problem. But I found [this thread][1] suggesting that the timezone setting is ignored in favor of the (unset) apps domain timezone setting. After setting the domain timezone, the time was correct again.

Secondly, hiding Gmail labels by dragging them into the "More Labels" section doesn't work. I found [this thread][2] explaining that the cause is the new "Touch-enabled" inbox view, and switching back to "Comfortable" returns the familiar behavior.

[1]: https://groups.google.com/forum/#!topic/chromebook-central/Gw5d_iZtPZc
[2]: https://productforums.google.com/forum/?fromgroups#!topic/gmail/uj8lgZPWva0
