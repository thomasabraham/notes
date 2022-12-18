---
layout: post
title: Imagemagick Cheat Sheet
date: 2022-07-30
categories: cheat-sheets
---

## Remove metadata from images
{% highlight shell %}
convert <input.jpg> -strip <output.jpg>
{% endhighlight %}

Removes all the image metadata from `input.jpg` and stores the result in `output.jpg`.

## Resize an image maintaining aspect ratio
{% highlight shell %}
convert <input.jpg> -resize <width>x<height> <output.jpg>
{% endhighlight %}

Resizes the `input.jpg` to fit in the specified `width` and `height`, and store
the results in `output.jpg`. The aspect ratio is maintained. Also, it is
possible to omit either the width or the height. See [Imagemagick
usage][image-magick-resize] for more details, but you might want to replace
`magick` command with `convert`.

## Convert an image to a PDF file
{% highlight shell %}
convert <input1.jpg> [<input2.jpg>] [-page a4] <output.pdf>
{% endhighlight %}

Create a pdf file named `output.pdf`, with each page containing one of the input
images in the given order. The optional `-page a4` ensures that each page is of
A4 size and images are scaled, maintaining aspect ratio to fit the pages. The
`-gravity center` option can also be used, but if might not work correctly if
the image won't fit in a single page; in this case, resize the image first.

## Join some PDF files
{% highlight shell %}
convert <input1.pdf> [<input2.pdf>] <output.pdf>
{% endhighlight %}

Creates a single PDF file, `output.pdf`, combining the given input files. This
can also be done using the `pdfunite` command as follows.

{% highlight shell %}
pdfunite <input1.pdf> [<input2.pdf>] <output.pdf>
{% endhighlight %}

[image-magick-resize]: https://imagemagick.org/Usage/resize/#resize
