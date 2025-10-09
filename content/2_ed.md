---
title: edge_detector tool
nav: edge_detector tool
gallery: true
---

<br>

The first tool was suggested by Evan Williamson, Digital Infrastructure Librarian at the U of I, prompted by the large number of archeological projects that we were collaborating on, including this example of an [archeological excavation at the local Moscow High School](https://www.spokesman.com/stories/2023/oct/06/ui-archaeology-students-unearth-history-on-grounds/) which unearthed this paleolithic bug juice container and He-Man leg. 

{% include gallery-figure.html img="vra_12.png" alt="Panel from slide show of examples of archeological context photos with plastic bottles, parts of a toy, a shard of glass and a flint." caption="Examples of archeological context photos where we needed to extract the object from it's background" %}

All of these projects were controlled context photographs of the object beside a ruler, possibly a color swatch, with varying backgrounds and lighting setups. The idea was to identify and extract the objects and, since different fellowship collaborators wanted these objects to be reproduced with both white and black backgrounds, we thought providing both of these options as well as a PNG file with a transparent background would be optimal. 

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

<br>

## edge_detector tool code snippet

<br>

- **from pathlib import Path**: handling directory and file paths
- **from rembg import remove, new_session**: third party library accessing ISNET computer vision
- **from PIL import Image**: pillow library for opening, editing and saving project
- **input_folder = Path(‘A’)**: original image file containing object that needs extracting
- **transparent_folder = Path(‘B’)**: extracted object with transparent background (PNG)
- **white_folder = Path(‘C’)**: white background (JPG)
- **black_folder = Path(‘D’)**: black background (JPG)
- **for folder in [transparent_folder, white_folder, black_folder]**
    - **folder.mkdir(exist_ok=True)**: checking that folders exist before processing
- **session = new_session(model_name=”isnet-general-use”)**: engage in new session with model
- **for img_path in input_folder.glob**:
    - **if not img_path.suffix.lower() in [‘.jpg’, ‘.jpeg’, ‘.png’, ‘.tiff’]**:
    - **continue**: skip unsupported image file types in A folder
    - **input_image = Image.open(img_path).convert(“RGB”)**: load image and convert to RGB
...
<br>

Find the full script [here](https://github.com/Scholarly-Projects/edge_detector)_

<br>

The tool implements a neural network called IS-Net, originally developed for a paper titled [“Highly Accurate Dichotomous Image Segmentation”](http://arxiv.org/abs/2203.03041) by [Xuebin Qin](https://github.com/xuebinqin/DIS) and others in 2022. The model executes fine grain, binary foreground/background segmentation and was trained on/for isolating retail objects for online marketplaces. The model is completely open access, requiring the user to open and close sessions within the Python script to use, but not requiring a monetary API key. 

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

{% include gallery-figure.html img="vra_14.png" alt="Side by side comparison of the U2Net vs. isnet-general-use computer vision models, looking at two different objects with visible blurring around the edges of the former." caption="U2Net vs. isnet-general-use model computer vision" %}

There are a few iterations that can be implemented under the greater [rembg](https://github.com/danielgatis/rembg) (remove background) library. At first, I was using the original u2net model, but found that the isnet-general-use model is more accurate and produces finer lines around the object, if a little slower to process.

<br>

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

<br>
