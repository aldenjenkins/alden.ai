---
layout: none
permalink: /tutorial/anomaly_detection_gaussian
---
<html>
<head><meta charset="utf-8" />

<title>anomaly_detection_gaussian_demo</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Anomaly-Detection-Using-Gaussian-Distribution">Anomaly Detection Using Gaussian Distribution<a class="anchor-link" href="#Anomaly-Detection-Using-Gaussian-Distribution">&#182;</a></h1><p><em>Source: 🤖<a href="https://github.com/trekhleb/homemade-machine-learning">Homemade Machine Learning</a> repository</em></p>
<blockquote><p>☝Before moving on with this demo you might want to take a look at:</p>
<ul>
<li>📗<a href="https://github.com/trekhleb/homemade-machine-learning/tree/master/homemade/anomaly_detection">Math behind the Anomaly Detection</a></li>
<li>⚙️<a href="https://github.com/trekhleb/homemade-machine-learning/blob/master/homemade/anomaly_detection/gaussian_anomaly_detection.py">Gaussian Anomaly Detection Source Code</a></li>
</ul>
</blockquote>
<p><strong>Anomaly detection</strong> (also <strong>outlier detection</strong>) is the identification of rare items, events or observations which raise suspicions by differing significantly from the majority of the data.</p>
<p>The <strong>normal</strong> (or <strong>Gaussian</strong>) distribution is a very common continuous probability distribution. Normal distributions are important in statistics and are often used in the natural and social sciences to represent real-valued random variables whose distributions are not known. A random variable with a Gaussian distribution is said to be normally distributed and is called a normal deviate.</p>
<blockquote><p><strong>Demo Project:</strong> In this demo we will build a model that will find anomalies in server operational parameters such as <code>Latency</code> and <code>Throughput</code>.</p>
</blockquote>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># To make debugging of logistic_regression module easier we enable imported modules autoreloading feature.</span>
<span class="c1"># By doing this you may change the code of logistic_regression library and all these changes will be available here.</span>
<span class="o">%</span><span class="k">load_ext</span> autoreload
<span class="o">%</span><span class="k">autoreload</span> 2

<span class="c1"># Add project root folder to module loading paths.</span>
<span class="kn">import</span> <span class="nn">sys</span>
<span class="n">sys</span><span class="o">.</span><span class="n">path</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s1">&#39;../..&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Import-Dependencies">Import Dependencies<a class="anchor-link" href="#Import-Dependencies">&#182;</a></h3><ul>
<li><a href="https://pandas.pydata.org/">pandas</a> - library that we will use for loading and displaying the data in a table</li>
<li><a href="http://www.numpy.org/">numpy</a> - library that we will use for linear algebra operations</li>
<li><a href="https://matplotlib.org/">matplotlib</a> - library that we will use for plotting the data</li>
<li><a href="https://github.com/trekhleb/homemade-machine-learning/blob/master/homemade/anomaly_detection/gaussian_anomaly_detection.py">anomaly_detection</a> - custom implementation of anomaly detection using Gaussian distribution.</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Import 3rd party dependencies.</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>

<span class="c1"># Import custom Gaussian anomaly detection implementation.</span>
<span class="kn">from</span> <span class="nn">homemade.anomaly_detection</span> <span class="k">import</span> <span class="n">GaussianAnomalyDetection</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Load-the-Data">Load the Data<a class="anchor-link" href="#Load-the-Data">&#182;</a></h3><p>In this demo we will use the dataset with server operational parameters such as <code>Latency</code> and <code>Throughput</code> and will try to find anomalies in them.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Load the data.</span>
<span class="n">pd_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;../../data/server-operational-params.csv&#39;</span><span class="p">)</span>

