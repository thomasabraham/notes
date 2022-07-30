#+title: Imagemagick Cheat Sheet
#+subtitle: Some imagemagick commands that I often use
#+description: This is a set of imagemagick commands that comes handy very often
#+date: 2022-07-30
#+keywords: Imagemagick, convert
#+html_link_home: ./
#+html_link_up: ./
#+SETUPFILE: org-templates/level-0.org

* Remove metadata from images
#+BEGIN_SRC bash
convert <input.jpg> -strip <output.jpg>
#+END_SRC
Removes all the image metadata from ~input.jpg~ and stores the result in ~output.jpg~.
* Resize an image maintaining aspect ratio
#+BEGIN_SRC bash
convert <input.jpg> -resize <width>x<height> <output.jpg>
#+END_SRC
Resizes the ~input.jpg~ to fit in the specified ~width~ and ~height~, and store
the results in ~output.jpg~. The aspect ratio is maintained. Also, it is
possible to omit either the width or the height. See
[[https://imagemagick.org/Usage/resize/#resize]] for more details, but you might
want to replace ~magick~ command with ~convert~.

* Convert an image to a PDF file
#+BEGIN_SRC bash
convert <input1.jpg> [<input2.jpg>] [-page a4] <output.pdf>
#+END_SRC
Create a pdf file named ~output.pdf~, with each page containing one of the input
images in the given order. The optional ~-page a4~ ensures that each page is of
A4 size and images are scaled, maintaining aspect ratio to fit the pages. The
~-gravity center~ option can also be used, but if might not work correctly if
the image won't fit in a single page; in this case, resize the image first.

* Join some PDF files
#+BEGIN_SRC bash
convert <input1.pdf> [<input2.pdf>] <output.pdf>
#+END_SRC
Creates a single PDF file, ~output.pdf~, combining the given input files. This
can also be done using the ~pdfunite~ command as follows.

#+BEGIN_SRC bash
pdfunite <input1.pdf> [<input2.pdf>] <output.pdf>
#+END_SRC
