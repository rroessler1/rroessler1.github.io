---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# WhereAmI? A Mixed Reality application for Indoor Localization

<div class="button-container">
  <a class="btn" href="/assets/whereami-report.pdf" download>Download the Final Report</a>
  <a class="btn" href="https://github.com/rroessler1/Hierarchical-Localization/tree/arni_changes" target="_blank">See the Code on Github</a>
</div>

This was a group project for the Mixed Reality class at ETH. We built an Augmented Reality for a Magic Leap 2 device that allowed the user to locate their position indoors and navigate in a previously mapped environment.

<div class="video-container">
  <video controls>
    <source src="/assets/whereami-video.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

We used the [Hierarchical-Localization](https://github.com/cvg/Hierarchical-Localization) algorithm on reference data inside one of our campus buildings at ETH from the [LaMAR dataset](https://github.com/microsoft/lamar-benchmark).

My specific contributions were:
* Cleaning and preprocessing the data we needed from the LaMAR dataset.
* Updating the Hierarchical-Localization algorithm to run and make predictions on that data.
* Experimenting with different algorithms and parameters to get the best localization results.

The high level idea was that a user would be indoors wearing the Magic Leap 2 device. The device would capture what they were looking at, send it to a server, and use HLoc to localize the position. The position, transformed to the building coordinate space, would be sent back to the device, where the user could then see where they were on a minimap and navigate through the building.

My job was to "get HLoc working", which was harder than it sounds. HLoc itself worked great out of the box on their example data, and the code was written well. But first, we had terabytes of data from LaMAR, and we didn't understand the different formats or what exactly we could use. We decided to use the HoloLens data, but there were some different transformations necessary to align the RBG images with the depth images. We also later realized that we didn't have much ground truth trajectory data, so we had to filter down our dataset. Then we didn't have enough data, so we also added in some iOS data, which was more sparse, but higher resolution, and helped with predictions.

Once it finally "worked", the predictions were terrible. After debugging some incorrect coordinate transformations, we realized that more data was not always better. We were sending keypoints from the top 40 image matches to COLMAP to predict the user's location, but it seems the final prediction was often including some outliers (despite using RANSAC), as one (or several) coordinates were always off by a lot, despite the 3 best image matches looking very visually similar and accurate. The Z-axis was most often off, so maybe we had some depth data quality issues. We never figured out what the exact problem was, but sending fewer images to COLMAP gave us better predictions. There are more details in the final report.

<figure class="responsive-figure">
  <img src="/assets/user-nav-screenshot.png" alt="User following the path overlaid on the world">
  <figcaption>Real world on the left. What the user sees is on the right, and the white line is the navigation path they're following.</figcaption>
</figure>

In the end, it worked well for the demo day, and was pretty cool! The localization was working well (we don't have exact accuracy numbers, but it generally looked completely correct on the minimap) and then users could navigate within the building.
