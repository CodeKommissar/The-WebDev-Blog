---
title: "Introduction"
date: 2017-09-10T22:17:38-04:00
draft: false
weight: 1
---

HTML stands for:
<span class="bold">H</span>yper
<span class="bold">T</span>ext
<span class="bold">M</span>arkup
<span class="bold">L</span>anguage and its job is to describe
the structure and content of web pages.
It is a language that computers can understand, but it isn't a
Programming Language by itself. As its name tell us, it is just a Markup Language.

HTML is composed of elements which, on most cases, have two tags; an opening
tag and a closing tag (which has an extra forward slash on it). HTML mission
is to tell the browser *what* do we want to display.

### High Level Overview

HTML is made of these 'elements' that allow us to describe the
contents of our website. For example, we have a `<p></p>` element for paragraphs.
As of right now, the `<p>` element is made of two *tags*; `<p>` and `</p>`.
Think of these two separate
tags as two pieces of bread in a sandwich; They "close over" the
*contents* of the sandwich. In our case, HTML tags close over the *content*
 that we are representing in our website.

![A photo of a sandwich](sandwich.jpg?width=60%)

As a simple example, to name the days of the week in a single paragraph of HTML,
we'd simply write something like this:

    <p>Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday</p>

Notice how we enclose our content with the two tags:
`<p>` and `</p>`, the first tag (called opening tag) doesn't have a slash
and the last tag (called closing tag) does have a slash after the
'Less-than sign'. So we could define a regular paragraph in any HTML documents as:

1. An opening `<p>` tag.
2. The content of the paragraph in the middle
3. A closing `</p>` tag.

If I wanted to describe something a little bit more complex, like the beginning
of Moby Dick, I would do it like this:

    <h1>Moby-Dick Chapter 1</h1>

    <p>
    Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world. It is a way I have of driving off the spleen and regulating the circulation.
    </p>

In this short excerpt we have a new element; `<h1>` which is used for headings
(we're going to cover it later) that describes in which chapter
are we located at the moment and a paragraph element that begins to tell the story.

### A Little Bit of History

![A photo of a Tim Berners-Lee](tim.jpg?width=60%)

HTML was created by [Tim Berners-Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee)
between 1989 and 1990 with the purposes of:

1. Having a simple standard format to publish scientific and technical documents.

2. Allowing these documents to be easily shareable with the help of the
Internet.

That's basically all that there is to HTML. A simple standard to write documents
that anyone could read and share through the Internet.

This first version of HTML was all about text and links. As time went through,
with Internet speeds going up and being more accessible to the regular people like
you and me, new versions of HTML emerged to add new features to the language
like; New Tags, Images, Sound, Video and even GeoLocation.

The current version of HTML is HTML5, which is what we are going to be learning
on this section and it includes all of the features we see above and more.

### Why is HTML important?

HTML represents the basic structure of almost all of the web pages in the world.
To make a simple analogy, think of HTML as your bone structure, without
your bones holding your body, you would be just laying on the ground all day
without being able to do much.

As Front-End/Full-Stack developers we're going to see a lot of HTML (at least
at the beginning of our journey) and to be honest, you could learn almost 90%
of the HTML you need to know in a couple of days. It is going to be simple,
fun and good for your career.
