---
title: JS Hint
subtitle: A interesting tale about function of design
excerpt: >-
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
  incididunt ut labore et dolore magna aliqua.
date: '2011-05-22'
thumb_image: images/siteshot1.png
thumb_image_alt: White concrete building wall
image: images/siteshot1.png
image_alt: White concrete building wall
seo:
  title: JS Hint
  description: >-
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: JS Hint
      keyName: property
    - name: 'og:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
      keyName: property
    - name: 'og:image'
      value: images/siteshot1.png
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: JS Hint
    - name: 'twitter:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
    - name: 'twitter:image'
      value: images/siteshot1.png
      relativeUrl: true
layout: post
---

This nifty webapp is a scripting godsend! Personally, I do a lot of work with JavaScript and when it comes time to subcontract work out if I need to manage a workload or a project's timeline I need to be able to trust in whom I've picked to help and in their ability and logical markup. Obviously I would be doing a screening, but I know what happends deep into projects, many hours and lines of code from the starting point. Those perfect semantics you handed in at the interview time arn't looking as pretty now, and rather then make sure I just drop what they give through my own personal "vaildator". Enter: JSHint.

> "[JSHint](http://jshint.com) is a community-driven tool to detect errors and potential problems in JavaScript code and to enforce your team's coding conventions. It is very flexible so you can easily adjust it to your particular coding guidelines and the environment you expect your code to execute in."

[JSHint](http://jshint.com) is an open-source project that is supported and maintained by the JavaScript developer community. The source code is available on [GitHub](http://github.com/jshint/jshint/).

[](http://jshint.com)

### Simple Usage

Taken from the official website; [JSHINT](http://jshint.com) is a global function and can take two parameters:

\[javascript\] var result = JSHINT(source, options); \[/javascript\]

The first parameter is either a string or an array of strings. If it is a string, it will be split on 'n' or 'r'. If it is an array of strings, it is assumed that each string represents one line. The source can be JavaScript or JSON, the choice is yours.

If all of the enabled tests pass, JSHINT returns true. Otherwise, it returns false.

If false, you can use JSHINT.errors to retrieve the errors or request a complete data structure representing the "lint" by using JSHINT.data(). IF you need more information, the JSHint source code is quite well documented and isn't hard to get going quickly.

You can also set options in-file,

\[javascript\] /\*jshint evil: true, boss: true \*/ \[/javascript\]

And let JSHint know what global variables it should expect,

\[javascript\] /\*global DISQUS: true, jQuery: false \*/ \[/javascript\]

In the example above, JSHint will allow you to override DISQUS, but complain if you try to override jQuery.
