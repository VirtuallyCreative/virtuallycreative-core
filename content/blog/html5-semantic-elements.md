---
title: HTML5 Semantic Elements
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
  title: HTML5 Semantic Elements
  description: >-
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: HTML5 Semantic Elements
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
      value: HTML5 Semantic Elements
    - name: 'twitter:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
    - name: 'twitter:image'
      value: images/slide4.jpg
      relativeUrl: true
layout: post
---

## Semantic Changes

Google, in 2005, did some research to find out what common names web developers were giving inside their markup. An awesome uber parser looked at over a billion web pages and calculated the most common class names. The results...didn't shock anyone. Class names such as "header," "footer," and "nav" were among the highest charted. These overused semantics allow for a nicely crafted segway to the new structural elements introduced in HTML5.

#### Semantic Element 1: section

In a nutshell, the section element is used for grouping together "contextually-releated content". Hold up, yes I know we have div elements but listen, the major difference is that a div element has no semantic meaning at all! None! It doesn't tell you anything about the content its holding unless you give it a clever ID (like "main\_content" or something...) but even then this is only for us humans, not a web browser. So, the section element is used explicity for grouping related content, and is more semantically correct than just a plan div. You might be able to replace SOME of your div elements with section elements, but remember to ask yourself, "Is all of the content related?":

\[html\] &lt;section&gt; &lt;h1&gt;Intro to HTML5&lt;/h1&gt; &lt;p&gt;It's what you're learning, RIGHT NOW! In blog format.&lt;/p&gt; &lt;p&gt;By Another McGuy&lt;/p&gt; &lt;/section&gt; \[/html\]

#### Semantic Element 2: header

The HTML5 specification describes a header element as the container for "a group of introductory or navigational aids." Sure, why not right? Usually the logo/site text and main navigation are always somewhere within a header but there is a critical difference between the header element in HTML5 and the generally accepted use of the word "header." In previous versions of HTML and XHMTL you only see one header on a page, but a document can have multiple header elements. You can use the header element within our new section element, for example:

\[html\] &lt;section&gt; &lt;header&gt; &lt;h1&gt;Intro to HTML5&lt;/h1&gt; &lt;/header&gt; &lt;p&gt;It's what you're learning, RIGHT NOW! In blog format.&lt;/p&gt; &lt;p&gt;By Another McGuy&lt;/p&gt; &lt;/section&gt; \[/html\]

A header will usually appear at the top of a document or section since you want a header for your site, but it doesn't have to. It is defined by its content-introductory or navigational aids-rather than its position on the page.

#### Semantic Element 3: footer

Like the header element, footer sounds like it's a description of position but, this isn't the case either. The footer element should contain information about its containing element: who wrote it, copywrite information, links to related content, etc. Again though, like with header above, the difference with our HTML5 footer element is that we are used to usually having one footer for an entire document, HTML5 allows us to have multiple by placing footers within a section.

\[html\] &lt;section&gt; &lt;header&gt; &lt;h1&gt;Intro to HTML5&lt;/h1&gt; &lt;/header&gt; &lt;p&gt;It's what you're learning, RIGHT NOW! In blog format.&lt;/p&gt; &lt;footer&gt; &lt;p&gt;By Another McGuy&lt;/p&gt; &lt;/footer&gt; &lt;/section&gt; \[/html\]

#### Semantic Element 4: aside

Just as the footer element matches the concept of something which usually migrates to the bottom of a page, the aside element matches the concept of a sidebar. But, I'm not referring to position. Just because some content appears to the left or right of the main content isn't enough to use the aside element. Once again, its the content that matters not position. Think of it more of an "aside" from English class. A character in a story would have an "aside" in his head about the current context which only the character (and reader) would know about. Like having a conversation with someone and while they're talking, you're thinking to yourself: Wow, this guy is a jerk!. That, is an aside... from english class. So how does this relate?

The aside element should be used for contextually related content. If you have a chunk of content that you consider to be separate from the main content (our "jerk" statement), then the aside element is probably the right container for it. Ask yourself if the content within an aside could be removed without reducing the comprehension of the main content of the doucment or section (if you didn't think about the talking man being a jerk, does that change what he's telling you at all?). The answer is no, it shouldn't.

