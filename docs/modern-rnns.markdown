---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Linear Language Models and their Memory Limitations

<div class="center-text">
  <figcaption>
    Team: Claudiu Craciun, Ross Roessler, Victor Zarzu
  </figcaption>
  <figcaption>
    Supervisor: Imanol Schlag
  </figcaption>
</div>

<div class="button-container">
  <a class="btn" href="/assets/modern-rnns/linear_language_models_poster.pdf" download>Download the Final Poster</a>
  <a class="btn" href="https://github.com/swiss-ai/modern_rnns" target="_blank">See the Code on Github</a>
</div>

### Abstract

Transformers (Vaswani et al.) and their instances (e.g., GPT) have shown strong performance using self-attention and masked attention. However, their quadratic time complexity limits generalization over long sequences. We evaluate the associative memory capacity of sequence decoders with different internal mechanisms, replacing standard attention with linear and recurrent layers, inspired by RNNs.

This research project was undertaken for the class "AI Center Projects in Machine Learning Research" at ETH.

### Implementation

We implemented six architectures: LSTM, quasi-LSTM, LRU, Linear Transformer, GPT, DeltaNet, and Mamba, and replaced the standard self-attention layer of a generic decoder with each of these architectures.

We implemented several synthetic datasets, including:

**Bit Parity**
```
# Returns a 1 if there have been an odd number of ones so far
Input:  0011010
Output: 0010011
```

**Dyck**
```
# Returns a 1 if the parenthesis are completely balanced
Input:  {[]()}[]()
Output: 0000010101
```

### My Contributions

We all contributed equally with implementation of different models, datasets, and debugging when the models were not learning.

### Results

This was an exploratory research project to understand trends and limitations. Some interesting findings are noted below.

<div class="content-wrapper">
<div class="video-container">
  <figure class="responsive-figure figure-small">
    <img src="/assets/modern-rnns/bp_ones_lru_vs_qlstm_1616vs3232_train_loss.png" alt="Bit parity training loss of LRU vs QLSTM">
  </figure>
  <figure class="responsive-figure figure-small">
    <img src="/assets/modern-rnns/bp_ones_lru_vs_qlstm_1616vs3232_eval_accuracy.png" alt="Bit parity evaluation accuracy of LRU vs QLSTM">
  </figure>
  </div>
    <figcaption>We compare training on Bit Parity sequences of length 16 and 32 with exactly 12 ones, evaluated on sequences 50% longer.  Certain models such as LRU overfit when training on a high percentage of ones (Left) and do poorly when evaluated on longer sequences (Right, light blue). This does not occur when trained on longer sequences with a lower percentage of ones (Right, dark blue).  Other models such as QLSTM (purple) do not exhibit this behavior.</figcaption>
</div>
<br>
<div class="content-wrapper">
<div class="video-container">
  <figure class="responsive-figure figure-small">
    <img src="/assets/modern-rnns/dyck_recall2.png" alt="Dyck model performance compared to evaluation sequence length">
    <figcaption>On Dyck, all models do worse the longer the evaluation sequence is.</figcaption>
  </figure>
  <figure class="responsive-figure figure-small">
    <img src="/assets/modern-rnns/dyck_3232,4848_recall.png" alt="Dyck recall relative to number of steps trained">
      <figcaption>For Dyck, we notice that one subset of models do worse the longer they are trained, while others do not.</figcaption>
  </figure>
  </div>
</div>

### Future Work

We only had 2 months to work on this project, which was not enough time. In the future we hope to investigate:

* Performance on MQAR (Multiple Query Associative Retrieval) dataset - this is a more interesting task. We implemented it, but our models did not learn well and we were not able to discover why not.
* Explore the limited-ones Bit Parity task more to understand relative benefits and limitations of the different models.