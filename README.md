# Image_Steganography

# Steganography: Hiding an image inside another

## Usage

Create a `virtualenv` and install the requirements:

```
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
```

Then, merge and unmerge your files with:

```
python steganography.py merge --image1=res/image1.jpg --image2=res/image2.jpg --output=res/output.png
python steganography.py unmerge --image=res/output.png --output=res/output2.png
```

To use the **Steganography** class in your **Python** code, you will need to use the **Image** module from the **Pillow** library, for example:

```python
from PIL import Image

merged_image = Steganography().merge(Image.open(image1), Image.open(image2))
merged_image.save(output)
```

**Note**: the **output image** from the **merge operation** and the **input image** for the **unmerge operation** must be in **PNG** format.

## Steganography

Let’s understand what is steganography, digital images, pixels, and color models.

### What is steganography?

> [Steganography](https://en.wikipedia.org/wiki/Steganography) is the practice of concealing a file, message, image, or video within another file, message, image, or video.

### What is the advantage of steganography over cryptography?
> The advantage of steganography over [cryptography](https://en.wikipedia.org/wiki/Cryptography) alone is that the intended secret message does not attract attention to itself as an object of scrutiny. Plainly visible encrypted messages, no matter how unbreakable they are, arouse interest and may in themselves be incriminating in countries in which [encryption](https://en.wikipedia.org/wiki/Encryption) is illegal.

In other words, steganography is more discreet than cryptography when we want to send a secret information. On the other hand, the hidden message is easier to extract.

### What is a digital image?

Ok, now that we know the basics of steganography, let’s learn some simple image processing concepts.

Before understanding how can we hide an image inside another, we need to understand what a digital image is.

We can describe a **digital image** as a finite set of digital values, called pixels. Pixels are the smallest individual element of an image, holding values that represent the brightness of a given color at any specific point. So we can think of an image as a matrix (or a two-dimensional array) of pixels which contains a fixed number of rows and columns.


When using the “**digital image**” term here, we are referencing to the “**raster graphics**”, which are basically a dot matrix data structure, representing a grid of pixels, which in turn can be stored in image files with varying formats. You can read more about [digital images](https://en.wikipedia.org/wiki/Digital_image), [raster graphics](https://en.wikipedia.org/wiki/Raster_graphics), and [bitmaps](https://en.wikipedia.org/wiki/Bitmap) at the [Wikipedia](https://en.wikipedia.org/wiki/Main_Page) website.

### Pixel concept and color models

As already mentioned, pixels are the smallest individual element of an image. So, each pixel is a sample of an original image. It means, more samples provide more accurate representations of the original. The [intensity](https://en.wikipedia.org/wiki/Intensity_(physics)) of each pixel is variable. In color imaging systems, a color is typically represented by three or four component intensities such as [red, green, and blue](https://en.wikipedia.org/wiki/RGB_color_model), or [cyan, magenta, yellow, and black](https://en.wikipedia.org/wiki/CMYK_color_model).

Here, we will work with the [RGB color model](https://en.wikipedia.org/wiki/RGB_color_model). As you can imagine, the RGB color model has 3 channels, red, green and blue.
> The **RGB color model** is an additive [color model](https://en.wikipedia.org/wiki/Color_model) in which red, green and blue light are added together in various ways to reproduce a broad array of colors. The name of the model comes from the initials of the three additive primary colors, red, green, and blue. The main purpose of the RGB color model is for the sensing, representation and display of images in electronic systems, such as televisions and computers, though it has also been used in conventional [photography](https://en.wikipedia.org/wiki/Photography).

**You can check out the result in the following image**:

The left upper image is the image that will hide the right upper image. The left lower image is the two images merged and the right lower image is the extracted (unmerged) image.

![](https://cdn-images-1.medium.com/max/2000/1*4paRMea_BGeNpJ2VzFGCoA.png)

As you can see in the image above, we lost some image quality in the process, but this does not interfere with image comprehension.Steganography
