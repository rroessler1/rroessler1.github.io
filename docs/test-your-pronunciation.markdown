---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Test Your Pronunciation: Anki Plugin for Pronunciation Feedback

<div class="button-container">
  <a class="btn" href="https://github.com/rroessler1/speech-to-text" target="_blank">See the Code on Github</a>
  <a class="btn" href="https://ankiweb.net/shared/info/673333980" target="_blank">Download the Anki Plugin here</a>
</div>

### Abstract

I wrote this plugin to help myself study Chinese, and then improved and released it so anyone could use it for any language. Many people study languages with [Anki](https://ankiweb.net/decks), a popular flashcard app. This plugin records you speaking the content on your flashcard, sends it to a cloud speech-to-text service, then diffs with the flashcard. It gives the user feedback whether the computer could understand what they were saying.

It currently (Jan 2025) has over 1000 downloads and is ranked top 15% of all Anki plugins.

### Results

* Over 1000 downloads, only positive feedback
* Supports multiple Speech-to-Text cloud providers and all languages
* Includes a bit of custom handling of punctuation and languages without spaces to give the user more helpful feedback on which parts they got correct versus not
