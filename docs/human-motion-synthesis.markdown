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

### Analysis

I was the primary contributer on this project. The main challenge was that the code we were given was an early version and didn't work out of the box. It was a lot of software engineering work to actually get it running and integrated with representations (SDFs, etc.) of real world scenes. The DNO model was built on top of [Human MDM](https://guytevet.github.io/mdm-page/), and we had some interesting issues such as, the generated motion would only ever move "forward". We had to change the scene orientation relative to the diffusion model's axes so that the human would move towards the area we wanted it to. It also performed unexpectedly poorly in our experiments for motion other than "walking forward", though we eventually got crawling, jumping, and a few other motions to work.

Another very important learning was to implement evaluation metrics and an automated running pipeline early. For a while, we were experimenting with various scene representations and hyperparameters, but only evaluating by manually inspecting the output videos. Once we had an automated pipeline and metrics, it was much easier to understand which methods were actually performing better, and they weren't what we expected. Well, in the end, simple was better, maybe that should have been expected.

\*Note: The code is private is because we were given early code access and couldn't fork the actual repo. I don't want to publish it publicly unforked and potentially cause any confusion or not give proper credit. The now-public original DNO code can be found [here](https://github.com/korrawe/Diffusion-Noise-Optimization). I am happy to give access to my repo if you are curious to evaluate my own personal work.
