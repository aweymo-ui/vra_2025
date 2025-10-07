---
title: image_extractor tool
nav: image_extractor tool
gallery: true
---

<br>


{% include gallery-figure.html img="vra_23.jpeg" alt="Page containing seven archival photos of people in outdoor wear on a trip through the woods." caption="Page from the Tacoma Mountaineers 1911 scrapbook, courtesy Tacoma Northwest Room." %}

The second tool was prompted by an archivist digitizing scrapbooks with our Zeutschel overhead scanner and wondering if we could batch extract individual photographs from the full page images. The image processing here is done using [Scikit-Image](https://scikit-image.org/), a collection of algorithms that can be implemented in different ways depending on the type of content you need to mask and extract. 

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

<br>

## image_extractor tool code snippet

<br>

- **from skimage import io, color, filters, measure, morphology, util**: image reading, gray scale conversion for preprocessing, region analysis and labeling
- **from skimage.morphology import binary_closing, remove_small_objects**: “closing” object edges and removing noise
- **from scipy.ndimage import binary_fill_holes**: “fill” interior holes in identified objects
- **import numpy as np**: replace Python loops with array operations for speed
- **import os**: file and directory operations and path manipulation
- **from pathlib import Path**: cleaning syntax for path manipulations
- **import time**: performance logging
- **from PIL import Image**: converting to final image format
- **Parameters**:
    - **min_long_edge** = 300
    - **max_long_edge** = 1000
    - **max_photos** = 10max_photos
<br>

...

<br>

_Find the full script [here](https://github.com/Scholarly-Projects/image_extraction)_

<br>

The design of this code is a little different than the previous tool, with simple, `human readable parameters` you can adjust depending on the general size of the photos in their collection, the number of photos within an image and the amount of margin around those images. The code identifies each photograph within the image placed in the A folder and generates a new derivative in the B folder where they are given sequential file names based on the parent item. The code is currently set up to give sequential files names by the position of each photograph in a clockwise rotation, but this can be configured to whatever you find intuitive.

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

<br>
