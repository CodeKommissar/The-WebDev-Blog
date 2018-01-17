---
title: "Basic Structure"
date: 2017-09-10T22:17:57-04:00
draft: false
weight: 4
---

Now that we have everything we need to write HTML, we'll begin
by covering the basic structure of every (good) HTML document.

### DOCTYPE!

The first line we're going to add to our HTML document is the [DOCTYPE](https://en.wikipedia.org/wiki/Document_type_declaration) or
"Document Type Declaration". In the first line of your "index.html" file, type
this:

    <!DOCTYPE html>

This "Document Type Declaration" tells the browser which version of HTML
the page is written in. As good developers that keep up with the modern times,
we'll be using the latest version of HTML which would be HTML5. That line you
see above (and that you already should have in your HTML file) tells the browser
exactly that; "I'm a HTML5 file, please read me that way, thanks!".

### HTML Wrap

Although we told the browser which version of HTML we're currently using,
we haven't told it where does the HTML actually starts in our document.
After the DOCTYPE, add the `<html>`
element (remember that HTML elements usually are comprised of two tags):

    <!DOCTYPE html>
    <html>

    </html>

Did Atom auto-complete the closing tag after you wrote the opening `<html>` tag?
If Atom did it, pretty nice! That's the job of text editors; making our life
easier with features like
<span class="underline">automatic completion</span> and
<span class="underline">syntax highlighting</span>.

Feel free to keep that extra line of space because we'll be ading content
inside of it right away.

### Head & Body

Now we're going to add to two elements to our HTML document: a
`<head>` and a `<body>`. Type this into your file:

    <!DOCTYPE html>
    <html>
        <head>

        </head>
        <body>

        </body>
    </html>

To add those extra spaces (called indentation) after the tags, use your Tab key.
Adding indentation to our code is optional, but we do it for readability. Code
that's correctly indented is code that's easy to read and reason about.

Now to explain a little more about these two new elements; The `<body>` element
contains everything that it is going to be
<span class="underline">displayed in the browser</span>. And on the other side, the
`<head>` element is all about <span class="underline">meta-information</span>.

What do I mean when I say "meta-information"? In the `<head>` we add info that is important
to our page but that we don't necessarily want to display to the users in our website.
I know this doesn't explain much right now, but you'll understand
better as we go.

### Displaying our Page in the Browser

Now we'll add some text to our document and then we will display it in the
browser. Type anything you want inside of the `<body>` element, I'll just
write "Hello World!":

    <!DOCTYPE html>
    <html>
        <head>

        </head>
        <body>
            Hello World!
        </body>
    </html>

Now, it is **very important** that you save your file. To do this, in your
keyboard press the Ctrl key and the S key at the same time. You can also go
to the menu at the superior part of Atom, click in "File" and then click in
"Save".

I hope that you didn't close your terminal because we're going to type one
simple command.

If you're using Google Chrome as your browser, enter this
into your command line:

    $ google-chrome index.html

If you're using Mozilla Firefox, enter this:

    $ firefox index.html

Any of those commands will automatically open your browser (if you have it closed)
and open the file that you indicated. You should be seeing something like this:

![Screenshot of basic HTML page](hello_world_html.png)

The file path should be different but the content should look similar (or the
same if you also wrote "Hello World!" into your HTML document).

Every time you change something in your page and want to see it in the browser,
you're going to need to repeat these two steps:

1. Save <span class="underline">(Ctrl + S)</span> your file at the text editor.
2. Refresh <span class="underline">(F5)</span> your browser.

Make a simple change to your page in Atom and follow the steps above to make
sure you really know them.

### Adding a Title

Right now the title of our page is literally "index.html", let's fix that by
making use of the `<title>` element. Let's add it to the `<head>` element:

    <!DOCTYPE html>
    <html>
        <head>
            <title>Awesome Title</title>
        </head>
        <body>
            Hello World!
        </body>
    </html>

Refresh your page and look at the top section of your browser.
Now the title of our HTML page is "Awesome Title".
<span class="strikethrough">Awesome!</span> Great!

### Going WorldWide

The last step to complete our basic structure it is going to be pretty short
actually. Type this in the line above the `<title>` element:

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

Here we're introducing a couple of new things:

First, the `<meta>` element, which as you may notice <span class="underline">doesn't</span> have a closing tag. Because this element doesn't have content inside of it, it doesn't need a `</meta>` tag closing it.

And second, we're seeing our first **attribute**; `charset="utf-8"` inside of the `<meta>` element.

Most attributes can only be used on certain elements and they tend to have
a predetermined format. Their job is to provide extra info to their element.
We're going to cover them a little bit more later, but for now I'll explain
what we just add to our document.

`<meta charset="utf-8">` basically tells the browser the character
codification of our website. If you want to test what happens when
you don't add this meta element to your HTML documents, remove the
`<meta>` element and add this line to the body of your file:

    "El niño esta en la biblioteca"

Translated to English that would say "The kid is in the library". As you can
see, instead of a "ñ" character, you're going to see some weird characters.
Now add the `<meta>` element again and refresh your page. The text should look
fine now.

Not only you're making your site available to all the languages of the World
by adding a single line to your HTML document, you're also avoiding the
[UTF-7 XSS Cheat Sheet](https://www.owasp.org/index.php/XSS_Filter_Evasion_Cheat_Sheet#UTF-7_encoding)
security exploit in older browsers. Basically we're killing two birds with one
stone in our code.
