---
layout: none
permalink: /tutorial/multivariate_logistic_regression
---
<html>
<head><meta charset="utf-8" />

<title>multivariate_logistic_regression_demo</title>

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
<h1 id="Multivariate-Logistic-Regression-Demo">Multivariate Logistic Regression Demo<a class="anchor-link" href="#Multivariate-Logistic-Regression-Demo">&#182;</a></h1><p><em>Source: 🤖<a href="https://github.com/trekhleb/homemade-machine-learning">Homemade Machine Learning</a> repository</em></p>
<blockquote><p>☝Before moving on with this demo you might want to take a look at:</p>
<ul>
<li>📗<a href="https://github.com/trekhleb/homemade-machine-learning/tree/master/homemade/logistic_regression">Math behind the Logistic Regression</a></li>
<li>⚙️<a href="https://github.com/trekhleb/homemade-machine-learning/blob/master/homemade/logistic_regression/logistic_regression.py">Logistic Regression Source Code</a></li>
</ul>
</blockquote>
<p><strong>Logistic regression</strong> is the appropriate regression analysis to conduct when the dependent variable is dichotomous (binary). Like all regression analyses, the logistic regression is a predictive analysis. Logistic regression is used to describe data and to explain the relationship between one dependent binary variable and one or more nominal, ordinal, interval or ratio-level independent variables.</p>
<p>Logistic Regression is used when the dependent variable (target) is categorical.</p>
<p>For example:</p>
<ul>
<li>To predict whether an email is spam (<code>1</code>) or (<code>0</code>).</li>
<li>Whether online transaction is fraudulent (<code>1</code>) or not (<code>0</code>).</li>
<li>Whether the tumor is malignant (<code>1</code>) or not (<code>0</code>).</li>
</ul>
<blockquote><p><strong>Demo Project:</strong> In this example we will train handwritten digits (0-9) classifier.</p>
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
<li><a href="https://docs.python.org/3/library/math.html">math</a> - math library that we will use to calculate sqaure roots etc.</li>
<li><a href="https://github.com/trekhleb/homemade-machine-learning/blob/master/homemade/logistic_regression/logistic_regression.py">logistic_regression</a> - custom implementation of logistic regression</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Import 3rd party dependencies.</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">matplotlib.image</span> <span class="k">as</span> <span class="nn">mpimg</span>
<span class="kn">import</span> <span class="nn">math</span>

<span class="c1"># Import custom logistic regression implementation.</span>
<span class="kn">from</span> <span class="nn">homemade.logistic_regression</span> <span class="k">import</span> <span class="n">LogisticRegression</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Load-the-Data">Load the Data<a class="anchor-link" href="#Load-the-Data">&#182;</a></h3><p>In this demo we will be using a sample of <a href="https://www.kaggle.com/oddrationale/mnist-in-csv/home">MNIST dataset in a CSV format</a>. Instead of using full dataset with 60000 training examples we will use cut dataset of just 10000 examples that we will also split into training and testing sets.</p>
<p>Each row in the dataset consists of 785 values: the first value is the label (a number from 0 to 9) and the remaining 784 values (28x28 pixels image) are the pixel values (a number from 0 to 255).</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Load the data.</span>
<span class="n">data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;../../data/mnist-demo.csv&#39;</span><span class="p">)</span>

<span class="c1"># Print the data table.</span>
<span class="n">data</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[3]:</div>



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
      <th>label</th>
      <th>1x1</th>
      <th>1x2</th>
      <th>1x3</th>
      <th>1x4</th>
      <th>1x5</th>
      <th>1x6</th>
      <th>1x7</th>
      <th>1x8</th>
      <th>1x9</th>
      <th>...</th>
      <th>28x19</th>
      <th>28x20</th>
      <th>28x21</th>
      <th>28x22</th>
      <th>28x23</th>
      <th>28x24</th>
      <th>28x25</th>
      <th>28x26</th>
      <th>28x27</th>
      <th>28x28</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>9</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>10 rows × 785 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Plot-the-Data">Plot the Data<a class="anchor-link" href="#Plot-the-Data">&#182;</a></h3><p>Let's peek first 25 rows of the dataset and display them as an images to have an example of digits we will be working with.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># How many numbers to display.</span>
<span class="n">numbers_to_display</span> <span class="o">=</span> <span class="mi">25</span>

<span class="c1"># Calculate the number of cells that will hold all the numbers.</span>
<span class="n">num_cells</span> <span class="o">=</span> <span class="n">math</span><span class="o">.</span><span class="n">ceil</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">))</span>

<span class="c1"># Make the plot a little bit bigger than default one.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">10</span><span class="p">))</span>

<span class="c1"># Go through the first numbers in a training set and plot them.</span>
<span class="k">for</span> <span class="n">plot_index</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">):</span>
    <span class="c1"># Extrace digit data.</span>
    <span class="n">digit</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="n">plot_index</span><span class="p">:</span><span class="n">plot_index</span> <span class="o">+</span> <span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">values</span>
    <span class="n">digit_label</span> <span class="o">=</span> <span class="n">digit</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="mi">0</span><span class="p">]</span>
    <span class="n">digit_pixels</span> <span class="o">=</span> <span class="n">digit</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="mi">1</span><span class="p">:]</span>

    <span class="c1"># Calculate image size (remember that each picture has square proportions).</span>
    <span class="n">image_size</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">digit_pixels</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]))</span>
    
    <span class="c1"># Convert image vector into the matrix of pixels.</span>
    <span class="n">frame</span> <span class="o">=</span> <span class="n">digit_pixels</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">image_size</span><span class="p">,</span> <span class="n">image_size</span><span class="p">))</span>
    
    <span class="c1"># Plot the number matrix.</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="n">num_cells</span><span class="p">,</span> <span class="n">num_cells</span><span class="p">,</span> <span class="n">plot_index</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">frame</span><span class="p">,</span> <span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;Greys&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="n">digit_label</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">tick_params</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span> <span class="n">which</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span> <span class="n">bottom</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">left</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">labelbottom</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">labelleft</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>

