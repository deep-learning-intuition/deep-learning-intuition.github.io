---
layout: page
mathjax: true
permalink: /digital-images/
---

- [Digital Images](#digital-image)
- [Why Study Computer Vision](#study)
  - [Hypothesis](#hypothesis)
  - [Update Rule](#update-rule)
- [Your First CV Program](#first)

[//]: # (Image References)

[one_pixel_image]: ./assets/one_pixel_image.jpg "A one pixel image"
[nine_pixel_image]: ./assets/nine_pixel_image.jpg "A nine pixel image"

<a name='digital-image'></a>

## Digital Images

This is an image. ![Just an image][image] But it's not just any image. You're viewing it on your computer (or smartphone), so it's stored in your computer as a **digital image**. A **digital image** is made up of **pixels**. A **pixel** is the smallest unit of an image. In fact, this is an image. ![One pixel image made up of one white pixel][one_pixel_image]

Not much of an image, huh? Let's look at an image with a few more pixels. ![9 pixel image][nine_pixel_image]

How about an image with enough pixels for you to recognize? ![a pixelated image][pixelated_image] Stand far away and the different blocks of colors, that is, the pixels, start to blend together.

Why are we paying so much attention to pixels? Once you understand the fundamental building block of a digital image, you can perform all kinds of cool operations on an image such as brightening it, rotating it, determining its contents, and more!

How are digital images stored in a computer? Well that depends on the image **format**. But regardless of the format, like anything else that is stored in a computer, a digital image is just a jumble of bits and bytes. To keep things simple, we will first describe **grayscale** images. Grayscale images have colors ranging from black to gray to white. For our purposes, we can think of a grayscale image as a 2D matrix of numbers. Each number describes a pixel with its value being the intensity, or _how much_, of a color the pixel should look like. The **color depth** tells you how many bits make up a single pixel. This means that the **color depth** tells you the number of shades of black, gray, and white a pixel can depict.

For example, a pixel with a color depth of 2 bits can be stored in a computer as 00, 01, 10, or 11. We can choose map these 2 bit patterns to any color we want. ![image of 00 to black, 01 to purple, 10 to blue, and 11 to white][map_of_bits_to_color]

Practically, we would prefer a mapping from bit patterns to colors that makes sense. If we view the bit patterns as binary numbers, $$00_2$$, $$01_2$$, $$10_2$$, and $$11_2$$ as binary numbers, then how about we say that $$00_2$$ represents the **absence of light**, or black, and $$11_2$$ represents the **full intensity of light**, or white. This leaves us with $$01_2$$ and $$10_2$$, which we can think of as the amount of light in a pixel. That would mean $$01_2$$ could be a light black and $$10_2$$ could be a light gray.


## Images as 2D Math Functions

Think of a digital image as 2D mathematical function. A highly pixelated one would be a bunch of tall and short bars. A high resolution image would be smoother and resemble a mathematical curve in a 3D space. Think of a digital image as a 2D math function.

#### Further Reading

Here are some (optional) links you may find interesting for further reading:

- [Gauss-Markov theorem](https://en.wikipedia.org/wiki/Gauss%E2%80%93Markov_theorem), learn why the least squares cost function results in the best fit line.