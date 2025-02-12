---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Image Superresolution using a CNN

<div class="button-container">
  <a class="btn" href="https://github.com/rroessler1/superresolution" target="_blank">See the Code on Github</a>
</div>

### Abstract

This was one of my favorite class projects, for "Mathematical Foundations of Computer Graphics", to train a CNN to upsample images to 2x resolution.

The nice part is that students were given the recommended model architecture, but no starter code, so I wrote everything from scratch, which turned out to be a very good learning process.

### Results

The model is passed the downsampled image at 240x240 with bilinear interpolation, and it outputs a 2x upsampled version.

The model output is on the left and the original is on the right.

<div class="content-wrapper">
<div class="video-container">
  <figure class="responsive-figure figure-small">
    <img src="/assets/superresolution/model-parrot.png" alt="Model output of a parrot">
    <figcaption>A 10 layer CNN with lr 1e-4. I find it very hard to see any difference.</figcaption>
  </figure>
  <figure class="responsive-figure figure-small">
    <img src="/assets/superresolution/gt-parrot.png" alt="Ground truth image of parrot">
    <figcaption>Ground Truth</figcaption>
  </figure>
  </div>
</div>
<br>
<div class="content-wrapper">
<div class="video-container">
  <figure class="responsive-figure figure-small">
    <img src="/assets/superresolution/model-castle.png" alt="Model output of a parrot">
    <figcaption>Again, a 10 layer CNN with lr 1e-4. You can see a bit of detail is lost in the middle of the castle, and on the stone wall at the bottom.</figcaption>
  </figure>
  <figure class="responsive-figure figure-small">
    <img src="/assets/superresolution/gt-castle.png" alt="Ground truth image of parrot">
    <figcaption>Ground Truth</figcaption>
  </figure>
  </div>
</div>
<br/>
<div class="content-wrapper">
<div class="video-container">
  <figure class="responsive-figure figure-small">
    <img src="/assets/superresolution/residual-model-greece.png" alt="Model output of a parrot">
    <figcaption>CNN with residual connections. This does even better.</figcaption>
  </figure>
  <figure class="responsive-figure figure-small">
    <img src="/assets/superresolution/gt-greece.png" alt="Ground truth image of parrot">
    <figcaption>Ground Truth</figcaption>
  </figure>
  </div>
</div>