\[html\] &lt;section&gt; &lt;header&gt; &lt;h1&gt;Intro to HTML5&lt;/h1&gt; &lt;/header&gt; &lt;p&gt;It's what you're learning, RIGHT NOW! In blog format.&lt;/p&gt; &lt;footer&gt; &lt;p&gt;By Another McGuy&lt;/p&gt; &lt;/footer&gt; &lt;aside&gt; &lt;blockquote&gt; "This blog is so awesome! It helped me learn the in's and out's of HTML5 without too much fuss! I would recommend this blog to anyone who wants to learn HTML5!" -Another Dudeostopoilous &lt;/blockquote&gt; &lt;/aside&gt; &lt;/section&gt; \[/html\]

The blockquote here is a good example of related content. Like the jerk comment above you can remove the quote without affecting the comprehension of the main content. So, aside = NOT A SIDEBAR, you don't usually put quotes or a "Comment Now" box in a sidebar, do you? I didn't think so unless it's some crazy design for some "amazing" clients. It's common on blogs and some forums to place an author bio in a sidebar but that kind of data is best suited to the shiney new footer element- the HTML5 specification explicitly states "authorship information" as footer element material. So please, make the connection happen and help poor footer element out.

But Google's parser information didn't lie, you should be ecountering websites that, a majority of the time, use a header for the top, footer for the bottom, and sections all around with relevent content inside. But then their are other sites which do not. Watch out for them! They will turn you towards the semantic dark side...

and in this case, it's totally not cooler. I swear.

#### Semantic Element 5: nav

The nav element does exactly what you think it does. SURPRISE! It contains navigation information, usually in the form of styled unorderd lists I hope. Actually, I should state that the nav element is intended for "major navigational information" like the main site's navigation. Just because a group of links are grouped together in a list isn't enough reason to use nav. If I see this, I will hunt you down. Quite often, a nav element will appear within a header element. That makes sense when you consider that the header element can be used for "navigational aids." So don't freak if you see this.

#### Semantic Element 6: article

I like to think of header, footer, nav and aside as being underling forms of the section element. A section is any amount of related content, while headers, footers, navs, and asides are chunks of specific kinds of related content which could be inside a section. The article element is a specialized kind of section. Use it for "self-contained related content." The hard part is figuring out what exactly constitutes "self-contained." Don't worry, its not confusing, ask yourself if you would syndicate the content in an RSS or Atom feed. This is a good indicator. If the content still makes sense standing on its own without the help of the main content to fill in the who,what,why,when,where.. and how, then article element is probably the right element to use. In fact, the article element is specifically designed for syndication! Thank you HTML5 Spec. If you use a time element within an article, you can add the optional pubdate Boolean attribute to show that it contains the date of our publication:

\[html\] &lt;article&gt; &lt;header&gt; &lt;h1&gt;Intro to HTML5&lt;/h1&gt; &lt;/header&gt; &lt;p&gt;It's what you're learning, RIGHT NOW! In blog format.&lt;/p&gt; &lt;footer&gt; &lt;p&gt;Published &lt;time datetime="2011-04-11T20:10" pubdate&gt; 8:10pm on April 11th, 2011 &lt;/time&gt; &lt;p&gt;By Another McGuy&lt;/p&gt; &lt;/footer&gt; &lt;/article&gt; \[/html\]

If you have more than one time element inside an article, you can only use the pubdate attribute ONCE, remember that markup Jedi.

The article element is useful for blog posts, news stories, comments, reviews, and forum posts as well and it also covers exactly the same useage cases as hAtom microformat which is a nice benefit.

If you actually take the time to read the massive volume which is the full HTML5 specification it will tell you the article element should also be used for self-contained widgets: stock tickers, calculators, clocks, weather widgets and other similar items. When I hear smack-talk about HTML5 it's usally because everyone is confused about the difference between proper usage of article and section elements. All that seperates them is the word "self-contained." Deciding which element to use would be easy if there were some hard and fast rules. But alas, it's a grey zone. Designer's interpretation. You can have multiple articles within a section, you can have multiple sections within an article, you can nest sections in sections and articles within articles. Guess who get's to make the call about which to use when, properly.

### The Wrap-Up

HTML5 gives us a new structural elements to bend to our design force and they're especially crafty if you're putting together a "good" website. You can now replace SOME of your div elements with more semantically precise structural elements but don't go crazy. I don't want to see div elements dissapear overnight! Don't swap all your div elements for shiny new HTML5 elements just for the sake if it. It should be semantically correct for the content you're marking up. They provide web browsers with a completely new way to understand your content. Not for you to say goodbye to our good friend div.