<span class="c1"># Plot all subplots.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">subplots_adjust</span><span class="p">(</span><span class="n">hspace</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span> <span class="n">wspace</span><span class="o">=</span><span class="mf">0.5</span><span class="p">)</span>
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
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAkEAAAJBCAYAAABBBGGtAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDMuMC4xLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvDW2N/gAAIABJREFUeJzs3Xm8leP+//H3pVKaJCUybVNCSJL5cAwNMicyz1RCZsdx0ODLMYVCxkJmJ47wM5wiMpe5UkQhSpuUojRcvz9296drae323muvte619v16Ph49vM+11/A53a29r31d93VdznsvAACApFkj7gIAAADiQCcIAAAkEp0gAACQSHSCAABAItEJAgAAiUQnCAAAJBKdIAAAkEhF3wlyzr3unFvknFuw4s+UuGtCdjjnmjrnnnHOLXTOzXDOHRd3Tcgu59xWKz6/I+KuBdnjnOvjnBvvnFvsnBsedz3ILufcNs65Mc65ec65r5xzR8RdU6aKvhO0Qh/vfcMVf7aOuxhkzR2S/pTUQtLxku5yzm0Xb0nIsjskfRB3Eci6HyQNlPRA3IUgu5xztSX9V9LzkppKOkvSCOdcq1gLy1BN6QShhnHONZDUTdK/vPcLvPfjJD0n6cR4K0O2OOd6SPpV0ui4a0F2ee9Heu+flfRz3LUg61pLailpkPd+mfd+jKS3VKTfm2tKJ+g651ypc+4t59y+cReDrGglaan3fmrQ9okkRoJqAOdcY0n9JV0Ydy0Aqs1JahN3EZmoCZ2gyyRtLmlDSfdIGuWc2yLekpAFDSXN/0vbPEmNYqgF2TdA0v3e++/jLgRAlUyR9JOkS5xzdZxzHSXtI6l+vGVlpug7Qd7797z3v3nvF3vvH1TZsNxBcdeFalsgqfFf2hpL+i2GWpBFzrm2kg6QNCjuWgBUjfd+iaTDJXWVNEvSRZKelFSUv9DUjruAHPAqG5pDcZsqqbZzbivv/Zcr2naUNDHGmpAd+0oqkfStc04qG/Wr5Zzb1nvfLsa6AFSC9/5TlY3+SJKcc29LejC+ijJX1CNBzrkmzrlOzrl6zrnazrnjJf1N0ktx14bq8d4vlDRSUn/nXAPn3J6SDpP0cLyVIQvukbSFpLYr/gyV9IKkTnEWhexZ8f24nqRaKuvg1luxqgg1gHNuhxXXtL5z7mJJG0gaHnNZGSnqTpCkOipbhjlHUqmkcyUd/pebaVG8ektaS2Xzz49J6uW9ZySoyHnvf/fez4r+qGzqc5H3fk7ctSFrrpT0h6TLJZ2wIl8Za0XIphMl/aiy7837SzrQe7843pIy47z3cdcAAACQd8U+EgQAAJAROkEAACCR6AQBAIBEohMEAAASiU4QAABIpCrt29CsWTNfUlKSo1JqpunTp6u0tLTgN2/k2mZmwoQJpd775nHXURGub2aK4fpybTNTDNdW4vpmqrLXt0qdoJKSEo0fPz7zqhKoffv2cZdQKVzbzDjnZsRdQ2VwfTNTDNeXa5uZYri2Etc3U5W9vkyHAQCARKITBAAAEolOEAAASCQ6QQAAIJHoBAEAgESiEwQAABKJThAAAEgkOkEAACCRqrRZIhC37777zvJtt90mSRo0aJC1XXDBBZbPP/98yxtvvHEeqgMAFBNGggAAQCLRCQIAAIlUdNNhy5cvt7x48eIKH//ggw9KkhYuXGhtkyZNsnzrrbdavuKKKyRJQ4YMsba11lrL8s0332y5V69eVSkb1TBz5kzLO+20k+Vff/1VkuTcyvNpw+sZXXtJmjNnTi5LRMwmT54sSTrggAOs7eOPP7bcvHnBn5OZePfee6/lnj17Wo6+50+ZMsXaWrVqlb/CUKMxEgQAABKJThAAAEikgpgOmzdvnuVly5ZZ/uSTTyy/8sorklZOgUjSPffck9H7lZSUWL7oooss33///ZKktdde29r23ntvy/vtt19G74eqmzFjhuV9993X8ty5cy1H02Dh9apbt67ln376yfLXX38tSdp0002trVatWtkruAb58ssvLYd/3x06dIijnEp57733JEn7779/zJWgKkaPHm35wgsvtLzGGqv+fh5OewPZwkgQAABIpNhGgr7//nvLbdu2tRz+5plN4W8W0YiPlHrj8+mnny5JWm+99aytYcOGlrm5MjeWLFkiKXX0p3PnzpbDvYHSCf/9XHvttZb32msvy1tttZWk1NHD6HojVfjb+RdffGG50EaCvPeWo9GrqVOnxlUOMhBer0WLFsVYCVZn+vTplocPH275pZdesvzBBx+s8rxHHnnEcrhX26uvvmr5lFNOkZQ6Q5NPjAQBAIBEohMEAAASKbbpsHXXXddyixYtLGc6HdaxY8e0rz1y5EhJqTfMhjfaIn6XXHKJpNT9mapi7NixlsP9oI444gjL0b+Djz76KKP3SJLbb7/dcvi5KjQLFiywfN1110lKPSqF6evCFe3Vds0116T9ert27SxHi2IaNGiQ87qQ6q233pIkHX300dY2e/Zsy+GU9JFHHmk5uoXhhBNOSPu64fOiPdzuuOOOLFRcdYwEAQCARKITBAAAEim26bBwVVZ4t/nTTz9teffdd7fcrVu3VV4jXP3z3//+1/Kaa65pedasWZJWnjiOwhCu+BoxYoSk1CHSUDitFf47iIZaw1UH22yzjeXLLrvMcvTvqrz3wErhXl2FLDxaIRJefxSWr776yvJBBx0kSfrll1/SPvb666+3HO4DhtwIj6MKV4J17dpVUurU8+GHH2554MCBlqMVuNLK7yGnnXaatT3++ONp33uPPfbIsOrsYCQIAAAkEp0gAACQSAVxbMYuu+xieYcddrAcTmtdeumlkqQbbrjB2gYMGJD2saH1119f0srVI4hPVU6DP/744y2Hp0tHq0rC9h49elhb/fr1Lbds2dJytFnmww8/bG2XX3655XBKLYl++OEHy+F1KmTpplIOPPDAGCpBZdx3332W022AGq4u+vvf/56XmlDmtddes9ypU6dVvn7MMcdYfuCBByyHq65D48aNk1T+FFi4MWJ4u0McGAkCAACJRCcIAAAkUkFMh4XKG15bZ511VmkLN3ULT3vntOHCUVpaavnf//635XBTzGizzM0228zaevXqZTmc6gzPCQtzZf3++++Wb7zxRsvhv6Ukijakk1L/jgpNuBnmZ599tsrXw41SEb/yPm/R9HR4vcLbG5B74fe8Cy64wHL48/Oqq66SlLrStryf0aG+ffuu9utPPPGE5fAWhjgwEgQAABKp4EaCyhP1LN9//31re+aZZyxPnDjRcps2bfJXGFaxdOlSyxdffLHlaD8gKXXvj5dfflmStOWWW1pbdLJ8Ln3zzTc5f49i8fnnn6dtz2S0LZf++c9/Wg5v5o4WVJS3QAL5Ey10kKTDDjtstY8Nj81o3bp1rkrCCkOHDrUcjv6EozvhQpN//OMfkqQ6deqkfb3we/0nn3xi+csvv5SUui9bOPLUvn37KteeK4wEAQCARKITBAAAEqlopsOiYe577rnH2kaPHm05HHYNt/Xec889JaXuRcCN07n17bffWg6nwELvvvuu5VatWq3y9fBYFcRn1113zev7LV682PKE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UlKi8ePHZ15VArVv3z7uEiqFa5sZ59yMuGuoDK5vZorh+nJtM1MM11bi+maqsteX6TAAAJBIdIIAAEAi0QkCAACJRCcIAAAkEp0gAACQSHSCAABAItEJAgAAiUQnCAAAJBKdIAAAkEhV2jEayKUBAwZYvuqqqyx36NDB8iuvvGJ57bXXzk9hAIC86d69u2XvveWnn3466+/FSBAAAEgkOkEAACCRauR02OLFiy0vWbJEkjRu3DhrmzlzpuWTTz7Zcu3aNfKvo+D9+uuvkqTbb7/d2tZYY2X/fMKECZa//fZby9tvv30eqkN1lZaWSpKWLl1qbe+//77lww47zHJ43avi1FNPlSTdfffd1larVq2MXgtVt2zZMsvTpk2z3LdvX8svvvhiXmtCcbn22mstv/DCC5YvuOCCnL4vI0EAACCR6AQBAIBEKur5n2gaRZJuvvlmy2PGjLH83nvvrfY1wqmxcEUS8qd+/fqSpEMPPdTahg8fHlM1yNSsWbMsP/TQQ5bvueceSdLy5cutLZzWDKfAnHMZvXf072WdddaxtoEDB1quW7duRq+LyglvQWjdurXljTbayPKCBQssN2zYMD+FoeBFP7vD6bA111zTcteuXXP6/owEAQCARCqakaA5c+ZIkm677TZrC/Mff/xhOdxXYLPNNpMkrbvuutYW3mgb3kjZq1cvSVLz5s2zVTYqIer1R9cKxenyyy+3PGLEiFhqGDRokOWePXta3mKLLeIoJ/G+//57y/PmzbPMSBAi0aKlP//809oOOeQQy3vssUdO35+RIAAAkEh0ggAAQCIV3HTYokWLLIc3Nt51112SUodUyxPuHzN27FhJqXuUtGjRwvLs2bMtR6/NdFh+Rdf8o48+irkSVEc4hJ1uOqxly5aWL774YsvhDdPp9gl68803LT/zzDPVrhP5E96agOL15ZdfWg4XED3wwAOW11prrUq/XviZfvvttyVJ2267rbWF09q5xkgQAABIJDpBAAAgkQpuOuytt96yfP3111f6eeFQ2htvvGG5cePGkqSff/45C9UhF6KjTSZNmlThY999913Lm2yyiSROky8URxxxhOVffvllla+HU11VWR109tlnW95mm20sh3sNRU477TTLm266aaXfA7kR7vsU7iWE4hKe6v7ZZ59ZHjBggOUtt9yy0q934YUXWv7pp58kSaNGjbK2cOo81xgJAgAAiUQnCAAAJFLBTYdVdFxCq1atLO+3336Wwy23oymw0IwZM6pfHHKiUaNGklJPC442rvyrsD3aAPPII4/MYXWorHC6K91nMFMffvih5ehE+vJEU6SSVLt2wX17S7SPP/7Y8uabbx5jJaiq8PMcTnGGGxxWJDyiKlxtFn3fiGu6lJEgAACQSHSCAABAIhXcePGdd95peffdd7fcuXNnSakbHTZo0KDSrxvdgY7CddZZZ1kubzoMyRGdKRSeEfj777+v9jmXXHJJTmtCeuFU6DrrrGN57ty5lidPnpzXmlB9gwcPliS988471rbTTjtZLikpWe3zw+my6667zvKCBQssd+rUSVLuzwgrDyNBAAAgkQpuJCi6SVaSevfunbXXHTNmTNZeC7lX0VEKqDnCfb0uuugiyxMnTpRUuZsv9957b0n8W4lLvXr1LIfHpzz00ENxlINqmD9/vuVor746depY2yOPPGK5fv36q32tfv36WR46dKjlcAHDiy++mHmxWcB3DAAAkEh0ggAAQCIV3HRYVTz99NOWwyG88OTiaE+DCRMmpH2Nrl27WmbvisIRTmuE+1KgcP3666+Wn3zyScsVDXeH2+VXdK2bNGliOZxq2WuvvSSlDtsDqJwff/zR8gEHHGB59uzZklKntcK9+soTTZnddNNNab9+++23Z1RnLjASBAAAEolOEAAASKSCng6LTheXpB9++EGSdNVVV1nbiBEj0j6vopVFG2+8seVhw4at9rEAyhcOo++7776Wp02blpP3C1ceHXTQQTl5D+RGRUeeIPfCn42vvfaa5Y4dO6Z9TPQzcezYsda2/vrrWz755JMtL1q0yHJ0/FV4a0p4LNLBBx+cUf25wE99AACQSHSCAABAIhXEdNiyZcssf//995bD4fXvvvtOUurmTOG0VpcuXSw/9thjlsPtuSNLly61/MILL1g+7rjjJEm1atWqUv0AUoe+w1yRqmyMGa4IO//88y23bdu20u+HeDz44IOWBw0aFGMlyfXmm29ajo6rkFJXZYafwe22205S6mbDYX7iiScshyfDRz+vw6mzG2+8sVq15wojQQAAIJHoBAEAgESKbTosnAL7+OOPLe+6665pHx+dLr///vtb2xZbbGH5jz/+sPzpp59afu+991Z5rVmzZlk+9dRTLUebJYY11K5dEDOGiVOZKZJXX31VknTkkUfmpSasaoMNNrD8wQcfWH7qqacsRytP1lxzzSq99v333y9Juvrqq6tTIvKsc+fOljk7rDC89dZbklI3Qgw/j02bNrX8v//9z3J0lmffvn2t7ZlnnrEcTo2l26Q42mxRkjbbbDPL4ebF4XvHgZEgAACQSHkf5ohGgG677TZru/TSS9M+NrpRWZJOOukkSamnFf/++++Ww30H3n33Xct169aVlHpTVjjyFO4TtM8++0iSjj76aGsL9yVq2LBh2jo32mijtO3IXGWOzbj33nslSddcc421tWjRIqd1oXxrr7225TPOOKParxedKM9IUHEJf+MP/fnnn5bnzZsnKfXfDHInuhF9yy23tLbw6IoDDzxwtc8fMmSI5XDW5aWXXlrt88LRocMPP9xy3KM/IUaCAABAItEJAgAAiZSX6bDwJtdbb71VknTZZZdZW3TzlbRyu20pdR+DaBpsxowZ1nbmmWdafuONNyxvv/32lh9//HFJUuvWra1t8eLFls8991zLDzzwgKTU/SzC07BD4YnzU6dOTfsYZO7KK6+0fO211672sdG02F+fh+L24Ycfxl0CMlDePmvh1Eh4JBJy75hjjpGU+jO1cePGlX7+/PnzLb/zzjtpHxPuQRQuWoo0adKk0u+XT4wEAQCARKITBAAAEikv02HPP/+85WgaLFxpNWrUKMs777yz5SlTplgeOnSopNST48O71MO718NVZemG/KIVY5K0ww47WI6m6rp162Zt4VRLiG3fcyu8LigM0crOzz77zNqibfUlqU6dOtV+j2jvJ0nq3r17tV8P+de+fXvL4XEm4arcaGVS//7981dYgmX6WYpOhn/kkUes7ddff7W87bbbWt5jjz0yrC5ejAQBAIBEohMEAAASKS/TYb17916lLTzJ/Z///KflaBMtSfr8889X+7p33XWX5dNPP91yRSdRV2TvvfdOm5E/4ZTkNttsY3nSpEmrPPZf//qX5fDfWiFtyFWswpOho00pw5Ojf/nlF8tVmQ4Lp7Lff/99yz169LC8YMGCVZ5Xv359y+HGqShM4ZE233zzjeVwE1oUrkcffVSSNHDgQGsLj8qJjuMoZowEAQCARMrLSFBJSYnl6PDS6IYrqfze5AknnGA52ta7S5cu1hbuO1Dd0R8Urg4dOliePHnyKl/n2ufOKaecYjndYcThAoGq7DsS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WB1Qc9x2222WL7vssoxe49FHH612HRdccIHl9u3bS5LOPPNMa+vWrZvlJk2aVPv9kB3z58+3PGLEiAofX1JSIolbEwpddJTJCy+8YG3htX777bctd+7cOX+FZREjQQAAIJEKeiQovFHu7rvvliQde+yx1hbuR7H55ptb/vrrr1d5rV9++cXyqFGjLDMSlAzRzbzhDcBPPvmk5YEDB6Z9XrS/1E033ZTD6uIX3ahaGeutt57lvffeu9LP22abbSyHCxl++ukny2+++abl999/P+W/krTzzjtbbtu2baXfG7kR3RDdpUsXa4tupv2r9957z3I0yofCVqdOHUmp1yu8GXrmzJl5rynbGAkCAACJRCcIAAAkUkFPh4UOOeQQSdKOO+5obeFNWc2aNbOcbjos1LNnzyxXh0IxadIky48//rjlaO+ouXPnWlu0df/qjB49OovVFa5x48ZZDoe70+3Vs+aaa1qOFixUx+LFiy1vt912ltN9jp966inLTIfF77HHHpMkTZs2zdpOOOEEy0OGDLHcqFGj/BWGrLrkkkssjxw50vLnn38eRzlZxUgQAABIJDpBAAAgkYpmOixy8803Ww63Z4+29K+MJUuWZLUmxCPaz+bDDz+0toqmr9Zee23L5557ruVwldPf//53y7VrF91HJCNNmzZNm/MhXDWUbgqsXr16ls8666y81ITyhSvB3njjDUlSq1atrO2WW26xzBRYzRCu7AwNHTrU8oABAyxnY5o8XxgJAgAAiUQnCAAAJFLRjfXvtttull966SXLBxxwgOVweD2dK6+80vI999yTxeqQC3/88Yfl/v37W77xxhslSc2bN7e2fffd1/J1111nOdpMM1zZFE6NIfeWLVtm+eqrr7Y8aNCg1T5v6tSplqtyOj2yZ/z48ZbDk+GjFZZnnHGGtUUb7KFmCjfDDFd2vv7665YPPvjgfJZULYwEAQCARKITBAAAEqnopsOi1QhS6rRXeL5QRcLT6VH4whWBN9xwg+V+/fpJSj31PJzuQmH44osvJEn333+/tYXXNBROpfznP/+RJK2//vo5rA7lWbRokeWKVl2Gm9U2bty40u8Rbn5Z3ia34ecb8Stvk9lwaqyYMBIEAAASqaBHgubMmWO5Y8eOklK36V66dGlGrxu9FgpDtG9TeJP67bffbvnRRx+13LlzZ8vRsQlJ2cunmMyYMcPy9ttvLyn1xujyrLHGyt/LopugK3O8CbIv/HsPR9qXL19uObpe4T5b5YmO2AhfO7xB/quvvkr7vMsvv1ySNH/+fGtj/yFkCyNBAAAgkegEAQCARCroeYRvvvnGcnRzZaZTYKFwqiUcjkU8opOmw2NQevXqZXnHHXe0zNRXcXj88cctV2YaLBLeXNmuXTtJqceYHHPMMZYPOeQQyxtssEFGdaJ8kyZNsvzf//7XcjhlucUWW0gq/2bomTNnWg5vrh4+fPgqjw2nuKJ9vSTpk08+kSR1797d2p544gnL7PeF6mAkCAAAJBKdIAAAkEgFPbfQoUMHyw8//LAk6aSTTrK28DiFqgiHaBG/Cy+8UFLqapRTTz3VMlNgxSecuohWdP7vf/+zttmzZ1f6tV577bW0uXfv3pavvfZaSVKfPn2srUGDBlWoGFLqdGR5+/ZsvPHGls877zxJ0rrrrmttpaWllv/9739bHjZsmOUWLVpISv13cskll1j+/fffLUcnmP/000+V/H+BXAqPzagJKzcZCQIAAIlEJwgAACRS0cwzHHXUUZKkrbbaytrCzbNC4WqUI444QpL066+/5rA6VMcBBxwgSRozZoy1hcPko0aNsrzddtvlrzBkLFzdE01lz5s3z9rCz+4vv/xiOdxQ78Ybb5SUOvweCjft+8c//iEpdVO/p59+2nJNGLbPh2gVrpS6Ei8UbV4oST179pQkLVy40NrCVZ4jRoywHK7iOuussyRJV155pbWF02jhe0fPO/TQQ9O+FvKrpn2WGAkCAACJRCcIAAAkUtFMh0XCjfPKEw6fDxw4UFLqqpFx48ZZDofoGWLNvunTp1sOV5XUqlXL8nPPPScpdfXIueeea3mvvfayPGXKFMvrrbdeVmtFboWfrzCH/y7Cz/dBBx0kaeVnWEpdYZbOM888YzmahpNSV5WifB9//HGFj4mmwELh9PUrr7yS9nnvvvuu5VatWklKXYEWtf1VtPKP0+QLW3RGYLFhJAgAACRS0Y0EVUZ4Y3Q4AhSpW7eu5Zp2k1ecFixYIEnq2rWrtYUjN+FW9/vss4/ltdZaS5J0yimnWFs4EhTeRBu9h8RIUE33t7/9TZL00ksvWVu3bt0sh0c5pDN58uTcFFaD/fzzz5bDEfVw365QtOfaxIkT0z7v0UcftRyO9EQ3QXfp0qXC55V3gzYKy/rrrx93CRlhJAgAACQSnSAAAJBINXI67JZbblnt18N9LMo7/RhV17p1a0mpezI99NBDlsMpsHTuu+++tO1HH3205Q033LA6JaIIhaeW77rrrpYrmg5r06ZNzmpKgvBWgYpuGwivUfjY8ePHW472cpJWHnkUXqPwseEtC0AuMRIEAAASiU4QAABIpLxPh0XDoL169bK20047zXK0IqSqwlVD11133WofG+0/guzq37+/pJUnS0srjztZnWhIPDptXJK23HJLyzfccINlhskLS/i5C49I2GGHHSzvscce1XqP8HiMDz/8cLWPrV175be0Dh06VOt9k+jwww+3fOmll1oO9/AKp7WiVWHhfmuhQYMGWQ5Xf0WnyEdHo0hSo0aNMi0bBWDp0qVxl5ARRoIAAEAi0QkCAACJlPfpsGjr8wcffNDawq3an3zyScvNmjWz3LRpU0nSd999Z23hkQzhEG26E+Ovv/56ywy75kY0rRlOWb333nuWw1O9Q3PmzJEknXDCCdZ28803W1533XWzWieqJ5wCO/DAAy2H1/r333+v9vtEJ5Pfdddd1lbev6HIzjvvbHmrrbaqdg1JU6dOHcsNGza0HF7z8O+1KpvNpjtFvm3bthnVicLz2muvWQ43NS10jAQBAIBEyvtIUN++fSVJX375pbWF2+JvvfXWlsPfOKL9QUaNGmVt5d2MF/52Ev2mccEFF1hbePMksu/4449Pm2+//fY4ykGWhQdZhqM/ofD4heh4k3CUIbRkyRLL4V5RV1xxhaTyP+fhjbbRKEM4woyqCw+zff311y1Hh5hK0siRI1f7GhdeeKHlcGRup512slzeYakoTA0aNLAcXtMJEybEUU5WMRIEAAASiU4QAABIpLzPC22++eaSUo9QCPcMOuywwyyHU2Zhrkh4I21F+4oAqJqDDz7YcnjTciicVtl7770lSc2bN0/72OjGeEl68803K11HeKPtO++8I4lplmwKb1p+6qmnYqwEcatVq5bl8hYWhbeqcGM0AABAgaMTBAAAEim2ZVKXX3655XC77fDU8dD7778vSRoyZEjar6+zzjqWmQIDcmf33Xe3fM4551i+44470j6+KlNc6YSrOcNVSt27d7dcUlJSrfcAUDnhcTThCsJwL6liwkgQAABIJDpBAAAgkQpi18BwuPvEE09M+5ioffDgwXmpCUB6TZo0sRye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C/fhi0bgpZX7RElSaWmp5WjG5v3337e2TTfd1PKzzz5rmZEgAACAGNAJAgAAiZT36bBrr71WUuo+IqGuXbtaDm+YrMo02KJFiyxHw3HPPfdche/HzZXFJRqKXbhwYdqvs2V/fMIb4ps0abLK17/77jvL4b5c4bB7dBJ1eOzGgQcemNU6UXUPPvig5WhRQjhFEgqPRwhvqI32bYsWvEjSo48+ajncOw7xefvttyWlngp/zTXXWA4/r6+99toqzx83bpzlQt1/j5EgAACQSHSCAABAIuV9Oqxv376SUo83CPf+GD58uOXyttOvSDisetZZZ63y9fAk6kceeaTa74d4zJ07V5L0ySefpP16ly5dVvv88MT5GTNmWA6HcKNh+fL2oULFwuMyquKEE06QlHqKPFOc8bvhhhssv/HGG5JSpz+jU8ElqVevXpajPYUkaaeddpIkjR8/3to6duxo+Z133rG8ww47ZKNsZGCDDTaQJM2bN8/axowZYznd9LW08mfpZpttlusSq42RIAAAkEh0ggAAQCLlfTps1113lSSNHTs2q68bbsTWp0+fVb4enjh++eWXW2YKrPCFG3KFp1V//PHHq31eNJ0iSXvuuaeklasdJOnHH3+0/M0331gON3D74osvJEk333xzVctOtOXLl1t+9dVXJaUOnZfnxBNPtByuQkK8Zs2aZTn8PEYblobCjWmPOeYYy+lWB0WfSyl1FWB4rEq4sR7yK5quDL8/Rqe+S6nXL3T66adLklq0aJHD6rKDkSAAAJBIdIIAAEAixXaKfLaFK77Cu9Qj//nPfywfdNBBeakJ0pIlSyyHq7GiaSZJevPNNyWtPB/ur3777TfL4SnxFQnPrZkzZ84qX7/44osth5tmhiuQ0m30h4qFq4Luu+8+Sek/l39Vmccg/6KVmH8VngcVadmypeUrrrii0u/Rs2fPtK+B+IWrvMINLsvzj3/8I5flZBUjQQAAIJGKeiRo0KBBlsMbMddYY9W+XThShNyIRn1uu+02awv3bKroRuZQOAITjsyE+5GEN2hGLrvsMsu9e/e2vPHGG1f6vVF54SjdE088Yfnee++1HI3u7LPPPtYWfh5vuukmy+H+YSh84SKCSN26dTN6LUZdi8NXX31luaKfu8WgOKsGAACoJjpBAAAgkYpuOizckj3ccj0cigtvrnz66aclSc2aNctD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
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
<h3 id="Split-the-Data-Into-Training-and-Test-Sets">Split the Data Into Training and Test Sets<a class="anchor-link" href="#Split-the-Data-Into-Training-and-Test-Sets">&#182;</a></h3><p>In this step we will split our dataset into <em>training</em> and <em>testing</em> subsets (in proportion 80/20%).</p>
<p>Training data set will be used for training of our model. Testing dataset will be used for validating of the model. All data from testing dataset will be new to model and we may check how accurate are model predictions.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Split data set on training and test sets with proportions 80/20.</span>
<span class="c1"># Function sample() returns a random sample of items.</span>
<span class="n">pd_train_data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">sample</span><span class="p">(</span><span class="n">frac</span><span class="o">=</span><span class="mf">0.8</span><span class="p">)</span>
<span class="n">pd_test_data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">pd_train_data</span><span class="o">.</span><span class="n">index</span><span class="p">)</span>

