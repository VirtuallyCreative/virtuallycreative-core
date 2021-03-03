---
title: HTML5 Semantics Introduction
subtitle: A interesting tale about function of design
excerpt: >-
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
  incididunt ut labore et dolore magna aliqua.
date: '2011-07-19'
thumb_image: images/slide4.jpg
thumb_image_alt: White concrete building wall
image: images/slide4.jpg
image_alt: White concrete building wall
seo:
  title: HTML5 Semantics Introduction
  description: >-
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: HTML5 Semantics Introduction
      keyName: property
    - name: 'og:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
      keyName: property
    - name: 'og:image'
      value: images/slide4.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: HTML5 Semantics Introduction
    - name: 'twitter:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
    - name: 'twitter:image'
      value: images/slide4.jpg
      relativeUrl: true
layout: post
---

# Introduction

Welcome to the Beginner HTML5 tutorial part 1! In this tutorial I'm going to cover some of the new updates and changes made to the HTML specification with version 5. Although not officially ready for release by the W3C, we can still have some fun using some of the new elements. In part 2 I will go over HTML5 Content Models and the proper way to use some of the new elements introduced here in part 1.

**\*\*\*NOTE:** This tutorial although beginner in scope, does assume you have some knowlege of HTML4, or XHTML. Either way, a little understanding will help comprehend some of the changes/updates that HTML5 is featuring. I also breifly touch on some microformats and how HTML5 applies to them but you don't need to know about them as they arn't totally relevant for the scope of this tutorial but maybe a google search couldn't help? **END NOTE\*\*\***

### So, what's the deal with HTML5?

Theirs going to be some new players in town besides our span, em, abbr, strong, et al. Not too many, nothing someone couldn't handle. Except now we don't call them "inline" anymore, instead they describe "text-level semantics". Catchy, I know. So lets meet some of the new guys and check out what they bring to the web designer's markup. Their are four that are more used than others:

##### Element 1: mark -he's a good friend!

I don't know about you all personally, but I use Google all the time. While searching you'll often see your searched term highlighted within results. To do this you could mark up every instance of the search term with a span element, but spans hold no semantic value. Their great for when you need to drop in those hidden classes, or put a wedge between some div's, but not here. You could even use em or strong but all of these wouldn't be semantically correct. You don't want to place any importance on the search term, just emphasise its location relative on the page so you can find it.

**Tada! Enter, the mark element:**

\[html\] <h1>Search results for 'magical'</h1> <ol> <li><span class="removed\_link" title="http://faireytales.com/"> Riding the <mark>magical</mark> unicorn across the rainbow of the internet.</span></li> </ol> \[/html\]

The mark element doesn't attach any importance to the content within the tags, other than to show that it's currently selected. HTML5 Spec says: mark element "denotes a run of text in one document marked or highlighted for reference purposes, due to its relevance in another context." You could use mark element in contexts other than search results to achieve a highlighting effect, but examples off the top of my head, I got nothing.. Oh! You could... Naw, just kidding.

##### Element 2: time -never enough of you!

hCalendar is among the most popular microformats because it provides an invaluable resource for marking up events so that users can add them straight to their calendars. Oh yeah, the good stuff. The only annoying part with hCalendar is describing dates and times in a machine-readable way. I like to describe dates as "May 20th" or "next Friday" but parsers expect ISO date format: YYYY-MM-DDThh:mm:ss. Talk about ugly and annoying to write each time.

**Using HTML5, insert the time element instead:**

\[html\]<time datetime="1902-01-13"> January 13th, 1902 </time> \[/html\]

The time element can be used for dates, times, or combinations of both:

\[html\]<time datetime="17:00">5pm</time> <time datetime="2011-04-07">April 7th</time> <time datetime="2011-04-07T17:00">5pm on April 7th</time> \[/html\]

You don't have to put the datetime value inside the datetime attribute but you then must expose the value to the end user:

\[html\]<time>2011-04-07</time>\[/html\]

##### Element 3: meter -how do you stack up?

The meter element is for markup of measurements and only if those measurements are part of a scale with minimum and maximum values.

\[html\]<meter>9 out of 10 cats</meter>\[/html\]

You don't have to expose the maximum value. You can use the max attribute instead:

\[html\]<meter max="10">9 cats</meter>\[/html\]

There's a min attribute as well as: high, low and optimum attributes too. If you want, you can even hide the measurement itself inside a value attribute:

\[html\]<meter low="-273" high="100" min="12" max="30" optimum="21" value="25"> It's quite warm for this time of year for 25 degrees! </meter> \[/html\]

##### Element 4: progress -we're making some right now!

The progress element allows you to markup a value that is "in the process of changing", which on the internet is a lot of items:

\[html\]Your profile is <progress>60%</progress> complete.\[/html\]

Once again like meter element, you have min, max and value attributes if you want to use them:

\[html\]<progress min="0" max="100" value="60'></progress>\[/html\]

The progress element is most useful when used with DOM Scripting. If you're feeling frosty can use Javascript to dynamically update the value, allowing the browser to communicate that change to the user. Awesome for Ajax file uploaders, loaders in general, profile creation bars, status bars I think you get the idea...

That's the end of this post but check out the next part: HTML5 Semantic Changes

You can also check out the whole tutorial on [Dream.In.Code as well!]( http:=)
