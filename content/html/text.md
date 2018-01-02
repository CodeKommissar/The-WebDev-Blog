---
title: "Adding Text"
date: 2017-09-10T22:17:57-04:00
draft: false
weight: 5
---

Your HTML document should be looking similar to this:

    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="utf-8">
        <title>Awesome Title</title>
      </head>
      <body>
        Hello World!
      </body>
    </html>

We already added text, but that text is not **semantic** enough.
As far as the browser knows, it is just random words floating in our body (and
that should be displayed because they're *in* the body).

When I say it "is not semantic enough" what I'm trying to say is that
it doesn't have a real meaning. Let's quickly solve this issue, wrap the text in your
body with the `<h1>` element, like this:

    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="utf-8">
        <title>Awesome Title</title>
      </head>
      <body>
        <h1>Hello World!</h1>
      </body>
    </html>

Save your file (Ctrl + S) and refresh your browser, you should now be seeing
"Hello World!" bolded and with a bigger font size. That is a **heading**.

Did you notice that the words "Hello World!" are displayed, but the `<h1>`
and `</h1>` tags that surround them doesn't show up anywhere in the browser? That's
exactly what HTML does; It takes elements in the form of code (the
`<h1>Hello World!</h1>` that you wrote) and it returns
their graphical representation to show in the browser.

### Headings

Headings come in six "types" and their job is to act as a "title" in your
body; They should shortly describe what is below them.

Here are the six available headings in action:

    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="utf-8">
        <title>Headings</title>
      </head>
      <body>
        <h1>Very Important Heading</h1>
        <h2>Important Heading</h2>
        <h3>Regular Heading</h3>
        <h4>Trivial Heading</h4>
        <h5>Less Important Heading</h5>
        <h6>"Nobody cares" Heading</h6>
      </body>
    </html>

Displayed on a browser, they should look like this:

![Screenshot of the six types of headings](headings.png)

There are a couple of basic rules regarding headings that you should know:

First, there should be only a `<h1>` element per page. This is called the
"main heading" and it tends to be reserved to display the name of the website
at the superior
part of the screen. The other tags can be used as many times as you desire,
but...

The second rule is that headings should be used in order, you shouldn't use
a `<h6>` tag just because. If you follow the rules accordingly, you would use
`<h6>` as a sub-heading of `<h5>`, `<h5>` as sub-heading of `<h4>` and so on.

### Paragraphs

Now, to make paragraphs of text, we use the `<p>` element. Simple, right?

We already saw the `<p>` element in the [Introduction](/html/intro), so
this is going to be an easy challenge for you:

1. Create a paragraph in the body of your HTML document, that says your name,
your age and a random fact about yourself.

It should look like this (but with your own information):

    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="utf-8">
        <title>Awesome Title</title>
      </head>
      <body>
        <h1>Hello World!</h1>
        <p>
          My name is Luis Rodriguez, I'm 20 years old and my favorite food is pizza.
        </p>
      </body>
    </html>

Done? If you displayed your info in your browser, keep reading. If not,
you already know what to do (save the file in your editor and refresh your browser).

### HTML Tags and Spacing

See the positioning of these two elements:

    <h1>Hello World!</h1>

And:

    <p>
      My name is Luis Rodriguez, I'm 20 years old and my favorite food is pizza.
    </p>

As you may notice, the `<h1>` element has the tags in the same line, and the
`<p>` element has the tags and the content in separate lines.

As far as the browser cares, these two positioning/spacing options are the same,
it will display the content the same if the tags are in the same line or in
separate lines.

Because it is an stylistic choice, go with the option that you find easier to
read. Mix and match to find your own balance and strive for good readability
in your HTML documents.
