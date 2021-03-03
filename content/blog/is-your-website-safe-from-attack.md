---
title: Is your website safe from attack?
subtitle: A interesting tale about function of design
excerpt: >-
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
  incididunt ut labore et dolore magna aliqua.
date: '2011-05-25'
seo:
  title: Is your website safe from attack?
  description: >-
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Is your website safe from attack?
      keyName: property
    - name: 'og:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
      keyName: property
    - name: 'og:image'
      value: images/post-1.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Is your website safe from attack?
    - name: 'twitter:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
    - name: 'twitter:image'
      value: images/post-1.jpg
      relativeUrl: true
layout: post
---

Having a website that handles user-submitted data is quite common and making sure your website is secure from vicious attacks is an important aspect to running a successful website. Validation and filtering are extremely important to ensure your site prevents threats from unwanted visitors.

#### What is code injection?

Simply put, code injection is when a user exploits a script or program with a bug; allowing the attacker to insert (or “inject”) extra code which then alters the execution or outcome. This can have devastating effects both locally on the web server and globally across a whole network. The severity depends on the type of injection attack and can a SQL or email injection or a full on server worm or virus.

Usually, the majority of injections are caused by poor administration regulations when accepting user-submitted content from the Internet. Good attackers can use email forms to insert additional content using it as a spam gateway. This could really hurt your creditably if you start sending out spam mail in your company’s name. Another major attack are SQL injections. [MySQL](http://mysql.com) is used on literally millions of websites and while I’m sure many sites do have some type of security, others do not and can fall victim. SQL injections can have devastating consequences as well like exposing user account passwords, erase database contents, or even having access and erasing your server; which is very bad.

#### Tips to protect your site

It’s actually not as hard as you think to help defend your site from most forms of attack. You don’t even need an information technology degree! You just need to know your options available to you and how to put them in place. You can learn more about PHP security ([Manual](http://php.net/manual/en/security.php) | [Tutorial](http://phpfreaks.com/tutorial/php-security)) thanks to [PHPfreaks.com](http://phpfreaks.com)
