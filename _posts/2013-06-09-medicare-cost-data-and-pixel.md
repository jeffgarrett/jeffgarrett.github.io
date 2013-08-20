---
layout: post
title: "Medicare Cost Data and the Pixel"
date: 2013-06-09
comments: false
categories:
 - Pixel
 - ChromeOS
---
[Extensive cost data][1] for medical procedures has recently been released. I thought it might be interesting to explore it, and out of curiosity try to do so on the Pixel. Unfortunately, this highlights why ChromeOS still needs some work.

The spreadsheet cannot be uploaded to a Google Sheet, because it has more than 400 thousand cells. Oops. A second option was fusion tables, but fusion tables is [unable to geocode addresses][2] split into multiple columns. In fact, Google's [recommended solution][3] is to download and modify the file on something other than a Chromebook using Excel.

I was expecting problems with programming given the lack of editors, IDEs and build tools, but not basic spreadsheet tasks!

[1]: http://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/Outpatient.html
[2]: https://code.google.com/p/fusion-tables/issues/detail?id=86
[3]: https://support.google.com/fusiontables/answer/175922
