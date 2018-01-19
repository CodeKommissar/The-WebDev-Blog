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

Let's follow the pattern above and add an image to our page:

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
        <img src="pizza.png" alt="Picture of a pizza">
      </body>
    </html>

{{% notice note %}}
We'll be playing with the image of a pizza in the following examples. But in the
exercises section you'll be adding an image of your own preference :).
{{% /notice %}}

After saving my file and refreshing the browser:

![Screenshot of a broken image in HTML](alt_text_image.png)

The result was pretty disappointing... But
at least we got to see the **alt** attribute in action!

What is the problem with our image? It is pretty simple, I broke the image element
by putting erroneous info at the **src** attribute; by writing "pizza.jpg", I'm making
reference to a image that doesn't exist. Let's solve this issue
by fixing the information I provided to the element:

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

From order of least to most importance, I want you to notice these three things:

1. The spacing: I broke the attributes into separate lines to improve readability.
The browser interprets the code the same but it is easier for us to see
what's happening inside of the element.

2. The width attribute: Just a new attribute related to images. As its name
explains, it allows us to control the width of the image. There's also a
height attribute, but it is recommended to only use one of them (width or height)
at a time to maintain the ratio of the image.

3. The link to the image:
I'm using an external link for the [location of the image](https://upload.wikimedia.org/wikipedia/commons/d/d3/Supreme_pizza.jpg). This is OK when we're
starting, but the linked image in that URL could be changed or deleted in
the future. To avoid this, let's learn about local images.

### Local Images

Instead of depending on an external source to add an image to our website, let's
download that image and put it inside our project.

To do this, go to the the [pizza photo](https://upload.wikimedia.org/wikipedia/commons/d/d3/Supreme_pizza.jpg),
right click it, and select "Save image as...". When choosing the folder to save
the image, select the folder in which we have our HTML project (Remember; "Home/The_WebDev_Blog/HTML/"). And save it as "pizza.png".

Change your src attribute of the image element to look like this:

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
          src="pizza.png"
          alt="Picture of a pizza"
          width="500px"
        >
      </body>
    </html>

The result in the browser shouldn't change, but now we've "future-proofed" our image.

### Exercises

1. Create a "images" directory inside of the HTML folder.
2. Put "pizza.png" inside of that "images" directory.
3. Change the src of the image to "images/pizza.png"
4. Save your code and refresh the browser. Nothing should change. But
now our project is better structured :).
5. Add a new image to your project related to your random fact, put it inside
of the "images" folder and replace the image of the pizza by your own image.
Remember to update the "alt" attribute.


<!-- a element stands for anchor

using a elements with images and external images

Opening links in new tabs -->