<span class="c1"># Convert training and testing data from Pandas to NumPy format.</span>
<span class="n">train_data</span> <span class="o">=</span> <span class="n">pd_train_data</span><span class="o">.</span><span class="n">values</span>
<span class="n">test_data</span> <span class="o">=</span> <span class="n">pd_test_data</span><span class="o">.</span><span class="n">values</span>

<span class="c1"># Extract training/test labels and features.</span>
<span class="n">num_training_examples</span> <span class="o">=</span> <span class="mi">6000</span>
<span class="n">x_train</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[:</span><span class="n">num_training_examples</span><span class="p">,</span> <span class="mi">1</span><span class="p">:]</span>
<span class="n">y_train</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[:</span><span class="n">num_training_examples</span><span class="p">,</span> <span class="p">[</span><span class="mi">0</span><span class="p">]]</span>

<span class="n">x_test</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">:]</span>
<span class="n">y_test</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[:,</span> <span class="p">[</span><span class="mi">0</span><span class="p">]]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Init-and-Train-Logistic-Regression-Model">Init and Train Logistic Regression Model<a class="anchor-link" href="#Init-and-Train-Logistic-Regression-Model">&#182;</a></h3><blockquote><p>☝🏻This is the place where you might want to play with model configuration.</p>
</blockquote>
<ul>
<li><code>polynomial_degree</code> - this parameter will allow you to add additional polynomial features of certain degree. More features - more curved the line will be.</li>
<li><code>max_iterations</code> - this is the maximum number of iterations that gradient descent algorithm will use to find the minimum of a cost function. Low numbers may prevent gradient descent from reaching the minimum. High numbers will make the algorithm work longer without improving its accuracy.</li>
<li><code>regularization_param</code> - parameter that will fight overfitting. The higher the parameter, the simplier is the model will be.</li>
<li><code>polynomial_degree</code> - the degree of additional polynomial features (<code>x1^2 * x2, x1^2 * x2^2, ...</code>). This will allow you to curve the predictions.</li>
<li><code>sinusoid_degree</code> - the degree of sinusoid parameter multipliers of additional features (<code>sin(x), sin(2*x), ...</code>). This will allow you to curve the predictions by adding sinusoidal component to the prediction curve.</li>
<li><code>normalize_data</code> - boolean flag that indicates whether data normalization is needed or not.</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Set up linear regression parameters.</span>
<span class="n">max_iterations</span> <span class="o">=</span> <span class="mi">10000</span>  <span class="c1"># Max number of gradient descent iterations.</span>
<span class="n">regularization_param</span> <span class="o">=</span> <span class="mi">10</span>  <span class="c1"># Helps to fight model overfitting.</span>
<span class="n">polynomial_degree</span> <span class="o">=</span> <span class="mi">0</span>  <span class="c1"># The degree of additional polynomial features.</span>
<span class="n">sinusoid_degree</span> <span class="o">=</span> <span class="mi">0</span>  <span class="c1"># The degree of sinusoid parameter multipliers of additional features.</span>
<span class="n">normalize_data</span> <span class="o">=</span> <span class="kc">True</span>  <span class="c1"># Whether we need to normalize data to make it more unifrom or not. </span>

