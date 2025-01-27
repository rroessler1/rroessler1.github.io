---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Human Motion Synthesis with Diffusion Models in Real Environments

{% assign user = "rossroessler" %}
{% assign domain = "gmail.com" %}
{% assign subject = "Human Motion Synthesis Code Request" %}

<div class="button-container">
  <a class="btn" href="/assets/digital-humans-report.pdf" download>Download the Final Report</a>
  <a class="btn" href="mailto:{{ user }}@{{ domain }}?subject={{ subject | uri_escape }}" target="_blank">Request Code Access</a>
</div>

This was a group project for the Digital Humans class at ETH. We extended a method called Diffusion Noise Optimization (DNO) and generate realistic human motions in real-world scenes with multiple, complex-shaped obstacles.

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

Our project was to build on top of the [Diffusion Noise Optimization](https://korrawe.github.io/dno-project/) paper and integrate the diffusion generation with realistic environments.
