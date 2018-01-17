---
title: "Images"
date: 2017-09-10T22:17:57-04:00
draft: false
weight: 7
---

To add images to our document we use the `<img>` element.
The basic pattern to use this element for adding images
to our webpage is this:

    <img src="image.png" alt="A brief description of the image">

As we can see, the `<img>` element is comprised of a single tag and a couple
of attributes. Remember that the mission of attributes is to provide additional
information to their element.

In this case, the `<img>` <span class="underline">*needs*</span> a **src** (short for "source")
attribute that tells the element where the image is located at, and
it <span class="underline">*should*</span> have an  **alt** (short for "alternative text") attribute
which has a couple of functions to it:

1. First, the alt attribute will describe what the image is about to visually-impaired visitors that
are browsing our page with the help of a
[screen reader](https://en.wikipedia.org/wiki/Screen_reader).
2. And second, if the image isn't correctly loaded to our page, the alternative text will be displayed instead of the image.

### Images in Action

Let's follow the pattern above and add an image to our page a:

    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="utf-8">
        <title>Awesome Title</title>
      </head>
      <body>
        <h1>Hello World!</h1>
        <p>
          My name is <strong>Luis Rodriguez</strong>, I'm 20 years old and
          <em>my favorite food is pizza</em>.
        </p>
        <img src="pizza.jpg" alt="Picture of a pizza">
      </body>
    </html>

After saving my file and refreshing the browser:

![Screenshot of a broken image in HTML](alt_text_image.png)

The result was pretty disappointing... But
at least we got to see the **alt** attribute in action!

What is the problem with our image? It is pretty simple, I broke the image element
by putting erroneous info at the **src** attribute; by writing "pizza.jpg", I'm making
reference to a image that doesn't exist. Let's solve this issue
by fixing the info I provided to the element:

    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="utf-8">
        <title>Awesome Title</title>
      </head>
      <body>
        <h1>Hello World!</h1>
        <p>
          My name is <strong>Luis Rodriguez</strong>, I'm 20 years old and
          <em>my favorite food is pizza</em>.
        </p>
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/d/d3/Supreme_pizza.jpg"
          alt="Picture of a pizza"
          width="500px"
        >
      </body>
    </html>


Correctly sourcing to an existing image, give me this as a result:

![Screenshot of a correctly loaded image](image_example.png)

Let's examine a little bit more closer the code for the `<img>` element.

    <img
      src="https://upload.wikimedia.org/wikipedia/commons/d/d3/Supreme_pizza.jpg"
      alt="Picture of a pizza"
      width="500px"
    >

From order of least to more important point, I want you to notice:

1. The spacing: I broke the attributes into separate lines to improve readability.
The browser interprets the code the same but it is easier for us to see
what's happening inside of the element.

2. The width attribute: Just a new attribute related to images. As its name
explains, it allows us to control the width of the image. There's also a
height attribute, but it is recommended to only use one of them (width or height)
at a time to maintain the ratio of the image.

3. The link to the [image](https://upload.wikimedia.org/wikipedia/commons/d/d3/Supreme_pizza.jpg):


### Local Images

<!-- a element stands for anchor

using a elements with images and external images

Opening links in new tabs -->