<span class="c1"># Init logistic regression instance.</span>
<span class="n">logistic_regression</span> <span class="o">=</span> <span class="n">LogisticRegression</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">polynomial_degree</span><span class="p">,</span> <span class="n">sinusoid_degree</span><span class="p">,</span> <span class="n">normalize_data</span><span class="p">)</span>

<span class="c1"># Train logistic regression.</span>
<span class="p">(</span><span class="n">thetas</span><span class="p">,</span> <span class="n">costs</span><span class="p">)</span> <span class="o">=</span> <span class="n">logistic_regression</span><span class="o">.</span><span class="n">train</span><span class="p">(</span><span class="n">regularization_param</span><span class="p">,</span> <span class="n">max_iterations</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Print-Training-Results">Print Training Results<a class="anchor-link" href="#Print-Training-Results">&#182;</a></h3><p>Let's see how model parameters (thetas) look like. For each digit class (from 0 to 9) we've just trained a set of 784 parameters (one theta for each image pixel). These parameters represents the importance of every pixel for specific digit recognition.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Print thetas table.</span>
<span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">thetas</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[7]:</div>



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
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
      <th>5</th>
      <th>6</th>
      <th>7</th>
      <th>8</th>
      <th>9</th>
      <th>...</th>
      <th>775</th>
      <th>776</th>
      <th>777</th>
      <th>778</th>
      <th>779</th>
      <th>780</th>
      <th>781</th>
      <th>782</th>
      <th>783</th>
      <th>784</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>-9.415686</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>-0.021898</td>
      <td>-0.007187</td>
      <td>-0.012262</td>
      <td>-0.014120</td>
      <td>-0.006262</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-13.113449</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>-0.000822</td>
      <td>0.000052</td>
      <td>0.000039</td>
      <td>0.000043</td>
      <td>0.000120</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-7.469225</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.000299</td>
      <td>-0.000012</td>
      <td>-0.000492</td>
      <td>-0.001165</td>
      <td>-0.015479</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-7.595137</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>-0.003893</td>
      <td>-0.001736</td>
      <td>0.000030</td>
      <td>0.000134</td>
      <td>0.000107</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-10.071984</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>-0.111370</td>
      <td>0.000150</td>
      <td>-0.001469</td>
      <td>-0.039018</td>
      <td>-0.025194</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>-7.926510</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>-0.009518</td>
      <td>-0.002626</td>
      <td>-0.008151</td>
      <td>-0.046778</td>
      <td>-0.028596</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>-9.968108</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>-0.003140</td>
      <td>0.000275</td>
      <td>-0.000694</td>
      <td>-0.021697</td>
      <td>-0.013973</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>-9.840224</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.055984</td>
      <td>-0.033359</td>
      <td>0.012303</td>
      <td>0.259343</td>
      <td>-0.118382</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>-6.248424</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.000022</td>
      <td>0.000083</td>
      <td>0.000272</td>
      <td>-0.005866</td>
      <td>-0.003580</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>-7.969921</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.031976</td>
      <td>-0.006597</td>
      <td>-0.005002</td>
      <td>-0.112930</td>
      <td>0.045055</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>10 rows × 785 columns</p>
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
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># How many numbers to display.</span>
<span class="n">numbers_to_display</span> <span class="o">=</span> <span class="mi">9</span>

<span class="c1"># Calculate the number of cells that will hold all the numbers.</span>
<span class="n">num_cells</span> <span class="o">=</span> <span class="n">math</span><span class="o">.</span><span class="n">ceil</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">))</span>

<span class="c1"># Make the plot a little bit bigger than default one.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">10</span><span class="p">))</span>

<span class="c1"># Go through the thetas and print them.</span>
<span class="k">for</span> <span class="n">plot_index</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">):</span>
    <span class="c1"># Extrace digit data.</span>
    <span class="n">digit_pixels</span> <span class="o">=</span> <span class="n">thetas</span><span class="p">[</span><span class="n">plot_index</span><span class="p">][</span><span class="mi">1</span><span class="p">:]</span>

    <span class="c1"># Calculate image size (remember that each picture has square proportions).</span>
    <span class="n">image_size</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">digit_pixels</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]))</span>
    
    <span class="c1"># Convert image vector into the matrix of pixels.</span>
    <span class="n">frame</span> <span class="o">=</span> <span class="n">digit_pixels</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">image_size</span><span class="p">,</span> <span class="n">image_size</span><span class="p">))</span>
    
    <span class="c1"># Plot the number matrix.</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="n">num_cells</span><span class="p">,</span> <span class="n">num_cells</span><span class="p">,</span> <span class="n">plot_index</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">frame</span><span class="p">,</span> <span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;Greys&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="n">plot_index</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">tick_params</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span> <span class="n">which</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span> <span class="n">bottom</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">left</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">labelbottom</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">labelleft</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>

<span class="c1"># Plot all subplots.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">subplots_adjust</span><span class="p">(</span><span class="n">hspace</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span> <span class="n">wspace</span><span class="o">=</span><span class="mf">0.5</span><span class="p">)</span>
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
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAj8AAAJBCAYAAACphNSGAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDMuMC4xLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvDW2N/gAAIABJREFUeJzs3Xe0VfWd///3FkGk9y4daVJFEKQpCgJ2jDEandijYXQ0maUx49eWGBMTE0101BgziiXGSmwgiHSlSe+9dxCpinh+f+is3+zP+2XYwL33cP08H2u5ZvZrbe7d99yzz/nk3Nd+7ySXyxkAAEAsjsn3AQAAABQlFj8AACAqLH4AAEBUWPwAAICosPgBAABRYfEDAACiwuIHAABEhcXPYUiSpEqSJG8kSbI7SZKVSZJclu9jAoqLJEkGJ0kyNUmSz5Mk+Z98Hw9Q3CRJclySJH/95v1nZ5IkM5Ik6Z/v4ypOjs33ARRTj5nZF2ZW08zam9k7SZLMzOVyc/N7WECxsM7Mfmlm/czs+DwfC1AcHWtmq82sl5mtMrMBZvaPJEna5HK5Ffk8sOIiYcLzoUmSpKyZbTezk3K53KJvsiFmtjaXy92R14MDipEkSX5pZvVyudyP8n0sQHGXJMksM7s3l8u9lu9jKQ74s9ehO9HMvvzfhc83ZppZ6zwdDwAgYkmS1LSv35v460NGLH4OXTkz+yzIdphZ+TwcCwAgYkmSlDSzF8zs2VwutyDfx1NcsPg5dLvMrEKQVTCznXk4FgBApJIkOcbMhtjXHdTBeT6cYoXFz6FbZGbHJknS7P9k7YyPGwEARSRJksTM/mpfX3gzKJfL7c/zIRUrLH4OUS6X221mr5vZfUmSlE2S5DQzO9++Xn0DOIgkSY5NkqS0mZUwsxJJkpROkoQrT4FD899m1tLMzs3lcnvzfTDFDYufw3OTfX2J7iYze8nMbuQydyCz/zKzvWZ2h5n98Jv//7/yekRAMZIkSQMzu8G+HrWyIUmSXd/8d3meD63Y4FJ3AAAQFT75AQAAUWHxAwAAosLiBwAARIXFDwAAiAqLHwAAEJVDmq1RtmzZXKVKlQrrWFDMrVu3bksul6ue7+M4mlWoUCFXo0aNfB8GjlJLly7lHDqIMmXK5CpWrJjvw8BRasOGDZnOoUNa/FSqVMluuOGGwz8qfKfdfffdK/N9DEe7GjVq2G9/+9t8HwaOUoMGDeIcOoiKFSvaj370o3wfBo5SDz74YKZziD97AQCAqLD4AQAAUWHxAwAAosLNBDM65hi/TixRokSm/T755BOXjR49OrX9hz/8we2zZMmSQzhC4LtBnVcqC2/Ns38/N7VG0SlVqlSm/b766iuXfX1D9v9f2bJl3T6ffvqpy8qUKZPp61eoUMFlU6ZMcVndunVT28cdd5zbR72nqe+pbpVVsmTJTF9v796ivy8rn/wAAICosPgBAABRYfEDAACiwuIHAABE5TtTeK5WrZrLVLFqy5YtqW1V3CpfvrzLVBFMZc2bN3dZ7969XXb99dentjds2OD2USW4L774wmVffvmly1T5DCgM6jw7/vjjXVa5cmWXVa/uB7Gq5/ju3btdVrt27dT2nDlz3D779u1z2YEDB1yWVVhUVY7k6yP/jj0229uiet1Vzw+Vhc/xbt26uX2eeOIJlzVr1sxl6mKA7t27u+zkk0922aZNmw56rKp4vWfPnkyZughh27ZtB92vXLlybp+Cxic/AAAgKix+AABAVFj8AACAqLD4AQAAUSmWhWc1WVOVz1TxsH79+qntBg0auH1WrVp10H9nZjZ9+nSXjR8/3mWtWrVy2XPPPZfavuWWW9w+qvC8ePFil6lyqSrt7dq1y2Xh46YK4PjuUSXl0qVLu0yV/0OqnKjKzSpTxzFy5EiXqQsJwiLmhAkT3D7nn3++yz7//HOXqUm0q1evdllYEDUzq1mzpstQPKjXSfX+op6natqyKuurSf1hNm3aNLfP3Xff7bKXXnrJZaqkPHbsWJd99NFHLguL1uHEZzOzmTNnumzlSn/j9CuvvNJl77zzjsuaNm3qsrDwrB7HgsYnPwAAICosfgAAQFRY/AAAgKjkrfOjuiVqaKAa4KTuALt06VKXtW3b9qD7zZs3718e57/aT/3Nd/78+S5TA6fCLoIa/KR+JjW0rXXr1i5Tf5NV3yPsPKlekPr7K0MU8091CVS/TPUV1F2f1X6q//D73/8+tX3bbbdl+lo7duxwmaLuPq26eWEPr3Hjxm4f1UdS5204/NTMbP369Zn+bfg91OvYxo0bXYaiF3Z8KlWq5PZRnU/1uqv6X7feeqvLdu7c6bIsQ/xU56dfv34uUz3QrVu3ukwNAg47Pup879y5s8tatGjhMvV+de+997rsww8/dFn4fqXWB+o15UjwyQ8AAIgKix8AABAVFj8AACAqLH4AAEBUiqzwHA5iUsPT1LCmihUrukzdAb1evXqZvl5YuqxTp47bR5VGVYnxzTffdFnVqlVd9sILL7gsPF5VuFR3yVXFO1Vu7tKli8tUUTwswamvXxQDp5CmflfhEEI1LEwN9lTDMtVgzHbt2rlMDUu7+OKLU9vqXFZ3gt68ebPLVMFS3eFaHW9YJFVfa/jw4S5r06ZNpuNYs2aNy15//XWXhQVw9bqjjl/9jlFw1O80fK6uXbvW7aOGfarXRfU8VYP+evXq5bLw9XnBggVun5tuusllDz/8sMtUmf6yyy5zmXo/GTNmTGpbvR/26NHDZerCGPUeqcrN6vENC84LFy50+6i70qufKSs++QEAAFFh8QMAAKLC4gcAAESFxQ8AAIhKoRSeVeEvnM6YtdysioJVqlRx2WeffeYydSf2sIip7vA8bNgwl6lScZMmTVymyp+qvBV+34YNG7p91J2mVSFNlaXVHan79OnjsnDiqZpgm2WqLQpWlue9mtitpqBmvZu6usN1x44dXRYWLFX5UU1kVueGOm/V1N3atWu7LKTO0U6dOrlMTY8N7yptZnbNNde47D//8z9dFv4e1GRo9XOq8xsFRxWew6nM6jxTr3eq9KvKvA8++KDL1Hka3mFdnY/q+ayek9u3b3eZuku8OifDc1e9H06aNMll6lyeNWuWy9QFQL1793ZZeCeH0047ze2jJmWr33FWfPIDAACiwuIHAABEhcUPAACICosfAAAQlSMuPGcpNyu5XM5lqrilpgtv3brVZWr6o5ruGpYdVblSlbROOukkl6li3Lhx41ymSsrh9Njly5e7fdRkXjXRUpUpVdFTTRENC+Bt27Z1+6iJ2mpaLw6PKiKqsuOXX36Z2laF2XBit5lZjRo1XKYm26rnljqXw3K+Kjyr0q8qfk6ZMsVlF110kctUSTk8Pxo3buz2Uedjs2bNXKZ+B2rCszrXwrKmmrKtqNdOHB71Wjl//nyXhb9ndeHGO++84zJVjA5/72ZmEyZMcNmgQYNcNmPGjNS2ei8JS9FmZj179nSZOpdVpiYw/+QnP0lth4VwM7O//e1vLrvxxhtdpqa6z5s3L9OxhRdWLFq0yO2j1gxZ1hrfhk9+AABAVFj8AACAqLD4AQAAUWHxAwAAonLEhWdVQlJZWO5TBS9ValQlyUaNGrlMFSdPOOEEl4UlNTWpUlHl0hdffNFlaqq0+retW7dObd93331un/vvv99lagqveoyWLVuW6djCnz9r8RMFR5Vos+yXdTqten7s3bvXZatWrXKZmqwcFuBVwVeVoNX0WFWSVNPJ1ZTZ8GIFdZ516NDBZaoUrs4rVeqvWbOmy8LXLfW1VDFTXcyBw6MmdKsLV8L3DvWc7969u8sWL17sMvX7Uxe3qOJy+Lxv3ry526d69eouGzNmjMtq1arlMnUBUNOmTV32yCOPpLbbt2/v9lF3BlA/kzpf1PdU52n4s6oLgBT1mpIVn/wAAICosPgBAABRYfEDAACiwuIHAABE5YgLz1mFEzjVrehV4VkVmtRkTTWddsWKFS4Li8ZqH5WtW7fOZWo6tJoYqspy4bRNVc5W5bZWrVpl+p6qSKqKr+Ek6CVLlrh9VJmQ6bQFRz2P1LTzsDSrSrTqYgNVbs76+1Nl7N27d6e2d+7cmenrq+NQpc7XX3/dZeq1ISxnqrK+mli+Y8cOl6nnuCouqyJ3eGzhJO5vo74+Dk/p0qVdpsq2S5cuTW2rqeC/+c1vXKZKvy1atHCZmqKsLowJn6tNmjRx+2zZssVlvXr1ctnZZ5/tspkzZ7pMXQQTTmt/8skn3T5q4rp6nalcubLLWrZs6TL1mI8fPz61feKJJ7p91PTpI8EnPwAAICosfgAAQFRY/AAAgKiw+AEAAFE54sadKjaqLJzqqIrM4eRYM1/IMjP78MMPXaYKomrCZzjReM6cOW6frVu3uuy0005zmSqc1qhRw2VhqdjMbPDgwaltNXVWFerUdMz333/fZap0qQppF154YWpbTQ1euXKlyyg8F5zp06e7TD13Q6p0qMq8qijYrFkzl+3bt89lamJ0OFH23Xffdft07drVZeqiAVWwHzt2rMs6duzospA699SkWFWOVeXj8CINM/34hqVwde6p85YJz4VL/R7CC22qVKni9mnXrp3L1Gvx6aef7rJx48a5rGfPni4Lp+2rovSiRYtcdt5557ns+eefd9nQoUNddtlll7ksfA6qcrO66EFdoLNx40aXqcf3vffec1l4EcUpp5zi9lFl7w8++MBlWfHJDwAAiAqLHwAAEBUWPwAAICqFMmVLDSEMOz6qL6OGpakBgepO0+pvpj169HBZOJCsQoUKbp9wEKKZvott2Nsx090E1Tu45557Utvq76DqTvXq78zqsbzqqqtcpgZfPfXUU6ltNeBLdRPUkEocHjXkUHWqwo6PGsynhgGqzo+6+7S6Y7kalhl2Zq677jq3j3rOqyGHI0aMcJn62dUAw/DY1BA31XNTgxVV50d1oNQw1fDnUsevvn7WYYg4uCzDOM3870bto3oq6lybO3euy9Trs3ruzp49O7WtBhoOGDDAZWqg7QUXXOAyNZTxH//4h8tUjyY0adIkl6lzWb2Xqh6v2i8c6Bu+L5np17FwOOKh4JMfAAAQFRY/AAAgKix+AABAVFj8AACAqBxx4VkNWlPCopkqAKqimSpOqgFIqhit7s4elhhVuVkNPuzQoYPLTjrpJJcpqvAWDr5Sx6/ubPvGG2+4TN3pXd3BvVu3bi7L8vtjoGHRU+fHgQMH/uW2mf5dqUK1uihh/fr1LlPPj3AAoyqbqgsQwlKjmdnmzZtdpgaoqeGbYdFffS01PFSVXFWpXw07zVKiVY+ZKsyi4KiLPrK8tjVv3txlqlSsXmPDQYVmepjlqlWrXBYO/Gzbtq3bZ/Xq1S5TgwTr1avnMjUoVA0MDgeWqoKy+p5qCKsqJKuBkX379nVZeGHCD3/4Q7fPWWed5bKBAwe6LCs++QEAAFFh8QMAAKLC4gcAAESFxQ8AAIhKoUx4VuW+sBSoymKq4KWKn6rEqO4YrVSsWDG1rUqjbdq0cVlYDDPTpVF1J2hVBPvd736X2lZ3pFYlOzV1VpW2X3jhBZepAnh4t2J1h3H1O0DhUsXJLKVZ9XxWE1XVdOH58+e7TJ0L4fNe/Tt1UYI651WpWJUd1TkflqDV91TFf3Vhxfbt211Wvnx5lynha5sqe6tJ2Sg4WSaim/nzSpX81Z3N1fNIXaSiJjWrLPy+6nxXJe4FCxa4TJ3fgwYNctn/+3//z2VZ3jdVAVw9x9V0a/XaoO6WsHLlytR248aN3T5dunRxWXjniEPBJz8AACAqLH4AAEBUWPwAAICosPgBAABRKZQmqyqaheWt6tWru31effVVl1188cUuU6WvhQsXukx9j3B6syq3qYmckydPdpmaRNu+fXuXlS5d2mUdO3ZMbTdp0sTts2bNGpepQvXzzz/vsq+++splanpnOP23VKlSbh8mPBe9vXv3uiwsM2edaqvKlGpispperM6Frl27prbPPvtst48qUu7atctl55xzjsvOPfdcl6niZOfOnVPbs2bNcvuo4uSePXtcpgrVanJ1mTJlXBb+rlQxXR1by5YtXYaCo163wos31GvnjBkzXKbKvH/6059cpl7H1ZTjcCqzOt/VxSdNmzZ12aRJk1ym3ksHDx7ssvA1Zfbs2W4fdQ7t3LnTZWqCtJqcri5MeOmll1LbzzzzjNtnxIgRLnv55ZddlhWf/AAAgKiw+AEAAFFh8QMAAKLC4gcAAESlyEb3hkXBDz/80O0zYMAAl9WuXdtlakLkySef7DJVPgvLnzt27HD7qImZ3/ve91zWvHlzl6mCl5oee/7556e2Z86c6fZRE2ZVCS4sT5vpQuvGjRtdFhacVVE66/RUFBw1gTmkCs/q966msaoSdJ06dVymzoWwOK+e3+pig6VLl7pMFY3Vz6Umm4fT2tXFAJUrV3aZKpeqCb6qGK0et/BcUOeQKo2i6IWvd6qcfu+997ps6tSpLlPPBXWuqQn/Yan6n//8p9vnl7/8pcvURHR13p511lmZjiPMLrzwQrePes9R703qghr1vqzK/+F76dVXX+32ufnmm1123nnnuSwrPvkBAABRYfEDAACiwuIHAABEhcUPAACIyhEXnrNO/w2LZqosvHbtWpepKcdq8qqafLllyxaXlShRIrWtjn/gwIEuCydymunSryp/TpkyxWVhWW7ixIluH1XGrlmzpsvCn8nMbMWKFS5ThbSwZL5+/Xq3DwqXKviqLHyuhtO5zXTZVpU6w8muZmZt2rRx2ebNm122ZMmSg35Pdd6eeuqpLlu5cqXLwim8Zv4CATNfuqxbt67bR70GqCnmqmCuzm9Vgg73U4+tKmNnKbUjG/U6rkq54UUfqhisys1qSnOLFi1cpp5vH3/8scvCorEq+L7yyisua9CggctUgViV+tV+p512Wmr70Ucfdfuo9xdV9q5fv77L1M+u3ufD9+8hQ4a4fQr6TgN88gMAAKLC4gcAAESFxQ8AAIgKix8AABCVIpvwHE4+Xrx4sdtHTWOdN2+ey2rVquUyVUgeOXKkyxYuXJjaVqXG+fPnu0wVzdS/VaXiqlWrumzs2LGpbVVKVaUy9XOOHj3aZZ9//rnLVEE2LH+qib67du1yGQqOKgyrSbFhQTbrlG31PFKl3N27d7usdOnSLlu+fHlqu1u3bm4fVbhX088bNmzoMnUOqTJlWIxWx69KxSpT/1aVzlVxOZR1yi9T0guO+l2p80qVoEOqXD98+HCXvffeey7r0aOHy8JSsZnZhAkTUttqIroqLavSb/fu3V321FNPueymm25yWXiedurUye2jSv7qLgujRo1y2YknnuiySy+91GXjx49Pbaup1eocVb/jrPjkBwAARIXFDwAAiAqLHwAAEJVC6fyoIWXh3/HV3V7DPo6ZWevWrV0Wdg7MzBYtWuQy1ScIuzuq+6D+Pq++vrojtRpM+Omnn7os/BuvGo6l/g4c3snaTP8du3fv3i5T3Y9wyJz62zmKnuqlhH/vV10sNTxUPT/U3aHV1/vwww9ddsIJJ6S2ly1b5vZZtWpVpqxXr14uU+dCuXLlXBaep+r4Vc9NdW3UuaGGIaoBq+F+qpug+k5qPxQc9XsOXxefeeYZt496DW/VqpXL1HNB9V5UZyb8t+o9U70GqP3mzJnjMvW+qfqc4TmkerfqZ1fnaIcOHVz24osvukx1pbp27ZraVu9Daojpzp07XZYV73QAACAqLH4AAEBUWPwAAICosPgBAABROeLCsyqVHX/88S4L7wz78ssvu31UYUqVoNVd11944QWXqcJzODxpwYIFbp9PPvnEZY0aNXKZKrypoXCqELpv377UthqOpe6wru6WrR439XuZPXu2y8LjVYU3NViLAW2FSxVkw+F5qqSrhmWqkmR4F2UzXepv2bKly8Iiprrz+9KlS12mCsRqQJv6t3PnznVZ+JqinqeqvKoGo6nycc2aNTN9vbBorUrWqsCpfi84POp8KVOmjMvCO6VnHYyphvX9z//8j8s6d+7ssu3bt7ssfG0Ph/yZ6YKyOkfVa3Hbtm1dNmLECJeFxejnnnvO7aMGDrZv395larCuKkur9+/JkyenttV7lXpsjwSf/AAAgKiw+AEAAFFh8QMAAKLC4gcAAESlUBp3qnwWTmdUk5XVxOQmTZq4rF+/fi5Td4kPpxebmU2ZMiW1re7SrCY8r1271mVnnnmmy1SRu1mzZgc9tnbt2rl9VKFVFVCnTp3qsmnTprmsSpUqLqtdu3ZqW03uVL+rsGyKgqUe37A0q+76rO6mri5AUCVMVXavVauWy2bOnJnaViV/VcxXpf6s/3bGjBkuC0uXqiSp7lKtyqtqMm84Dd7Mny9mvgStit2qWKt+dhQcVQTetm1balvdcV0V4j/++GOXdenSxWWzZs1ymbow5pprrkltP/74426fwYMHu0y9T4TvaWZm48aNc5ma6l6vXr3Utnr9UF8rfA0w0xcvNG7c2GXq7gOTJk1Kbffp08fto16zjuSOBHzyAwAAosLiBwAARIXFDwAAiAqLHwAAEJVCKTyrwlhY7tuwYYPbR01PVZkqeKkJzPPmzXNZWIyuWrWq20dNTK5fv77LJkyY4DJVGFaTLy+++OKDfq1woq+Z2fLly12mys3lypVzWceOHV22ZMmS1Lb63alirSqKo+CownM4wViVaNVzTV0MoCabq6nPO3fudFn4fFPTXm+66aZMX0sVRNXzWZVLwwsT1AUT6nmqCsmqSKqKqqpEO3/+/NT2q6++6va57bbbXMZFA4VLvSeEZXc1zX/dunUuU9OW1YTuBx54wGVDhgxxWTgVXZ1D6nV3zJgxLqtRo4bL7r//fpdt3LgxUxZSFxKoiwbCKc1mZt26dXOZOj/C9YF6batYsaLL1GOUFZ/8AACAqLD4AQAAUWHxAwAAosLiBwAARKVQCs/79+93WTghWU0vVtRUYpWpItiuXbtcdvLJJ6e2a9as6fYJC4xmurCopseq0qUqkoYTntUUaFUge//9910W/kxm2YqqZnr6bygs2qLwqWJtWICvVKmS20cVGFV5MJx0a6af9+q5G5aZVRlUTV5VBX51HLfeeqvL1M8wZ86c1LYqoP7lL39xmZrMrianq4st1PGG2rRp4zJVslaT01Fw3nrrLZeF7x1lypRx+6jnwurVq1324YcfZtpPvdeFF9Coi2zUpHN1QU316tVd9s4777hMnafly5dPbb/99ttun8cee8xlo0ePdpk6/9R5q95zw9cLdeGN+lpMeAYAAMiIxQ8AAIgKix8AABAVFj8AACAqhVJ4VmXNcOKwmryqCsq1a9d2mZpYqwrDqmAZFsZUCVgVSVu0aOGyBg0auEwVtdQ066FDh6a2VcnuhBNOcNlVV13lsnHjxrlM/Q5UuS/cT5Xz6tSp47JPP/3UZShaqvg/cuRIl6mi46mnnuqyiRMnuuyLL75wWViSVFOl1YRxNTFZlfVffvlll6nXhmXLlqW2VZG5Vq1aLlOvC+p8URcDqInw4e+hVatWbp8jmUSLw6NeP8P3EzU1eMWKFS6bO3euy84//3yXqa+nnjPr169Pbaui9KRJk1zWv39/l4UXz5j5iclmusAf3llg4MCBbp/hw4e7bM+ePS4bMGCAy9Q0Z3VOhhOuwwukzPSFVOo1MCs++QEAAFFh8QMAAKLC4gcAAESFxQ8AAIhKoRSelXBapSoYqtKy2i/rZFs1mbhx48apbVVGU/9OFZkVNYXyggsucFk43VWVub788kuXLV261GWqyFyiRAmXqanPIfWzU24ueup3H/4e1O/zvPPOc9nmzZtdpgqRt99+u8vUBQFhEbNevXpun02bNrlMTYtWZX01Iblbt24uC895VYqeOnWqy1ThcuvWrS5TE5hVFk5vViVxHB3Cc2HdunVunxNPPNFll112mcvUhSzq/UqVg8OpzMuXL3f7qPKx+lrhtGgzs86dO7vs+eefd1l4Z4QLL7zQ7aNeZ9RrytixY12mznn1c4UXaqgLBNR5eyT45AcAAESFxQ8AAIgKix8AABCVIuv8hNQAMfX3THU3ZLWfGiymsnAokvqbrxoaVbduXZepu7qrIVfq77mNGjVKbau7RW/fvt1lWanOiBosGXaDsvSCkB/hAErV61LdNDXsLRxUaKbvIq2e9z169Ehtqx7MlClTXKb+jq/OFzXEVHUHwg6U6tpcccUVLlPdoKx3WM8yIJG7tR+9wruAq9dE1dtUdywPX8PN9Dmp3uuyDMZUd3BXnUz1frhw4UKXde/e3WXhubxv376DHquZPg8qV67sMvV6NH36dJeFHaii6M3xyQ8AAIgKix8AABAVFj8AACAqLH4AAEBU8lZ4VkP9spab1V2ks9x92swPX1OFSzVsUR1beEdcM136UndKD+9aqx4PVW5T1H7q66kyG4oP9TsNhYVOM11+VwPa1L9VxcbwnFTP744dO7pMXUigBiTWqFHDZeqO1OHPpe4an7UUrn529W/Va4q6WAFHp/B9Qr1vqNdJ9VxQg3XV80gJzxn171TJWp1rqmCvSttqv/BcUOdG1gG/6jFSQx9Vlo/BoHzyAwAAosLiBwAARIXFDwAAiAqLHwAAEJW8FZ6VrIVcVdxSd2VWEzKzlLdUyVNRRVKVqUJyWLRWx6VKYKpUpjBl9rtPFaDVeVDQ1q9ff9B95s6dm+lrqQsOVFlTnVeFTZ2TlJu/+46k9JuVuminIBX08R7u91QF7Xycywqf/AAAgKiw+AEAAFFh8QMAAKLC4gcAAEQlUdMWv3XnJNlsZn5MK/C1Brlcrnq+D+JoxjmEg+AcOgjOIRxEpnPokBY/AAAAxR1/9gIAAFFh8QMAAKLC4gcAAESFxQ8AAIgKix8AABAVFj8AACAqLH4AAEBUWPwAAICosPgBAABRYfEDAACiwuIHAABEhcUPAACICosfAAAQFRY/AAAgKix+AABAVFj8AACAqLD4AQAAUWHxAwAAosLiBwAARIXFDwAAiAqLHwAAEBUWPwAAICosfgAAQFRY/AAAgKiw+AEAAFFh8QMAAKLC4gcAAESFxQ8AAIgKix8AABAVFj8AACAqLH4AAEBUWPwAAICosPgBAAAyPWHNAAAgAElEQVRRYfEDAACiwuIHAABEhcUPAACICosfAAAQFRY/AAAgKix+AABAVFj8AACAqLD4AQAAUWHxAwAAosLiBwAARIXFDwAAiAqLHwAAEBUWPwAAICosfgAAQFRY/AAAgKiw+AEAAFFh8QMAAKLC4gcAAESFxc9hSJLk+SRJ1idJ8lmSJIuSJLk238cEFEdJkjRLkmRfkiTP5/tYgOIkSZLR35w7u775b2G+j6k4YfFzeH5tZg1zuVwFMzvPzH6ZJMnJeT4moDh6zMym5PsggGJqcC6XK/fNf83zfTDFCYufw5DL5ebmcrnP/3fzm/+a5PGQgGInSZJLzexTM/sg38cCIC4sfg5TkiSPJ0myx8wWmNl6M3s3z4cEFBtJklQws/vM7LZ8HwtQjP06SZItSZJMSJKkd74Ppjhh8XOYcrncTWZW3sx6mNnrZvb5v/4XAP6P+83sr7lcbk2+DwQopm43s8ZmVtfMnjKzt5Ik4S8QGbH4OQK5XO5ALpcbb2b1zOzGfB8PUBwkSdLezM40sz/k+1iA4iqXy03K5XI7c7nc57lc7lkzm2BmA/J9XMXFsfk+gO+IY43OD5BVbzNraGarkiQxMytnZiWSJGmVy+U65vG4gOIsZ2ZJvg+iuOCTn0OUJEmNJEkuTZKkXJIkJZIk6WdmPzBKm0BWT9nX/2Oh/Tf/PWFm75hZv3weFFBcJElSKUmSfkmSlE6S5NgkSS43s55mNizfx1Zc8MnPocvZ13/iesK+XjyuNLP/yOVy/8zrUQHFRC6X22Nme/53O0mSXWa2L5fLbc7fUQHFSkkz+6WZtTCzA/b1hTcX5HK5RXk9qmIkyeVy+T4GAACAIsOfvQAAQFRY/AAAgKiw+AEAAFFh8QMAAKLC4gcAAETlkC51L1OmTK5ixYqFdSwo5jZs2LAll8tVz/dxHM3KlSuXq1KlSr4PA0ep1atXcw4dRNmyZXOVK1fO92HgKLV27dpM59AhLX4qVqxo11xzzeEfFb7TfvWrX63M9zEc7apUqWI/+9nP8n0YOErdcsstnEMHUblyZRs8eHC+DwNHqZ///OeZziH+7AUAAKLC4gcAAESF21sUgW9u3piSZbJ2iRIlMn39r7766rC+PnA4SpcundquVq2a2+eLL75w2bZt2zJ9fdUrLFu2rMv27NmT2s769RV1voQ/p5lZyZIlXfbZZ58d9vcFzA7/PcLM7Jhj/GcYKvvyyy8P/cC+5Wsp6niP5vchPvkBAABRYfEDAACiwuIHAABEhcUPAACISrEsPB9JASsslqlS8XHHHeeyOnXquGzdunUu27dvn8tUITn8GVThTWUHDhxw2dFcKkPRynpuHHusP/UrVarksp07d7qsevX0/LAaNWq4fVasWOEyVWRu0KCBy0qVKuWyUaNGuax///6p7c2bN2c6DnV+165d22W7d+922caNG10G/C/1mq1K8lles9X5qL5WhQoVXKbKzXv37nVZ+Drw6aefZvp36mIA9T63f/9+l33++ecuywc++QEAAFFh8QMAAKLC4gcAAESFxQ8AAIjKUVV4VkVHNSlWlTXDEqaZWZkyZVw2fvz41Hbnzp3dPk899ZTLBgwY4LLFixe7rEOHDi5TJbjwrsQzZ850+6i7f9evX99l6jFSxetdu3Zl+rf4blHPPzUxWZUwVTk4zNRFA6oE3a5dO5ctWLDAZc2bN3dZltJlkyZN3D7qZ1+7dq3L3n//fZepErT6HuXLl09tz5492+2DOKjzpV69ei7bvn17anvr1q1un9WrV7tMvc+pEn6zZs1cpgrU4XuMeg+eM2eOyzZt2uSyqlWruky9v6gydvhzFcXUdD75AQAAUWHxAwAAosLiBwAARKXIOj/hHZgVNfBMDfVT3ZWHHnrIZVdffbXLwiFOCxcudPuEw9PM9N9LO3bs6LLhw4e77IQTTnBZOPwp7A2YmY0YMcJl3bt3d1nXrl1d9vjjj7vsxRdfdNmf//zn1Pbh3vkXRU8NNFy6dKnLVNdG/W1//fr1Llu1apXLwnNB3dVddRPUuayGqr355psuU+fali1bUtuqc7Bjxw6XTZgwwWWq36N6QP/2b//msj/+8Y+p7V/84hdun7lz57oM+afOITVIUHV51FC/jz/+2GXq9blp06ap7XHjxrl9VGdVDQhUXT3VF1Ln6ciRI10Wuuqqq1w2dOhQl6nXD9UHVMNON2zYkNpWXcAWLVq4TD1GWfHJDwAAiAqLHwAAEBUWPwAAICosfgAAQFQKpfCs7vgaDlVT5StV+lIDDcNylJnZRRdd5LK+ffu6rHHjxqntyZMnu31U0bhmzZqZvn6vXr1cpoYhtm7dOrWtCnWqjN22bVuXqeKdKoDfddddLjvllFNS26rgqr6+ylBw1PM+HBhWt25dt48q+G7bts1lqnSo7sB84oknuiwcqqYGGk6bNs1lAwcOdJkqPKuLC1TpMhwe17t370xfK3zOm+mCpbpQIRxOZ2Z24YUXprbnzZvn9lHFWs6h/FPvVeq9SQ23VMMs1VDNiRMnuiw8vxs1auT2Ue85b7/99kG/lpl+PxwyZIjLwtcUVcxXj1HWQcPqfFF3oQ+HGqqfXWU7d+50WVZ88gMAAKLC4gcAAESFxQ8AAIgKix8AABCVQik8Dxs2zGWXXHJJaltNoFSTlR999FGXXXPNNS5ThcV///d/d1k4AVeVJK+99lqXjRo1ymWqEDlmzBiXqWJjuXLlUtuqbPrwww+77A9/+IPLLr/8cpepO/GqOweHBWpVji2KO+wiTU0uDadvq3K6mqR++umnu0xNOVZl6U6dOrksnICrpiP/x3/8h8uyXtCgitGq6L9ixYqDHoea0qzKperO2KeeeqrLnn76aZeFj5E6DjXpVmUoWqqIrt6b9u3b57Lw+Wem7+CuSrlhqVqdy+o9rX79+i6bOXOmyx544AGXqfL/HXfckdpeuXKl20cVpdXjoc7l5s2bu0wVqMPzT/1e1IVDderUcVlWfPIDAACiwuIHAABEhcUPAACICosfAAAQlSMuPKsSrZqg2qVLl9T2iy++6PYJp02amXXv3t1lamJmy5YtXRZOczYz+/Wvf53aVkXjjz76yGWq+PnWW2+5LPw5zcw+//xzl61Zsya1vXz5crfP8OHDM2VXX321y9Sk0Ztvvtll4ZTgypUru33UFF4UnFKlSrlMlczDgqz6d+p3pUq/qiSvpseOHDnSZeH5PX/+fLePKmYef/zxLvvBD37gslwu57JatWq5bMmSJaltdVGCKo6rqe5qkrV6PVLn9969e1PbW7ZscfuoMqg613B41Oudeh6Fk/QbNGjg9pk+fbrLNm/e7LJu3bq57IUXXnBZOAHczGzo0KGpbXVuqEx9z/A8MNNTqvv06eOy8H1YTWRWRenw4gszPYFZlZRVkbtdu3ap7fCCIDOzc845x2Xq9SkrPvkBAABRYfEDAACiwuIHAABEhcUPAACIyhEXntVt7FXZMZwS+eabb7p9VMlJTV5t2LChy1QhuVevXi4LC17z5s1z+6jsiiuucFmNGjVcpiYkv/HGGy5r3bp1art8+fJun759+7rsggsucNmzzz7rsipVqrhMTeUMS3VqGqkqa6rCGw7PgQMHXKYKnG3atEltjxgxwu2jpgu3b9/eZWoSuSoVq+MIC/xly5Z1+6jSrzo2NSVXPbcqVqzosnXr1qW2VRl59+7dLlPl1RkzZrhMlaXVeRqWth977DG3j7ogQz1uODyq3BxezGHmH3P1Oqky9fXVe5+aXrxp0yaXDRgwILWtLrJR74dqEvR1113nMvX1li1b5rLwIgFV/FdTlNXFBU2bNnWZWguo5314oYYqSocXFpjpAnhWfPIDAACiwuIHAABEhcUPAACICosfAAAQlSMuPKsyrCqHrV+/PrV9ySWXuH2qVq3qMjUFtVmzZi6bNm2ay9SkziuvvDK1/cc//tHt8/jjj7tMFR1V4TSc3Gymp0iHRTA10VdN8L322mtd9qMf/chlixYtctmkSZNc9qtf/Sq1HU5ANdMlvl27drkMh6dkyZIuU1PB9+zZk9pW55k6H1XhUn1P9W/VRQMffPBBaludj+pcVtPJVSFSFVXV5NlGjRqltlVhO5yka6ZLkqNHj3ZZixYtXKYeo/BnPeYY/78p69Wr5zL1WoGCs3btWpeFF6mo8q266GPDhg0H/Vpm2d8Ply5detDvGU50N9Pn8oQJE1ymLm5RRe4nn3wytf3aa6+5fdSk87PPPttls2fPzvQ9X331VZeFFyb85Cc/cfuoydDqgoms+OQHAABEhcUPAACICosfAAAQFRY/AAAgKkdceFbFSTUh+ac//Wlqe/78+W6fcePGuUyVB9WEVjVdUk18DScaqxKwMmXKFJd16NDBZXPmzHFZnz59XBZOtFSFupUrV7rsrrvucpkqlc2dO9dlqhC6evXq1LaaqM0058KlHl/1vA+fM+eee26mrz916lSXqeebKh9v3brVZWH5WBX61STaU045xWWqGK0uVFCTpsOyoyotqzK2+tkrVKjgsnCCtJnZaaed5rLLL788tf3QQw+5fbK+tqFwhc/d5cuXu33atm3rssaNG7ts5MiRLvvqq69c9sknnxw0O/PMM90+qrD97rvvuuyRRx5xmSoCZzn/Tj75ZLePmnSupkWr90P1/tqvXz+XhYXnn/3sZ26f+++/32Xq8c6Ksw8AAESFxQ8AAIgKix8AABCVI+78qL+5hd0EM7N77rkntX3DDTe4fdQgQfW3+I4dO7pMDST77//+b5eFd6ht1aqV20fd8Vp1B9SQwxNOOMFl6u68YZdCPY5q0J0aOqfulq36G+rvr+FjrgZyqb6F2g+HR3V+1ICzcNhY2F8z0+ee+jv+e++95zLV1evbt6/Lxo4dm9resWOH20cNYxs0aJDLVK9m8uTJLlMD1MJM/UyPPvqoy6644gqXqYF1auBb9+7dXRYOClW/A3UO0aUremGfZ/z48W4f9bt6/fXXXda5c2eXqXNICQdtqk5Y//79XRYO9jTTPdMGDRq47Le//a3L2rVrl9o+55xz3D6qU9qpUyeXzZo1y2VXXXWVy9RA3/BxU31X9XtRr5NZ8ckPAACICosfAAAQFRY/AAAgKix+AABAVI648Kzu+KqKYOFgMVUKVAPEVFlTDTNTw9hUmTksmqki5YEDB1wWljzN9JA5VdRSxcawVH3RRRe5fcK7eJvpEuaNN97oMlUUV2XpcJCW+tlRuNRjXrp0aZeFg8BUqVg9TwcOHOgyVYhftGiRy+69916XhYXFIUOGuH3CCwvMdBm0ZcuWLlNFf3VX9HCo2iuvvOL22bt3r8vUnbdVWVrdXV79rhYvXpzaPvHEE90+KlODXlFwVEE2PGfWr1/v9lEXEmzZssVlEydOdJkahtikSROXhXdxVyX/JUuWuEwVmdV5qy68URcKhRfLqPdRVWQOi9LfdmzqdUy9NoTn0Hnnnef2UWuGI8EnPwAAICosfgAAQFRY/AAAgKiw+AEAAFEplAnPqkQWFhZvueUWt48qBapprOqOtWrypSp1ht+3bNmybh81zVmVH4cNG+YyNXFSlSTDEuqFF17o9lGPh7pTvSq0lixZ0mVr1qxxmSqXomip54cqXVasWDG1/cADD7h9rrvuOpepCwTUXdeXLl3qMlVODO9Gru6Srp5/6m7nCxcudNm+fftcpi4aCO+qraYvq0L1ww8/7DJ1HvTu3dtlM2bMcFlYVlWlUTURF4VLFZ7DiwbU+4aaaHzGGWe4bMGCBS5r3769y4YOHeqyyy+/PLWtysirV692WfgaYKbv1q7OW3VObty4MbWtLl5QdyhQJeiuXbu6TN3pXd0doHr16qntWrVquX0++OADlx0JPvkBAABRYfEDAACiwuIHAABEhcUPAACIyhEXnlV5SWVhgbN///5unyuvvNJlaoK0KoI988wzLgvLbep7TJo0ye2jStyqQKZK0GrCsypBh//2T3/6k9tHlTVvvfVWlz366KMue/zxx12mCtrhlOpt27a5fVTZVP2OUXC2b9/ush07dqS2e/bs6fYJJ8eamb355psuU2V6VfT/+OOPXRZOSVfF4HBi67cdR6VKlVymzr933nnHZeHUXTURd8KECS5T09RVwVJNyVVT13/84x+ntl9++WW3j5p0i8KlnkfhlGBVdFfvTeoim6ZNm7qsZs2aLuvbt6/L7rnnntT2oEGD3D7hJHUzXdBW57J6/VDvTeH7srqgZv/+/S5T75uqLP3RRx+5TL1u/e53v0ttDx482O2jCtvq2LLikx8AABAVFj8AACAqLH4AAEBUWPwAAICoHHHhOauwIKtKYNOmTXPZDTfc4DI1ubNatWoue//9910WFkLVxExVWLzppptc9vTTT7usV69eLqtRo4bLmjRpktquXbu22+e+++5zmSrjqZ/9iSeecNm4ceNcFhY4w+My08U7FC5V5At/V8ce609fNS361FNPdZmabB5ObjbTpfvwudq6dWu3z9ixY122a9cul/3jH/9wmSqqqnOoTZs2qe27777b7XPXXXe5TJWb1eOhpmCrUnh4YYUqSpcpU8ZlnFdFL3wfUs95NaFbTcdXz4VRo0a5LJyibOYnQauvpS6UUe996o4KakJ8w4YNXRb+rCNGjHD7qAt71NcPpzSrr29m9uyzz7osfL0bPny420edVxSeAQAAMmLxAwAAosLiBwAARIXFDwAAiMoRF55ViVEVMcOi1rJly9w+69atc5kqMXbo0MFlnTp1cpkqVS9atCi1rSZIt2rVymXly5d32cCBA10WljDNzObMmeOycGKompipiqSqtDZ58mSXqam7o0ePdllY1qxQoYLbR00NZsJzwSlVqlSm/cKy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V6JEidR2+/bt3T7qPWHQoEEuUyX8IUOGuEwVjadNm3bQfQYPHuyy8PXaTD93VWlbTbwOzw917rVr185lYcnfTF/soy5iUo95eF61bdvW7aPeW9V7fFZ88gMAAKLC4gcAAESFxQ8AAIgKix8AABCVIis8H3PMMf9y20wXOFXxU01lVgUsVRg++eSTU9vz5s1z+6jptNWqVcv09VW5VJVGw0mjqoxWpUoVl6nHQxXv1HFkeYxUUbVfv34uO5KiGQ4uLGaamZ122mmpbfU7VhPR1fNPlQdVmVKdC2FxWRUi1XOyQoUKLlNlb1UqVt9jxIgRB/2eajqtKoiqafDdu3d3mbowoWHDhqltNZldUecaClf4Ojt79my3zyWXXOIyNU19+/btLrvjjjtcpor+4dT8v/71r26fsWPHukxNPm7durXLVHFZvdedddZZqW1V9v7ggw9cFr6Pmun3JnUxhLrIYeHChf/yuMzM5s6d67IjudMAn/wAAICosPgBAABRYfEDAACiwuIHAABEpcgKz+H0VVUWLlu2rMtUMfqUU05x2fz5812mJhOHJbKweGxmduWVV7pMFavUpMq9e/e6TBW069evn9resWOH20dRky83b97ssp07d7qsVKlSLlu5cmVqWz22qpSKgrN//36XqWnF4XNQlXRVCVMV51evXu2y0qVLu0w9x8MJz0uXLnX7qEx9fVX6VcVl9byfNWtWajuc3m5mdvzxx7vs448/dtnAgQNdpqjXrfDxVd9zz549mb4+ipYq5B44cMBlakq/Om9r1qzpMlWWDidGq5K/mkQ+atQol23YsMFl6rVePQfD80+VotVFA2Fh20w/HmrStJrWfumll6a2TzjhBLePKjwfCT75AQAAUWHxAwAAosLiBwAARIXFDwAAiEqRFZ5DXbp0cZkqlanipCo+rVq1ymWqpBwWgadNm+b2adCggcvCKa5muhh32WWXuWzYsGEuW758eWr79NNPd/uoEvdDDz3kMjUJ9OWXX3aZKmv26dMnta0K5qo4Tgm64KhysxI+5lu3bnX7qIsG1MRhNUFaTQBXJckWLVqktl9//XW3j5oWPXLkSJepiwFatmzpMjXN+oYbbkhtz5kzx+0TFkvNzNatW+eyk046yWVqunV43pr5KcETJkxw+6gLCdTrBwpXOKFbXaDy0UcfuUxN4H/vvfdcporLw4cP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
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
<h3 id="Analyze-Gradient-Descent-Progress">Analyze Gradient Descent Progress<a class="anchor-link" href="#Analyze-Gradient-Descent-Progress">&#182;</a></h3><p>The plot below illustrates how the cost function value changes over each iteration. You should see it decreasing.</p>
<p>In case if cost function value increases it may mean that gradient descent missed the cost function minimum and with each step it goes further away from it.</p>
<p>From this plot you may also get an understanding of how many iterations you need to get an optimal value of the cost function.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Draw gradient descent progress for each label.</span>
<span class="n">labels</span> <span class="o">=</span> <span class="n">logistic_regression</span><span class="o">.</span><span class="n">unique_labels</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">label</span> <span class="ow">in</span> <span class="nb">enumerate</span><span class="p">(</span><span class="n">labels</span><span class="p">):</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">costs</span><span class="p">[</span><span class="n">index</span><span class="p">])),</span> <span class="n">costs</span><span class="p">[</span><span class="n">index</span><span class="p">],</span> <span class="n">label</span><span class="o">=</span><span class="n">labels</span><span class="p">[</span><span class="n">index</span><span class="p">])</span>