<span class="c1"># Print the data table.</span>
<span class="n">pd_data</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[5]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Latency (ms)</th>
      <th>Throughput (mb/s)</th>
      <th>Anomaly</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>13.046815</td>
      <td>14.741152</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>13.408520</td>
      <td>13.763270</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>14.195915</td>
      <td>15.853181</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>14.914701</td>
      <td>16.174260</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>13.576700</td>
      <td>14.042849</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>13.922403</td>
      <td>13.406469</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>12.822132</td>
      <td>14.223188</td>
      <td>0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>15.676366</td>
      <td>15.891691</td>
      <td>0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>16.162875</td>
      <td>16.202998</td>
      <td>0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>12.666451</td>
      <td>14.899084</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Print histograms for each feature to see how they vary.</span>
<span class="n">histohrams</span> <span class="o">=</span> <span class="n">pd_data</span><span class="p">[[</span><span class="s1">&#39;Latency (ms)&#39;</span><span class="p">,</span> <span class="s1">&#39;Throughput (mb/s)&#39;</span><span class="p">]]</span><span class="o">.</span><span class="n">hist</span><span class="p">(</span><span class="n">grid</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">4</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Plot-the-Data">Plot the Data<a class="anchor-link" href="#Plot-the-Data">&#182;</a></h3><p>Let's plot <code>Throughput(Latency)</code> dependency and see if the distribution is similar to Gaussian one.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Extract first two column from the dataset.</span>
<span class="n">data</span> <span class="o">=</span> <span class="n">pd_data</span><span class="p">[[</span><span class="s1">&#39;Latency (ms)&#39;</span><span class="p">,</span> <span class="s1">&#39;Throughput (mb/s)&#39;</span><span class="p">]]</span><span class="o">.</span><span class="n">values</span>

<span class="c1"># Plot the data.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">data</span><span class="p">[:,</span> <span class="mi">0</span><span class="p">],</span> <span class="n">data</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">],</span> <span class="n">alpha</span><span class="o">=</span><span class="mf">0.3</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Latency (ms)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Throughput (mb/s)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Server Operational Params&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Find-Anomalies-Using-Gaussian-Distribution">Find Anomalies Using Gaussian Distribution<a class="anchor-link" href="#Find-Anomalies-Using-Gaussian-Distribution">&#182;</a></h3><p>Let's try to use our custom anomaly detection implementation using Gaussian distribution.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Init Gaussian anomaly instance.</span>
<span class="n">gaussian_anomaly</span> <span class="o">=</span> <span class="n">GaussianAnomalyDetection</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>

<span class="c1"># Let&#39;s see Gaussian estimation parameters.</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;mu&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">gaussian_anomaly</span><span class="o">.</span><span class="n">mu_param</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">&#39;</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;sigma^2&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">gaussian_anomaly</span><span class="o">.</span><span class="n">sigma_squared</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>mu
[14.11222578 14.99771051]


sigma^2
[1.83263141 1.70974533]
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Visualize-the-Fit">Visualize the Fit<a class="anchor-link" href="#Visualize-the-Fit">&#182;</a></h3><p>Let's draw a contour plots that will represent our Gaussian distribution for the dataset.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Create a 3D grid to build a contour plots.</span>

<span class="c1"># Create ranges along X and Y axes.</span>
<span class="n">latency_from</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">latency_to</span> <span class="o">=</span> <span class="mi">35</span>

<span class="n">throughput_from</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">throughput_to</span> <span class="o">=</span> <span class="mi">35</span>

<span class="n">step</span> <span class="o">=</span> <span class="mf">0.5</span>

<span class="n">latency_range</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">arange</span><span class="p">(</span><span class="n">latency_from</span><span class="p">,</span> <span class="n">latency_to</span><span class="p">,</span> <span class="n">step</span><span class="p">)</span>
<span class="n">throughput_range</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">arange</span><span class="p">(</span><span class="n">throughput_from</span><span class="p">,</span> <span class="n">throughput_to</span><span class="p">,</span> <span class="n">step</span><span class="p">)</span>

<span class="c1"># Create X and Y grids.</span>
<span class="p">(</span><span class="n">latency_grid</span><span class="p">,</span> <span class="n">throughput_grid</span><span class="p">)</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">meshgrid</span><span class="p">(</span><span class="n">latency_range</span><span class="p">,</span> <span class="n">throughput_range</span><span class="p">)</span>

<span class="c1"># Flatten latency and throughput grids.</span>
<span class="n">flat_latency_grid</span> <span class="o">=</span> <span class="n">latency_grid</span><span class="o">.</span><span class="n">flatten</span><span class="p">()</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">latency_grid</span><span class="o">.</span><span class="n">size</span><span class="p">,</span> <span class="mi">1</span><span class="p">))</span>
<span class="n">flat_throughput_grid</span> <span class="o">=</span> <span class="n">throughput_grid</span><span class="o">.</span><span class="n">flatten</span><span class="p">()</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">throughput_grid</span><span class="o">.</span><span class="n">size</span><span class="p">,</span> <span class="mi">1</span><span class="p">))</span>

<span class="c1"># Joing latency and throughput flatten grids together to form all combinations of latency and throughput.</span>
<span class="n">combinations</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">hstack</span><span class="p">((</span><span class="n">flat_latency_grid</span><span class="p">,</span> <span class="n">flat_throughput_grid</span><span class="p">))</span>

<span class="c1"># Now let&#39;s calculate the probabilities for every combination of latency and throughput.</span>
<span class="n">flat_probabilities</span> <span class="o">=</span> <span class="n">gaussian_anomaly</span><span class="o">.</span><span class="n">multivariate_gaussian</span><span class="p">(</span><span class="n">combinations</span><span class="p">)</span>

<span class="c1"># Resghape probabilities back to matrix in order to build contours.</span>
<span class="n">probabilities</span> <span class="o">=</span> <span class="n">flat_probabilities</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="n">latency_grid</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>

<span class="c1"># Let&#39;s build plot our original dataset.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">data</span><span class="p">[:,</span> <span class="mi">0</span><span class="p">],</span> <span class="n">data</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">],</span> <span class="n">alpha</span><span class="o">=</span><span class="mf">0.6</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Latency (ms)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Throughput (mb/s)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Server Operational Params&#39;</span><span class="p">)</span>

<span class="c1"># On top of our original dataset let&#39;s plot probability contours.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">contour</span><span class="p">(</span><span class="n">latency_grid</span><span class="p">,</span> <span class="n">throughput_grid</span><span class="p">,</span> <span class="n">probabilities</span><span class="p">,</span> <span class="n">levels</span><span class="o">=</span><span class="mi">10</span><span class="p">)</span>

<span class="c1"># Display the plot.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Select-best-threshold">Select best threshold<a class="anchor-link" href="#Select-best-threshold">&#182;</a></h3><p>Now, in order to decide which examples should be counted as an anomaly we need to decide which probability threshold to choose. We could do it intuitively but since we have all data examples labeled in our dataset let's use that data to calculate the best threshold.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Extract the information about which example is anomaly and which is not.</span>
<span class="n">num_examples</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
<span class="n">labels</span> <span class="o">=</span> <span class="n">pd_data</span><span class="p">[</span><span class="s1">&#39;Anomaly&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">values</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">num_examples</span><span class="p">,</span> <span class="mi">1</span><span class="p">))</span>

<span class="c1"># Returns the density of the multivariate normal at each data point (row) of X dataset.</span>
<span class="n">probabilities</span> <span class="o">=</span> <span class="n">gaussian_anomaly</span><span class="o">.</span><span class="n">multivariate_gaussian</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>

<span class="c1"># Let&#39;s go through many possible thresholds and pick the one with the highest F1 score.</span>
<span class="p">(</span><span class="n">epsilon</span><span class="p">,</span> <span class="n">f1</span><span class="p">,</span> <span class="n">precision_history</span><span class="p">,</span> <span class="n">recall_history</span><span class="p">,</span> <span class="n">f1_history</span><span class="p">)</span> <span class="o">=</span> <span class="n">gaussian_anomaly</span><span class="o">.</span><span class="n">select_threshold</span><span class="p">(</span>
    <span class="n">labels</span><span class="p">,</span> <span class="n">probabilities</span>
<span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Best epsilon:&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">epsilon</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">&#39;</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Best F1 score:&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">f1</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Best epsilon:
8.986095083415364e-05


Best F1 score:
0.8
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Plot-Precision/Recall-Progress">Plot Precision/Recall Progress<a class="anchor-link" href="#Plot-Precision/Recall-Progress">&#182;</a></h3><p>Let's now plot precision, reacall and F1 score changes for every iteration.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Make the plot a little bit bigger than default one.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">15</span><span class="p">,</span> <span class="mi">5</span><span class="p">))</span>

<span class="c1"># Plot precission history.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Iteration&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Value&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Precission Progress&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">precision_history</span><span class="p">)</span>

<span class="c1"># Plot recall history.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="mi">2</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Iteration&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Value&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Recall Progress&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">recall_history</span><span class="p">)</span>

<span class="c1"># Plot F1 history.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="mi">3</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Iteration&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Value&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;F1 Progress&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">f1_history</span><span class="p">)</span>

<span class="c1"># Display all plots.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Fing-Outliers">Fing Outliers<a class="anchor-link" href="#Fing-Outliers">&#182;</a></h3><p>Since now we have calculated best <code>epsilon</code> we may find outliers.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Find indices of data examples with probabilities less than the best epsilon.</span>
<span class="n">outliers_indices</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">where</span><span class="p">(</span><span class="n">probabilities</span> <span class="o">&lt;</span> <span class="n">epsilon</span><span class="p">)[</span><span class="mi">0</span><span class="p">]</span>

<span class="c1"># Plot original data.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">data</span><span class="p">[:,</span> <span class="mi">0</span><span class="p">],</span> <span class="n">data</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">],</span> <span class="n">alpha</span><span class="o">=</span><span class="mf">0.6</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Dataset&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Latency (ms)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Throughput (mb/s)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Server Operational Params&#39;</span><span class="p">)</span>

<span class="c1"># Plot the outliers.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="n">outliers_indices</span><span class="p">,</span> <span class="mi">0</span><span class="p">],</span> <span class="n">data</span><span class="p">[</span><span class="n">outliers_indices</span><span class="p">,</span> <span class="mi">1</span><span class="p">],</span> <span class="n">alpha</span><span class="o">=</span><span class="mf">0.6</span><span class="p">,</span> <span class="n">c</span><span class="o">=</span><span class="s1">&#39;red&#39;</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Outliers&#39;</span><span class="p">)</span>

<span class="c1"># Display plots.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[10]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>[]</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAYIAAAEWCAYAAABrDZDcAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDMuMC4xLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvDW2N/gAAIABJREFUeJzt3Xl8nGW58PHf9cxMMtmXLqErLUgrhUKtZRNB0KqAvgVBfeV1YbEgKG5wUA4ggiBHjwIe5bUeDyJWca9ABTmHopZFXoG2FmjBtkBLmzZdk2afZJbr/eN+Jp2EzGTSZjJJ5vp+PvPJzLNemUyea+7luW9RVYwxxhQuL98BGGOMyS9LBMYYU+AsERhjTIGzRGCMMQXOEoExxhQ4SwTGGFPgLBEYM8REpE1EjsjxOc4QkfpcnsMUDksEBU5E3ikiz4hIs4g0isjfROSEfMeVjoi8Q0T+IiKtfsx/FJE5eYxnpYgsTl2mquWq+nq+YgIQERWRdj8pbReRO0UkkM+YzMhliaCAiUgl8DDwA6AWmALcAnQdxLGCQxzbm44nIqcAjwEPAZOBmcALwN9y8Q18qH+nPDheVcuB9wD/B7hssAcYA++ByYaq2qNAH8ACYP8A21wKvAI0Af8DHJ6yToHPAZuAzcAS4Lt99n8IuNp/PhlYBuzxt/9CynY3A78HfgG0AIv7ieUp4If9LH8UWOo/PwOoB64H9gJbgI+nbFsMfBfYCuwCfgSU9Nn3q8BO4OdADS5Z7vHfg4eBqf723wTiQARoA+5OeV/e4j+vApb6+78B3Ah4/rqLgaf9eJr89+TslFgv8d/7VuB14DMp684A6jP83Xpi8F//LiW+64DX/OO+DHwoZbuLgb8BdwH7gNuAI4G/+K/3AvcD1Sn7bAGuBV4E2oGfAHX+36UVeByo8bcN+3/jfcB+4HmgLt//C4X+yHsA9sjjHx8q/X/InwFnJ/9ZU9afC7wKHA0E/YvYMynrFViBK02UAKcD2wDx19cAnbgE4AGrgZuAIuAI/+L2fn/bm4EocJ6/bUmfWEr9i+6Z/fwelwAN/vMzgBhwJ+6i/y7/4jTbX38XsNyPuQL4I/Bvffb9tr9vCTAOuMA/f4V/QX0w5dwr6ZO06J0IluKSYQUwA9gIfNpfd7H/O18GBIArgR0p798H/Iuw+L9HBzA/JdasEgEwB5fYkuf9SMrf5H/778+klJhiwOf9v3kJ8Bbgvf57MgF4Evheyrm2AH/HXfynALuBNcDbcBf+vwBf97f9jP+el/q/89uBynz/LxT6I+8B2CPPHwB3kb8P90045l8k6/x1jyYvHv5rz78YHe6/VuDdKesF9037dP/1ZcBf/OcnAVv7nPtfgZ/6z28GnswQ51T/fG/tZ91ZQNR/fob/e5SlrP8t8DU/vnbgyJR1pwCbU/btBsIZ4pgHNKW8XkmaROBf6LqBOSnrPgOs9J9fDLyasq7U3/ewNOd+EPhiSqwDJYIWXEnjNdw3ey/NtmuBc1Ni2pruuP425wH/SHm9hd6lrmXAkpTXn8dPnrgS5jPAcfn+7NvjwMPq/wqcqr6C++dHRN6KK7Z/D7gQOBz4DxG5I2UXwX3re8N/vS3lWCoiv/b3fRJXL/0Lf/XhwGQR2Z9yrACuuidpG+k1AQlgEvDPPusm4aoserZV1faU12/gvgFPwF1sV4tI6u+T2oi6R1UjPStFSnGliLNwJRyAChEJqGo8Q7wA44EQB96rZCxTUl7vTD5R1Q4/rnL/3GcDXwdm4ZJwKfDSAOdMNV9VX+27UEQ+BVyNK6Ekzzc+ZZNtfbavA/4DOA1XsvFwf49Uu1Ked/bzutx//nNgGvBrEanGfT5uUNVo1r+VGXLWWGx6qOo/caWDY/1F23D10tUpjxJVfSZ1tz6H+RXwYRE5HFcKWJZyrM19jlWhqudkOFZqbO3A/8NVa/T1UeDPKa9rRKQs5fV0XJXLXtxF6ZiUGKrUNaimi+EaYDZwkqpW4qq/wCWQjDH754vikmBqLNsz7OMOLlKMe+++iyuhVQN/SjnvQfH/Lv8FXAWM84+7rs9x+/5Ot/vL5vrvwScONg5VjarqLao6B3gH8EHgUwdzLDN0LBEUMBF5q4hcIyJT/dfTcN/m/+5v8iPgX0XkGH99lYj0dyHuoar/wF0A7wH+R1WTJYDngFYR+aqIlIhIQESOHWRX1euAi0TkCyJSISI1InIbrnrnlj7b3iIiRSJyGu5i8ztVTeAugneJyET/d5oiIu/PcM4KXPLYLyK1uG/oqXbh2jvexC8x/Bb4ph/v4bhv4r/ob/s+inB18nuAmF86eF8W+w2kDHdR3wMgIpdwIPGnU4FrDG8WkSm4huGDIiJnishcvytrCy5RJg72eGZoWCIobK24b+3Pikg7LgGsw30LRlUfwDWc/lpEWvx1Z2dx3F8CC/2f+MeK4y7I83C9Y5LJoirbYFX1aeD9wPlAA66a5W3AO1V1U8qmO3FVFztwPVyu8Es74HoEvQr83f+dHsd940/ne7gG07249+e/+6z/D1wJqElEvt/P/p/HtUu8jush9Evg3ix+11bgC7hE0oSrZls+0H5ZHPdl4A5c6WoXMBfXSyiTW4D5QDPwCPCHQwjhMFzvsBZcj6gncNVFJo+SvROMGRNE5AzgF6o6Nd+xGDNaWInAGGMKnCUCY4wpcFY1ZIwxBc5KBMYYU+BGxQ1l48eP1xkzZuQ7DGOMGVVWr169V1UnDLTdqEgEM2bMYNWqVfkOwxhjRhUReWPgraxqyBhjCp4lAmOMKXA5SwQiMk1E/ioiL4vIehH5or/8Zn/GpLX+45yBjmWMMSZ3ctlGEAOuUdU1IlKBG/Fxhb/uLlX9bg7PbYwZA6LRKPX19UQikYE3LmDhcJipU6cSCoUOav+cJQJVbcCNB4OqtorIK/QeftcYYzKqr6+noqKCGTNmkDJ0uEmhquzbt4/6+npmzpx5UMcYljYCEZmBGxzsWX/RVSLyoojcKyI1afa5XERWiciqPXv2DEeYxpgRJhKJMG7cOEsCGYgI48aNO6RSU84TgYiU48ZV/5KqtuDmtT0SNwplA24kxDdR1R+r6gJVXTBhwoDdYI0xY5QlgYEd6nuU00QgIiFcErhfVf8AoKq7VDWeMjb8ibmMwRhjTGa57DUkwE+AV1T1zpTlk1I2+xBujPuc2rD8cZ49+2O8MPcdPHv2x9iw/PFcn9IYMwYEAgHmzZvHMcccw/HHH88dd9xBIpF5Hp0tW7bwy1/+MuM2B+N73/seHR0dQ35cyG2J4FTgk8C7+3QV/XcReUlEXgTOBL6cwxjYsPxxuq6/kWBTI5HDJhFsaqTr+hstGRhjBlRSUsLatWtZv349K1as4NFHH+WWW/pOhtebJYIUqvq0qoqqHqeq8/zHn1T1k6o611++yO9dlDP7l9xDtLySWGUViEessopoeSX7l9yTy9MaY/Jg7dYmvvbgOi6+9zm+9uA61m5tGrJjT5w4kR//+MfcfffdqCpbtmzhtNNOY/78+cyfP59nnnFTeV933XU89dRTzJs3j7vuuivtdg0NDZx++unMmzePY489lqeeegqAxx57jFNOOYX58+fzkY98hLa2Nr7//e+zY8cOzjzzTM4888wh+52SRsUw1AsWLNCDHWvohbnvIHLYJJCUnKcJwjsbOP6lZ9LvaIzJu1deeYWjjz46q23Xbm3izhUbqQiHKA8HaYvEaI1Eufq9s5g3vd/OiQMqLy+nra2t17Lq6mo2bNhARUUFnucRDofZtGkTF154IatWrWLlypV897vf5eGHHwago6Oj3+3uuOMOIpEIN9xwA/F4nI6ODrq6ujj//PN59NFHKSsr49vf/jZdXV3cdNNNPWOujR8/Puv3SkRWq+qCgX7PUTHo3KGITJ1OsKnRlQh8wdZWIlOn5zEqY8xQW7ZmOxXhEJUl7qaq5M9la7YfdCLIJBqNctVVV7F27VoCgQAbN24c1HYnnHACl156KdFolPPOO4958+bxxBNP8PLLL3PqqacC0N3dzSmnnDLksfc15hNB9ZWL6br+RgBiFRUEW1sJtbVQfv1X8hyZMWYobWvsoK4q3GtZeTjItsahq1d//fXXCQQCTJw4kVtuuYW6ujpeeOEFEokE4XC4333uuuuufrc7/fTTefLJJ3nkkUe4+OKLufrqq6mpqeG9730vv/rVr4Ys5myM+UHnZi9aSPHttxGrqSW8s4FYTS3Ft9/G7EUL8x2aMWYITastpS0S67WsLRJjWm3pkBx/z549XHHFFVx11VWICM3NzUyaNAnP8/j5z39OPB4HoKKigtbW1p790m33xhtvUFdXx2WXXcbixYtZs2YNJ598Mn/729949dVXAWhvb+8pQfQ97lAa8yUCcMkAu/AbM6ZdMH8Kd65wF83UNoLLTju4YRcAOjs7mTdvHtFolGAwyCc/+UmuvvpqAD772c9ywQUXsHTpUs466yzKysoAOO644wgEAhx//PFcfPHFabdbuXIl3/nOdwiFQpSXl7N06VImTJjAfffdx4UXXkhXVxcAt912G7NmzeLyyy/nrLPOYvLkyfz1r389lLfqTcZ8Y7ExZvQaTGMxuAbjZWu2s62xg2m1pVwwf0pO2gdGImssNsYYYN70moK58A+lMd9GYIwxJjNLBMYYU+AsERhjTIGzRGCMMQXOEoExxhQ4SwTGGJNBfX095557LkcddRRHHnkkX/ziF+nu7s64z+23397rdXl5OQA7duzgwx/+cM5iPViWCIwxJg1V5fzzz+e8885j06ZNbNy4kba2Nm644YaM+/VNBEmTJ0/m97//fdbnj8ViA280BCwRGGPGjueeg899Ds45x/187rlDOtxf/vIXwuEwl1xyCeAmqrnrrru49957+eEPf8hVV13Vs+0HP/hBVq5cyXXXXddzR/LHP/7xXsfbsmULxx57LADxeJxrr72WE044geOOO47//M//BNwdx6eddhqLFi1izpw5tLe384EPfIDjjz+eY489lt/85jeH9Dv1x24oM8aMDc89BzfdBFVVMGUK7N3rXn/jG3Diwc2Iu379et7+9rf3WlZZWcn06dPTflv/1re+xd13383atWszHvsnP/kJVVVVPP/883R1dXHqqafyvve9D4A1a9awbt06Zs6cybJly5g8eTKPPPII4MYuGmpWIjDGjA0/+5lLAtXV4HnuZ1WVWz4CPfbYYyxdupR58+Zx0kknsW/fPjZt2gTAiSeeyMyZboykuXPnsmLFCr761a/y1FNPUVVVlemwB8USgTFmbNi8GSorey+rrHTLD9KcOXNYvXp1r2UtLS1s3bqV6urqXvMXRyKRQR1bVfnBD37A2rVrWbt2LZs3b+4pESQHpgOYNWsWa9asYe7cudx444184xvfOOjfJx1LBMaYsWHmTGhp6b2spcUtP0jvec976OjoYOnSpYCr17/mmmu4+OKLOeKII1i7di2JRIJt27bxXEp7RCgUIhqNZjz2+9//fpYsWdKz3caNG2lvb3/Tdjt27KC0tJRPfOITXHvttaxZs+agf590rI3AGDM2XHSRaxMAVxJoaYHmZrjmmoM+pIjwwAMP8NnPfpZbb72VRCLBOeecw+23305RUREzZ85kzpw5HH300cyfP79nv8svv5zjjjuO+fPnc//99/d77MWLF7Nlyxbmz5+PqjJhwgQefPDBN2330ksvce211+J5HqFQiCVLlhz075P297RhqI0xI9Vgh6Hmuedcm8Dmza4kcNFFB91QPNrYMNTGGAPuol8gF/6hZG0ExhhT4CwRGGNGtNFQfZ1vh/oeWSIwxoxY4XCYffv2WTLIQFXZt28f4XD4oI9hbQTGmBFr6tSp1NfXs2fPnnyHMqKFw2GmTp160PtbIjDGjFihUKjnDluTO1Y1ZIwxBc4SgTHGFDhLBMYYU+AsERhjTIGzRGCMMQXOEoExxhQ4SwTGGFPgLBEYY0yBs0RgjDEFzhKBMcYU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
"
>
</div>

</div>

</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>
