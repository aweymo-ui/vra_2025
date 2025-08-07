---
title: edge_detector tool
nav: edge_detector tool
gallery: true
---

<br>

The first tool was suggested by Evan Williamson, Digital Infrastructure Librarian at the U of I, prompted by the large number of archeological projects that we were collaborating on, including this example of an [archeological excavation at the local Moscow High School](https://www.spokesman.com/stories/2023/oct/06/ui-archaeology-students-unearth-history-on-grounds/) which unearthed this paleolithic bug juice container and He-Man leg. 

{% include gallery-figure.html img="vra_12.png" alt="Panel from slide show of examples of archeological context photos with plastic bottles, parts of a toy, a shard of glass and a flint." caption="Examples of archeological context photos where we needed to extract the object from it's background" %}

All of these projects were controlled context photographs of the object beside a ruler, possibly a color swatch, with varying backgrounds and lighting setups. The idea was to identify and extract the objects and, since different fellowship collaborators wanted these objects to be reproduced with both white and black backgrounds, we thought providing both of these options as well as a PNG file with a transparent background would work best. 

{% include gallery-figure.html img="vra_04.png" alt="Screenshot of Visual Studio Code interface of Python Script." caption="edge_detector Python script with explanation of import functions" %}

The tool implements a neural network called IS-Net, originally developed for a paper titled [“Highly Accurate Dichotomous Image Segmentation”](http://arxiv.org/abs/2203.03041) by [Xuebin Qin](https://github.com/xuebinqin/DIS) and others in 2022. The model executes fine grain, binary foreground/background segmentation and it is often used for isolating retail objects for online marketplaces. The model is completely open access, requiring the user to open and close sessions within the Python script to use, but not requiring a monetary API key. 

{% include gallery-figure.html img="vra_14.png" alt="Side by side comparison of the U2Net vs. isnet-general-use computer vision models, looking at two different objects with visible blurring around the edges of the former." caption="U2Net vs. isnet-general-use model computer vision" %}

There are a few iterations that can be implemented under the greater [rembg](https://github.com/danielgatis/rembg) (remove background) library. At first, I was using the original u2net model, but found that the isnet-general-use model is more accurate and produces finer lines around the object, if a little slower to process.

{% include gallery-figure.html img="vra_03.png" alt="Screenshot of the setup.md file in Visual Studio Code, guiding users on how to use this tool after cloning from GitHub." caption="Beginning of setup.md guide and folder structure on the left" %}

In both tools you’ll notice I have a fairly `Python for Dummies` approach to structure, with original images being dropped into folder A, transparent backed PNGs into B, white backgrounds into C and black into D. After cloning this repository in GitHub, you can just follow the steps outlined in the setup.md file for either Mac or Windows users to use these scripts. 

<br>