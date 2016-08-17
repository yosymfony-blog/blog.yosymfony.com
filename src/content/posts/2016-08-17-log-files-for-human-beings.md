---
layout: post
title: "Log files for human beings"
description: "Human-friendly Monolog handler for dev environments"
author: Víctor
categories: [php]
tags: [monolog,log]
thumb_img: tools.png
header_img:
  url: "header-files-bn.jpg"
  author: "ExeterAnna"
  author_url: "https://flic.kr/p/9noJDW"
---
At development time it's important to understand what is occurring inside your
code to take appropriate actions. At that moment, debugger and logger tools
have an importan role to play. Log files are a huge stream of text thought for
computers instead of human that, sometimes, it tough to work with those.

Ok, we get to the point. [EasyLogHandler](https://github.com/EasyCorp/easy-log-handler)
is a human-friendly [Monolog](https://github.com/Seldaek/monolog) handler
written by [Javier Eguiluz](https://github.com/javiereguiluz). It's optimized
to display the log information in a clear and concise way. This handler is ideal
for dev environments.

Below, an example of output:
![An EasyLogHandler output example](/assets/img/easyLogHandler-output.png "An EasyLogHandler output example")

The output text is more suitable for you and me. You can see there are not many marks
of timestamps because in `dev` environment you shouldn't care about that.

To conclude this post, I'll say that sometimes we forget that we coding for humans because
machines only understand binary code. Writing a readable code is important. In
case of log files in certain environments, is important to keep that concept in mind.  
