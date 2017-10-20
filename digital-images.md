---
layout: page
mathjax: true
permalink: /digital-images/
---

- [Intro](#intro)
- [Digital Images](#digital-image)
- [Images as 2D Math Functions](#images-as-math-functions)
- [Image Filters](#image-filters)
- [Your First CV Program](#first)

[//]: # (Image References)

[selfie]: ./assets/selfie.jpg "Selfie"
[group_photo]: ./assets/group_photo.jpg "Group photo"
[one_pixel_image]: ./assets/one_pixel_image.jpg "A one pixel image"
[nine_pixel_image]: ./assets/nine_pixel_image.jpg "A nine pixel image"
[blurred_image]: ./assets/blur.jpg "Blurred image"
[sharpened_image]: ./assets/sharpen.jpg "Sharpened image"
[embossed_image]: ./assets/emboss.jpg "Embossed image"
[edge_image]: ./assets/edge.jpg "Edge finding"

<a name='intro'></a>

## Intro

Suppose you recently vacationed through Southeast Asia, taking selfies and group photos. Upon returning home, you realize you've taken 1,000 photographs. As you start to sort through them, you see photos you wish to delete such as those taken in poor lighting and unflattering selfies. All is not lost since you also discover beautiful group photos invoking fun memories, funny selfies with animals at the zoo, and other treasured photographs you'd like to keep. You want to sort the photographs you've taken into two groups, "keep" and "delete". As the group names suggest, you'll delete the photos in the "delete" group, and keep the photos in the "keep" group. Manually sorting through all 1,000 photos is time-consuming, a task you'd rather avoid. Plus, you'd rather start planning your next vacation anyway! With computer technology, there must be a computer program you can use to sort your photographs automatically. There is where computer vision, machine learning, and deep learning come into play. With advances in computer vision technology in recent years, computers are now able to "see" and "understand" images much better than in the past. The rest of the lectures will prepare us with knowledge and techniques to build such a computer program. **Image classification** is the task of assigning an image a label from a fixed set of categories. For example, suppose you have 1,000 images of stored on your computer 

<a name='digital-image'></a>

## Digital Images

This is an image. ![Just an image][image] But it's not just any image. You're viewing it on your computer (or smartphone), so it's stored in your computer as a **digital image**. A **digital image** is made up of **pixels**. A **pixel** is the smallest unit of an image. In fact, this is an image. ![One pixel image made up of one white pixel][one_pixel_image]

Not much of an image, huh? Let's look at an image with a few more pixels. ![9 pixel image][nine_pixel_image]

How about an image with enough pixels for you to recognize? ![a pixelated image][pixelated_image] Stand far away and the different blocks of colors, that is, the pixels, start to blend together.

Why are we paying so much attention to pixels? Once you understand the fundamental building block of a digital image, you can perform all kinds of cool operations on an image such as brightening it, rotating it, determining its contents, and more!

How are digital images stored in a computer? Well that depends on the image **format**. But regardless of the format, like anything else that is stored in a computer, a digital image is just a jumble of bits and bytes. To keep things simple, we will first describe **grayscale** images. Grayscale images have colors ranging from black to gray to white. For our purposes, we can think of a grayscale image as a 2D matrix of numbers. Each number describes a pixel with its value being the intensity, or _how much_, of a color the pixel should look like. The **color depth** tells you how many bits make up a single pixel. This means that the **color depth** tells you the number of shades of black, gray, and white a pixel can depict.

For example, a pixel with a color depth of 2 bits can be stored in a computer as 00, 01, 10, or 11. We can choose map these 2 bit patterns to any color we want. ![image of 00 to black, 01 to purple, 10 to blue, and 11 to white][map_of_bits_to_color]

Practically, we would prefer a mapping from bit patterns to colors that makes sense. If we view the bit patterns as binary numbers, $$00_2$$, $$01_2$$, $$10_2$$, and $$11_2$$ as binary numbers, then how about we say that $$00_2$$ represents the **absence of light**, or black, and $$11_2$$ represents the **full intensity of light**, or white. This leaves us with $$01_2$$ and $$10_2$$, which we can think of as the amount of light in a pixel. That would mean $$01_2$$ could be a light black and $$10_2$$ could be a light gray.

<a name='images-as-math-functions'></a>

## Images as 2D Math Functions

Think of a digital image as a 2D mathematical function. A highly pixelated one would be a bunch of tall and short bars. A high resolution image would be smoother and resemble a mathematical curve in a 3D space. Think of a digital image as a 2D math function.

Once you view digital images as 2D math functions, a whole world of interesting operations on images open up to you.

Recall that 0 maps to black and 255 maps to white. Put another way, a pixel is lighter if its intensity value is higher. Let's develop more intuition around this.

{% highlight python %}
> import cv2
> import numpy as np
> img = cv2.imread('./test.jpg')
> gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
> Plot histogram of gray's pixel intensity values
> 
{% endhighlight %}

(Create a custom CSS for Jupyter)

You can see that the image is brighter on the left side than the right side, and the intensity values in the matrix reflect that. (Take average value of left side of matrix and compare with average value of right side of matrix).

<a name='image-filters'></a>

## Image Filters

Photo editing software such as [Adobe Photoshop](http://www.adobe.com/products/photoshop.html) and its free and open source cousin [GIMP (GNU Image Manipulation Program)](https://www.gimp.org/) come replete with a plethora of image effects - blur, sharpen, emboss, and find edges.

<a name='image-classification'></a>

# Image Classification



![Blurred image][blurred_image]
![Sharpened image][sharpened_image]
![Embossed image][embossed_image]
![Edge image][edge_image]

Recall that grayscale digital images can be viewed as 2D matrices, each element representing a single pixel. With this view, we can operate on the pixels, either individually or in groups of various sizes. (We will continue to use grayscale images to learn the basic concepts, and these concepts will generalize well to colored images.) Remember, the pixel value represents the intensity of light in a grayscale image. With that in mind, how would you darken an image? How would you brighten it?

The answer is simple: to darken an image, lower its pixel intensity values, and to brighten it, increase them. Let's try it out. 

(darken an image by subtracting 1 from every pixel)

It appears that the darkening effect is rather weak when only 1 is subtracted per pixel. Let's try subtracting 10 per pixel.

(darken an image by subtracting 10 from every pixel)

#### Further Reading

Here are some (optional) links you may find interesting for further reading:

- [Gauss-Markov theorem](https://en.wikipedia.org/wiki/Gauss%E2%80%93Markov_theorem), learn why the least squares cost function results in the best fit line.