---
title: Introduction
nav: Introduction
gallery: true
---

<br>

My name is Andrew Weymouth and I am the Digital Initiatives Librarian for University of Idaho. Today I’ll be discussing two practical applications implementing computer vision that can facilitate batch processing large numbers of digital visual resources. 

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

The team I’m a part of in the [Center for Digital Inquiry and Learning](https://cdil.lib.uidaho.edu/) consists of three other people and a small group of student workers, collaborating with the five members of our [Special Collections](https://www.lib.uidaho.edu/special-collections/) department to create and maintain the [150 digital collections](https://www.lib.uidaho.edu/digital/) on our main institutional repository as well as the many other, more customized fellowship projects. I also develop digital tools and workflows to enhance transcription, optical character recognition for archival documents, tagging, and image processing, in order to make the university’s audio, text, and visual resources more discoverable for researchers.

{% include gallery-figure.html img="vra_01.gif" alt="Screen capture of a patron scrolling through the U of I digital collections, going from the main browse page to a collection and then an item level resource." caption="The U of I Digital Collections, moving from the main browse page to a collection and down to the item level" %}

Both of the tools I’ll be speaking about today have their origins in finding practical solutions to repetitive, digital work that comes after the hands-on arranging, research, cataloguing and description work in the archive. Considering I work with technology quite a bit, I would broadly self identify as critical towards AI applications to cultural heritage work, which I think you’ll find reflective in the coding approach, where sets of algorithms and neural networks are implemented on guardrails within a programmatic workflow, to make sure results are scalable and reproducible.

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

## Definitions

<br>

It might be helpful to begin with some definitions of what resources these tools implement. Both tools are written in `Python`, a general purpose, readable programming language, and they are hosted in `GitHub`, a static web platform for hosting software development projects which allows these tools to be implemented in controlled environments and avoid software versioning complications.

{% include gallery-figure.html img="vra_07.png" alt="A visual analogy of the definitions, where large language models are within a sphere of neural networks within a sphere of machine learning, that is within a sphere of algorithms. The first three are yellow, indicating they are all trained, and the outer ring of algorithms is green, indicating it is not necessarily trained. There is a box of yellow and green spheres representing Python libraries and three green dots representing untrained, deterministic path utilities." width="75%" caption="Representation of algorithmic shared characteristics. A large language model is necessarily a neural network but a neural network is not necessarily a large language model, a neural network is necessarily machine learning but machine learning... and so on." %}

The first tool I’ll discuss implements an artificial intelligence resource. At the moment, most of us would associate AI with `large language models` that are trained on text and reproduce human language styled output. In contrast, this tool is a more general `neural network`, computer architecture in which processors are interconnected in a manner suggestive of the human brain. The second tool utilizes `machine learning` which is a computational method that enables a computer to learn to perform tasks by analyzing a large dataset without being explicitly programmed, in that case to focus on pattern recognition. All of the other resources these tools utilize are `Python libraries`, wrappers that distribute any of the above models as well as `path utilities`, which are untrained, deterministic functions.

<div class="symbol-container">
    <p class="symbol">&#10042;</p>
</div>

<br>