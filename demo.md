---
layout: default
title: Resumable File Upload Demo
comments: true
---

## {{ page.title }}

This demo is a proof of concept for resumable file uploads built using the [tus-js-client](https://github.com/tus/tus-js-client). 

It sends your files
to a [tusd](https://github.com/tus/tusd) server written in Go, that we
deployed via [infra-tusd](https://github.com/tus/infra-tusd).

### Instructions

 1. Select a large file.
 2. Watch it upload for a bit, then close this tab before it finishes.
 3. Come back to the tab, select the same file again, the upload should resume where it left off.

<p class="alert hidden" id="support-alert">
  <b>Warning!</b> Your browser does not seem to support the features necessary to run this demo. The buttons below may work but probably will fail silently.
</p>
<noscript>
  <p class="alert">
    <b>Warning!</b> Either you disabled JavaScript or your browser does not support it. However, this demo requires JavaScript. The buttons below  will fail silently unless you activate it, at least for this page.
  </p>
</noscript>

<input type="file">
<label>
  <input type="checkbox" id="resume">
  Perform full upload (even if we could resume)
</label>

<div class="row">
  <div class="nine columns">
    <div class="progress">
      <div class="progress-bar progress-bar-striped" style="width: 0%;"></div>
    </div>
  </div>
  <div class="three columns">
    <button class="u-full-width" id="stop-btn" disabled> abort upload</button>
  </div>
</div>

<hr />
<h3>Uploads</h3>
<p class="upload-list">
  Succesful uploads will be listed here. Try one!<br>
</p>

---------------------------------------

### Compatibility

The [tus-js-client](https://github.com/tus/tus-js-client) used in
this demo has been [automatically tested](https://travis-ci.org/tus/tus-js-client) and works with the following browsers:

<div id="browser-matrix">
  <center>Loading...</center>
</div>

Going forward, all relevant browsers will be supported with as many features
as possible. All browsers will be able to perform at least simple multipart
uploads.

Using the `X-HTTP-Method-Override` header, it's possible to run tus
even on platforms that won't let you do `PUT` and `PATCH` requests.
