---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# WhereAmI? A Mixed Reality application for Indoor Localization

<div class="center-text">
  Team: Árni Bjarnsteinsson, Fabian Blatter, Matěj Mrázek, Ross Roessler
</div>

<div class="button-container">
  <a class="btn" href="/assets/whereami-report.pdf" download>Download the Final Report</a>
  <a class="btn" href="https://github.com/rroessler1/Hierarchical-Localization/tree/arni_changes" target="_blank">See the Code on Github</a>
</div>

<div class="video-container">
  <video controls>
    <source src="/assets/whereami-video.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

### Abstract

This was a group project for the Mixed Reality class at ETH. We built an Augmented Reality for a Magic Leap 2 device that allowed the user to locate their position indoors and navigate in a previously mapped environment. We used the [Hierarchical-Localization](https://github.com/cvg/Hierarchical-Localization) algorithm on reference data inside one of our campus buildings at ETH from the [LaMAR dataset](https://github.com/microsoft/lamar-benchmark).

### My Contributions

* Cleaning and preprocessing the data we needed from the LaMAR dataset.
* Updating the Hierarchical-Localization algorithm to run and make predictions on that data.
* Experimenting with different algorithms and parameters to get the best localization results.

### Analysis

#### Challenges

* Terabytes of data requiring different transformations - we weren't even sure at first which data we could use
* Relatively sparse ground truth global trajectory data
* Poor predictions from COLMAP

#### Learnings

* Sending fewer images to COLMAP actually worked better
* Integrating different ground truth data sources helped significantly
* Visualization tools for debugging were extremely helpful

<figure class="responsive-figure">
  <img src="/assets/hg-map.png" alt="Outline of ground truth locations within the building">
  <figcaption>My teammate Árni built the visualization on the bottom right, which showed the ground truth locations and the prediction location. It was super helpful in debugging.</figcaption>
</figure>
<br>
<br>
<figure class="responsive-figure">
  <img src="/assets/user-nav-screenshot2.png" alt="User following the path overlaid on the world">
  <figcaption>Real world on the left. What the user sees is on the right, and the white line is the navigation path they're following.</figcaption>
</figure>
