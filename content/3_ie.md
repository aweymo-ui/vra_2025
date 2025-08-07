---
title: image_extractor tool
nav: image_extractor tool
gallery: true
---

<br>


{% include gallery-figure.html img="vra_23.jpeg" alt="Page containing seven archival photos of people in outdoor wear on a trip through the woods." caption="Page from the Tacoma Mountaineers 1911 scrapbook, courtesy Tacoma Northwest Room." %}

The second tool was prompted by an archivist digitizing scrapbooks with our Zeutschel overhead scanner and wondering if we could batch extract individual photographs from the full page images. The image processing here is done using [Scikit-Image](https://scikit-image.org/), a collection of algorithms that can be implemented in different ways depending on the type of content you need to mask and extract. 

{% include gallery-figure.html img="vra_05.jpg" alt="Screenshot of Python code, including initial imports, customizable parameters and image preprocessing." caption="image_extractor Python code, including initial imports, customizable parameters and image preprocessing" %}

In this script, I am using Scikit’s io and color to preprocess images, making them easier to identify. Then this uses their morphology, closing and remove_small_objects to reduce noise, identify the correct shapes within the image to extract and then fill in the holes within the objects if anything is missing with the original visual resource data. 

The design of this code is a little different than the previous tool, with simple, human readable parameters you can adjust depending on the general size of the photos in their collection, the number of photos within an image and the amount of margin they would like their photos to have around the photos.

<br>
