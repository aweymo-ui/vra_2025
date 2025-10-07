---
title: Findings
nav: Findings
gallery: true
---

<br>

{% include gallery-figure.html img="vra_18.png" alt="Card displaying the before and after of an original archeological flint and an expanded version of the extracted image." caption="edge_detector successful applications" %}

Despite the Edge Detection tool working with much more complex materials than the Image Extraction tool, the results are much more accurate. I believe this is due to the model being trained to identify retail objects at close range, with fairly blank backgrounds on newer cameras –  which just so happens to be very close to the same conditions of archeological context photos.

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

{% include gallery-figure.html img="vra_19.png" alt="Card displaying the before and after of two unsuccessful examples -- one where the ruler was not removed from the photo and one where an artifact containing two objects was not fully rendered." caption="edge_detector unsuccessful examples" %}

On the 24 objects I tested with this tool, including some tricky, nearly transparent glass items, the tool only produced three minor inaccuracies: a very slight shadow beside a glass shard, the ruler next to this pencil, possibly due to proximity and the text being lifted from a label you can view on the banner for this presentation. 

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

{% include gallery-figure.html img="vra_20.png" alt="Card displaying the before and after of a successful examples -- where seven images are pulled from the original scan, although there are still minor inaccuracies around the margins of the photographs." caption="image_extractor successful example" %}

While the Image Extraction tool is simply identifying rectangles within an image, the action is complicated with variable margins, paper backing color, overlapping or connected images as well as patterns on the actual scrapbook paper. On a scrapbook with a plain background and fairly straight somewhat evenly spaced photos, it identified and correctly extracted 25 of the 26 photos, although there are still minor inaccuracies around the margins of the photographs -- which is something you can adjust for manually in the parameters section mentioned earlier.

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

{% include gallery-figure.html img="vra_21.png" alt="Card displaying two examples of pages that the tool has difficulty with -- one featuring heavily skewed photographs on backing paper featuring designs and another where there are varying background colors and the edges of photographs are cut off." caption="image_extractor least successful examples" %}

On a scrapbook containing the above complications, the tool only identified and extracted 48 out of the 56 total items. 

<br>

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

<br>

That said, the tool is still certainly a work in progress and you can follow (and suggest) improvements on the GitHub public repository. 

<br>

## About the Author

{% include alert.html text="Andrew Weymouth is the Digital Initiatives Librarian at University of Idaho, primarily focusing on static web design to curate the institution’s special collections and partner with faculty and graduate students on fellowship projects. He has also created digital scholarship projects for the universities of Oregon, Washington and the Tacoma Northwest Room archives, ranging from long form audio public history to architectural databases and network visualizations. He writes about labor, architecture, underrepresented communities and using digital scholarship methods to survey equity in archival collections." color="light" align="center" %}

{% include button.html text="More Workshops from the Author" link="https://aweymo.github.io/base/" color="light" centered="true" %}

<br>

