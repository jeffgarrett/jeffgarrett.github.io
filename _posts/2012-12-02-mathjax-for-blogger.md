---
layout: post
title: "MathJax for Blogger"
date: 2012-12-02
comments: false
categories:
 - MathJax
 - GoogleBlogger
 - LaTeX
---
For basic MathJax support in Blogger, all you have to do is edit the HTML of your template and put the following before `</head>`:

```html
<script type='text/x-mathjax-config'>
MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']],
                     displayMath: [['\\[','\\]'], ['$$','$$']]}});
</script>
<script src='http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML' type='text/javascript'>
</script>
```

This is all you have to do if you aren't using Blogger's dynamic views. The principal issue with this method is that RSS readers do not render the LaTeX. This was the justification for <a href="https://github.com/jeffgarrett/browser-extensions">the LaTeX for Blogger user script</a>. But MathJax looks _so_ much better on a retina screen!

It is possible to have the best of both worlds, and maybe one day I'll blog how...

$$\int_0^1 x^2 dx = \frac{1}{3}$$

Source: <a href="http://checkmyworking.com/2012/01/how-to-get-beautifully-typeset-maths-on-your-blog/#blogger">checkmyworking.com</a>

**Edit:** Set your mobile template to "Custom" to pick up the MathJax on mobile.