<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Gradient Steps&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Cost&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">()</span>
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
<h3 id="Calculate-Model-Training-Precision">Calculate Model Training Precision<a class="anchor-link" href="#Calculate-Model-Training-Precision">&#182;</a></h3><p>Calculate how many of training and test examples have been classified correctly. Normally we need test precission to be as high as possible. In case if training precision is high and test precission is low it may mean that our model is overfitted (it works really well with the training data set but it is not good at classifying new unknown data from the test dataset). In this case you may want to play with <code>regularization_param</code> parameter to fighth the overfitting.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Make training set predictions.</span>
<span class="n">y_train_predictions</span> <span class="o">=</span> <span class="n">logistic_regression</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_train</span><span class="p">)</span>
<span class="n">y_test_predictions</span> <span class="o">=</span> <span class="n">logistic_regression</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_test</span><span class="p">)</span>

<span class="c1"># Check what percentage of them are actually correct.</span>
<span class="n">train_precision</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">y_train_predictions</span> <span class="o">==</span> <span class="n">y_train</span><span class="p">)</span> <span class="o">/</span> <span class="n">y_train</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">*</span> <span class="mi">100</span>
<span class="n">test_precision</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">y_test_predictions</span> <span class="o">==</span> <span class="n">y_test</span><span class="p">)</span> <span class="o">/</span> <span class="n">y_test</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">*</span> <span class="mi">100</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Training Precision: </span><span class="si">{:5.4f}</span><span class="s1">%&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">train_precision</span><span class="p">))</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Test Precision: </span><span class="si">{:5.4f}</span><span class="s1">%&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">test_precision</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Training Precision: 96.9667%
Test Precision: 89.8500%
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Plot-Test-Dataset-Predictions">Plot Test Dataset Predictions<a class="anchor-link" href="#Plot-Test-Dataset-Predictions">&#182;</a></h3><p>In order to illustrate how our model classifies unknown examples let's plot first 64 predictions for testing dataset. All green digits on the plot below have been recognized corrctly but all the red digits have not been recognized correctly by our classifier. On top of each digit image you may see the class (the number) that has been recognized on the image.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># How many numbers to display.</span>
<span class="n">numbers_to_display</span> <span class="o">=</span> <span class="mi">64</span>

