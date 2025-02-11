---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Human Motion Synthesis with Diffusion Models in Real Environments

<div class="center-text">
  Team: Öykü Irmak Hatipoğlu, Ross Roessler, Bingjie Xue, Kai Zhang
</div>

{% assign user = "rossroessler" %}
{% assign domain = "gmail.com" %}
{% assign subject = "Human Motion Synthesis Code Request" %}

<div class="button-container">
  <a class="btn" href="/assets/digital-humans-report.pdf" download>Download the Final Report</a>
  <a class="btn" href="mailto:{{ user }}@{{ domain }}?subject={{ subject | uri_escape }}" target="_blank">Request Code Access</a>
</div>

<div class="content-wrapper">
<div class="video-container">
    <figure>
    <video class="video-small" controls>
        <source src="/assets/person-jumping-forward.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <figcaption>"A person jumping forward."</figcaption>
    </figure>
    <figure>
    <video class="video-small" controls>
        <source src="/assets/walking-while-kicking.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <figcaption>"A person walking forward while kicking."</figcaption>
    </figure>
</div>
</div>

### Abstract

This was a group project for the Digital Humans class at ETH. We extended a method called Diffusion Noise Optimization (DNO) and generate realistic human motions in real-world scenes with multiple, complex-shaped obstacles. Our project was to build on top of the [Diffusion Noise Optimization](https://korrawe.github.io/dno-project/) paper and integrate the diffusion generation with realistic environments.

### My Contributions

* All the work to get the model initially running and training against a Signed Distance Function representing an environment
* Integrating with the real world scans
* Creating an automated pipeline, enabling bulk running of different environments and configurations
* Implementing evaluation metrics
* The ablation study

### Results

* Implemented three different SDFs and tested on multiple scenes
* Able to reach the goal 94% of the time with a 20% increase in foot skating ratio compared to DNO
* Saw an average 20% loss in semantic accuracy preservation compared to DNO
  * This is expected, as the obstacles were more complicated than in DNO, and there's a tradeoff between preserving accuracy and avoiding obstacles
  * Accurately preserved semantic content for all the tested behaviors: Walking, Crawling, Jumping, and Walking with Raised Hands

#### Example Results

<div class="content-wrapper">
<div class="video-container">
  <figure class="responsive-figure figure-small">
    <img src="/assets/walking_complex_scene.png" alt="Outline of ground truth locations within the building">
    <figcaption>"Walking forward" in a more complicated environment</figcaption>
  </figure>
  <figure class="responsive-figure figure-small">
    <img src="/assets/jumping_complex_scene.png" alt="Outline of ground truth locations within the building">
    <figcaption>"Jumping forward" in a more complicated environment</figcaption>
  </figure>
  </div>
</div>

<br>

<small>\*Note: The code is private is because we were given early code access and couldn't fork the actual repo. I don't want to publish it publicly unforked and potentially cause any confusion or not give proper credit. The now-public original DNO code can be found [here](https://github.com/korrawe/Diffusion-Noise-Optimization). I am happy to give access to my repo if you are curious to evaluate my own personal work.</small>