<span class="c1"># Calculate the number of cells that will hold all the numbers.</span>
<span class="n">num_cells</span> <span class="o">=</span> <span class="n">math</span><span class="o">.</span><span class="n">ceil</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">))</span>

<span class="c1"># Make the plot a little bit bigger than default one.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">15</span><span class="p">,</span> <span class="mi">15</span><span class="p">))</span>

<span class="c1"># Go through the first numbers in a test set and plot them.</span>
<span class="k">for</span> <span class="n">plot_index</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">):</span>
    <span class="c1"># Extrace digit data.</span>
    <span class="n">digit_label</span> <span class="o">=</span> <span class="n">y_test</span><span class="p">[</span><span class="n">plot_index</span><span class="p">,</span> <span class="mi">0</span><span class="p">]</span>
    <span class="n">digit_pixels</span> <span class="o">=</span> <span class="n">x_test</span><span class="p">[</span><span class="n">plot_index</span><span class="p">,</span> <span class="p">:]</span>
    
    <span class="c1"># Predicted label.</span>
    <span class="n">predicted_label</span> <span class="o">=</span> <span class="n">y_test_predictions</span><span class="p">[</span><span class="n">plot_index</span><span class="p">][</span><span class="mi">0</span><span class="p">]</span>

    <span class="c1"># Calculate image size (remember that each picture has square proportions).</span>
    <span class="n">image_size</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">digit_pixels</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]))</span>
    
    <span class="c1"># Convert image vector into the matrix of pixels.</span>
    <span class="n">frame</span> <span class="o">=</span> <span class="n">digit_pixels</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">image_size</span><span class="p">,</span> <span class="n">image_size</span><span class="p">))</span>
    
    <span class="c1"># Plot the number matrix.</span>
    <span class="n">color_map</span> <span class="o">=</span> <span class="s1">&#39;Greens&#39;</span> <span class="k">if</span> <span class="n">predicted_label</span> <span class="o">==</span> <span class="n">digit_label</span> <span class="k">else</span> <span class="s1">&#39;Reds&#39;</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="n">num_cells</span><span class="p">,</span> <span class="n">num_cells</span><span class="p">,</span> <span class="n">plot_index</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">frame</span><span class="p">,</span> <span class="n">cmap</span><span class="o">=</span><span class="n">color_map</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="n">predicted_label</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">tick_params</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span> <span class="n">which</span><span class="o">=</span><span class="s1">&#39;both&#39;</span><span class="p">,</span> <span class="n">bottom</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">left</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">labelbottom</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">labelleft</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span>

<span class="c1"># Plot all subplots.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">subplots_adjust</span><span class="p">(</span><span class="n">hspace</span><span class="o">=</span><span class="mf">0.5</span><span class="p">,</span> <span class="n">wspace</span><span class="o">=</span><span class="mf">0.5</span><span class="p">)</span>
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
    </div>
  </div>
</body>

 


</html>
