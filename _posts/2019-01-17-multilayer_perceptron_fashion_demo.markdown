---
layout: none
permalink: /tutorial/multilayer_perceptron_fashion
---
<html>
<head><meta charset="utf-8" />

<title>multilayer_perceptron_fashion_demo</title>

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
<h1 id="Neural-Network-(Multilayer-Perceptron)-Demo">Neural Network (Multilayer Perceptron) Demo<a class="anchor-link" href="#Neural-Network-(Multilayer-Perceptron)-Demo">&#182;</a></h1><p><em>Source: 🤖<a href="https://github.com/trekhleb/homemade-machine-learning">Homemade Machine Learning</a> repository</em></p>
<blockquote><p>☝Before moving on with this demo you might want to take a look at:</p>
<ul>
<li>📗<a href="https://github.com/trekhleb/homemade-machine-learning/tree/master/homemade/neural_network">Math behind the Neural Networks</a></li>
<li>⚙️<a href="https://github.com/trekhleb/homemade-machine-learning/blob/master/homemade/neural_network/multilayer_perceptron.py">Neural Network Source Code</a></li>
</ul>
</blockquote>
<p><strong>Artificial neural networks (ANN)</strong> or connectionist systems are computing systems vaguely inspired by the biological neural networks that constitute animal brains. The neural network itself isn't an algorithm, but rather a framework for many different machine learning algorithms to work together and process complex data inputs. Such systems "learn" to perform tasks by considering examples, generally without being programmed with any task-specific rules.</p>
<p>A <strong>multilayer perceptron (MLP)</strong> is a class of feedforward artificial neural network. An MLP consists of, at least, three layers of nodes: an input layer, a hidden layer and an output layer. Except for the input nodes, each node is a neuron that uses a nonlinear activation function. MLP utilizes a supervised learning technique called backpropagation for training. Its multiple layers and non-linear activation distinguish MLP from a linear perceptron. It can distinguish data that is not linearly separable.</p>
<blockquote><p><strong>Demo Project:</strong> In this example we will train clothes classifier that will recognize clothes types (10 categories) from <code>28x28</code> pixel images using simple multilayer perceptron.</p>
</blockquote>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># To make debugging of multilayer_perceptron module easier we enable imported modules autoreloading feature.</span>
<span class="c1"># By doing this you may change the code of multilayer_perceptron library and all these changes will be available here.</span>
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
<li><a href="https://github.com/trekhleb/homemade-machine-learning/blob/master/homemade/neural_network/multilayer_perceptron.py">neural_network</a> - custom implementation of multilayer perceptron</li>
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

<span class="c1"># Import custom multilayer perceptron implementation.</span>
<span class="kn">from</span> <span class="nn">homemade.neural_network</span> <span class="k">import</span> <span class="n">MultilayerPerceptron</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Load-the-Data">Load the Data<a class="anchor-link" href="#Load-the-Data">&#182;</a></h3><p>In this demo we will use a sample of <a href="https://www.kaggle.com/zalando-research/fashionmnist">Fashion MNIST dataset in a CSV format</a>.</p>
<p>Fashion-MNIST is a dataset of Zalando's article images—consisting of a training set. Each example is a 28x28 grayscale image, associated with a label from 10 classes. Zalando intends Fashion-MNIST to serve as a direct drop-in replacement for the original MNIST dataset for benchmarking machine learning algorithms. It shares the same image size and structure of training and testing splits.</p>
<p>Instead of using full dataset with 60000 training examples we will use cut dataset of just 5000 examples that we will also split into training and testing sets.</p>
<p>Each row in the dataset consists of 785 values: the first value is the label (a category from 0 to 9) and the remaining 784 values (28x28 pixels image) are the pixel values (a number from 0 to 255).</p>
<p>Each training and test example is assigned to one of the following labels:</p>
<ul>
<li>0 T-shirt/top</li>
<li>1 Trouser</li>
<li>2 Pullover</li>
<li>3 Dress</li>
<li>4 Coat</li>
<li>5 Sandal</li>
<li>6 Shirt</li>
<li>7 Sneaker</li>
<li>8 Bag</li>
<li>9 Ankle boot</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Load the data.</span>
<span class="n">data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;../../data/fashion-mnist-demo.csv&#39;</span><span class="p">)</span>

<span class="c1"># Laets create the mapping between numeric category and category name.</span>
<span class="n">label_map</span> <span class="o">=</span> <span class="p">{</span>
    <span class="mi">0</span><span class="p">:</span> <span class="s1">&#39;T-shirt/top&#39;</span><span class="p">,</span>
    <span class="mi">1</span><span class="p">:</span> <span class="s1">&#39;Trouser&#39;</span><span class="p">,</span>
    <span class="mi">2</span><span class="p">:</span> <span class="s1">&#39;Pullover&#39;</span><span class="p">,</span>
    <span class="mi">3</span><span class="p">:</span> <span class="s1">&#39;Dress&#39;</span><span class="p">,</span>
    <span class="mi">4</span><span class="p">:</span> <span class="s1">&#39;Coat&#39;</span><span class="p">,</span>
    <span class="mi">5</span><span class="p">:</span> <span class="s1">&#39;Sandal&#39;</span><span class="p">,</span>
    <span class="mi">6</span><span class="p">:</span> <span class="s1">&#39;Shirt&#39;</span><span class="p">,</span>
    <span class="mi">7</span><span class="p">:</span> <span class="s1">&#39;Sneaker&#39;</span><span class="p">,</span>
    <span class="mi">8</span><span class="p">:</span> <span class="s1">&#39;Bag&#39;</span><span class="p">,</span>
    <span class="mi">9</span><span class="p">:</span> <span class="s1">&#39;Ankle boot&#39;</span><span class="p">,</span>
<span class="p">}</span>

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
      <th>pixel1</th>
      <th>pixel2</th>
      <th>pixel3</th>
      <th>pixel4</th>
      <th>pixel5</th>
      <th>pixel6</th>
      <th>pixel7</th>
      <th>pixel8</th>
      <th>pixel9</th>
      <th>...</th>
      <th>pixel775</th>
      <th>pixel776</th>
      <th>pixel777</th>
      <th>pixel778</th>
      <th>pixel779</th>
      <th>pixel780</th>
      <th>pixel781</th>
      <th>pixel782</th>
      <th>pixel783</th>
      <th>pixel784</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
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
      <th>1</th>
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
      <th>2</th>
      <td>6</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>30</td>
      <td>43</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
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
      <th>5</th>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>4</td>
      <td>5</td>
      <td>5</td>
      <td>3</td>
      <td>5</td>
      <td>...</td>
      <td>7</td>
      <td>8</td>
      <td>7</td>
      <td>4</td>
      <td>3</td>
      <td>7</td>
      <td>5</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6</th>
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
      <td>14</td>
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
      <th>8</th>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>2</td>
      <td>0</td>
      <td>...</td>
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
    </tr>
    <tr>
      <th>9</th>
      <td>8</td>
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
      <td>203</td>
      <td>214</td>
      <td>166</td>
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
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">data</span><span class="o">.</span><span class="n">info</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>&lt;class &#39;pandas.core.frame.DataFrame&#39;&gt;
RangeIndex: 5000 entries, 0 to 4999
Columns: 785 entries, label to pixel784
dtypes: int64(785)
memory usage: 29.9 MB
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Plot-the-Data">Plot the Data<a class="anchor-link" href="#Plot-the-Data">&#182;</a></h3><p>Let's peek first 25 rows of the dataset and display them as an images to have an example of clothes we will be working with.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># How many images to display.</span>
<span class="n">numbers_to_display</span> <span class="o">=</span> <span class="mi">25</span>

<span class="c1"># Calculate the number of cells that will hold all the images.</span>
<span class="n">num_cells</span> <span class="o">=</span> <span class="n">math</span><span class="o">.</span><span class="n">ceil</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">))</span>

<span class="c1"># Make the plot a little bit bigger than default one.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">10</span><span class="p">))</span>

<span class="c1"># Go through the first images in a training set and plot them.</span>
<span class="k">for</span> <span class="n">plot_index</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">):</span>
    <span class="c1"># Extract image data.</span>
    <span class="n">digit</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="n">plot_index</span><span class="p">:</span><span class="n">plot_index</span> <span class="o">+</span> <span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">values</span>
    <span class="n">digit_label</span> <span class="o">=</span> <span class="n">digit</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="mi">0</span><span class="p">]</span>
    <span class="n">digit_pixels</span> <span class="o">=</span> <span class="n">digit</span><span class="p">[</span><span class="mi">0</span><span class="p">][</span><span class="mi">1</span><span class="p">:]</span>

    <span class="c1"># Calculate image size (remember that each picture has square proportions).</span>
    <span class="n">image_size</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">digit_pixels</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]))</span>
    
    <span class="c1"># Convert image vector into the matrix of pixels.</span>
    <span class="n">frame</span> <span class="o">=</span> <span class="n">digit_pixels</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">image_size</span><span class="p">,</span> <span class="n">image_size</span><span class="p">))</span>
    
    <span class="c1"># Plot the image matrix.</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="n">num_cells</span><span class="p">,</span> <span class="n">num_cells</span><span class="p">,</span> <span class="n">plot_index</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">frame</span><span class="p">,</span> <span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;Greys&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="n">label_map</span><span class="p">[</span><span class="n">digit_label</span><span class="p">])</span>
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
<img src="data:image/png;base64,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82b2GZI+v3odp3wBiQPuDCRtY68Qgps990fivDkZSV88OYTg2oQzAIwC8BqA1wGMScsQQhiHZBB/P+37MpvURmNzOfgzgFWQmBZPRf3r+N8AbkASnPABgC+RjMcAgNT/504A2/E5U1PZDkhMZZORmFXPReI03WpY1uTeMTGztwHsEkJ4u5HHd0LyNbRSCGF8U96bmH/Sr5FZAFYNIXzQ2vcjhKgfGptFa9PhcymYWWck0QyN6mSibWJmu1qSz2QxJCHyryMJ+RRCtAM0Nou2QIefBKUhtOe29n2IJucnqDjJrgpgv1AGtaYQHQSNzaItUApzmBBCCCFETTq8JkgIIYQQIg9NgoQQQghRSuod/goAXbt2DX379m2mW0n49ttKZvUpU6ZE2c12yy5byYnXuXPnWtsB4IsvKskwZ86snUi4d+/eUf7BD5p3Hjh+/HjMmDGjzeewaYm6rcb331dSkXz88cdR/vrrr6PM9bzQQgsBAFZYoZLjq7nrsyajR4+eEUKoK+txm6At1G97pD3Ur+q2cbSHugVavn55vH3nnXcAAAssUFnQ3cddIPu+Znr0SJJ5L7poJRdjNu9p81Pf+m3QJKhv374YNWpUvfbll1VDfvy0adOifPbZZ0f5m2++AQAccMABsax///61tgPA66+/HuXrr7++1j1cfPHFUV58cU46W5vG/g5n0KBBDT6mNWhI3TYXPHm94IILovzBB5Wod54o9eyZJI0+4YQTYhl3upbAzCZU36v1aQv12x5pD/Wrum0c7aFugca/d5mGvLsmTqzkoNxxxx0BAEsssUQsYyUCKxm+++67KJ9xxhkAgA022CCW8eQpDx7bm+Jjtr7126BJUDXqM2HwSc4///nPWHbNNddEedasWVFeaqmlouwvyCuuuKLqffDsdMklk8SwXIndunWLcp8+lezfRx99NADg0EMPrfo7RNPx5JNJVvXtttsull177bVRPvbYY6PMk93zzz8fALDYYovFsqeeeirKW265Za1rNcUgIURHoCEvHf4gffjhh6N8ww03AMi+GOuDj+dHHXVULOOx/9JLL43y8ssvX+e5mvrl2VHIG9PGjRsX5VtuuSXKzz//fJT79esX5fXWWw8AcPfdd8ey5557Lspsmdl5552jfPvttwOovFMBYPXVK3lRN9lkkygPHToUQNay05KoxQghhBCilGgSJIQQQohS0qA8QYMGDQqNsT0//fTTUT7yyCMBZFWfCy9cWTqkU6d8C52rOdlpi01Z77//fpR5HzeVsMqU4X3nzp0LANhhhx1i2U033ZR7XH0ZNGgQRo0a1eZtLY2t22oUmUg//fTTKP/qV78CANx4442xrJr9mOG2tOeee0aZ627FFVes834ai5mNDiG0ecev5qpfptqznT17dpTdTA0Ab7zxRpQfeeSRKB9zzDG1zvHJJ59EmceNRRZZpNY9sGmEy9lc7g6f7PjJtIf6rVa39Wnz8+bNAwCce24ld+Ell1wSZQ4++PLLL6Psz33llSvrnRb5Wfr4ClTawtSpU2MZm7X5nt977z0AwKmnnhrL8toGkPVL8Tot+v3toW6Bxvddfuf9+9//BgC8/XYlObfXXU2Z34le7126dIll3laArA8mB7P4mFzUrz7//PMoez/de++9Y9n666+f+zsaYu6sb/1KEySEEEKIUtKkjtEMz954Bu+z/QUXXDCWffVVZfFvnsnnhd+xpmjSpElRZs1B3qyWz8uwM5Y7TLPjFzvuXXTRRbnnEMUUfXmeeeaZUT7kkEMAZOsw74sOyHdsZgd61gTxNf7+97/XeT+i+XBn9quvvjqWcb/jr9zhw4dH+eWXXwYAzJkzJ3c7O+Puu+++AIDllqtExD722GNRZk1Fr169orz00ksDAC677LJY5m2lveNjcNHX83XXXRdl7ys8vg4YMCDKrN3h+vD9WSvHmoIiXIPATs98Du7zHtTC4+8TTzwRZXfCBbJjf7Xf39G57777ouwa1MGDB8cyjsbld+1nn30WZdfYsbadg1NYa8TvdNcc5VllgGzf9fbEztmsCWru+itn6xBCCCFE6dEkSAghhBClpNnMYZxLYvz48VF2dTWr1IqcFlkN5jI75TFsSmEVnJtVWL3Kpha+DzfLsXnl8ccfjzKrCTnvkMhS5MjGKlVOsvWjH/2o1jnqcFSNcp5p7PDDD4/yXnvtFWWvO663pnaSFvm4mnzNNdeMZWPGjInyu+++G2Xu/94Pub+ygyab0b1t8b7PPvtslN0xHsgmWb3zzjsBZLPTV8tL05ap5kT6+9//Pso333xzlD2pHR/P5hJ2aman9smTJwMApk+fHsvYpMZ9LK98mWWWyb1frkfvm2ye4+vx+MHvHTe5cZsqCrzpiLAJ0xPLcp1ykAGbsvhd6uMlPzduI0UZo/0dzCYwrl82qea5qnDfZjNpcyBNkBBCCCFKiSZBQgghhCglzaYb5KUwWJXmZgnOL8AmKTaDsOxqN1aNsQmD1XJ8Plfz8blYLZenaivylOf1rE455ZRax4mEItMSL2mRl2afVef1yfdSzYTFZg2PlBgyZEidx4iWYezYsVFmFT3Xz/+3d+bxdk3n//8sMxWERCYZyCCICBVKEmKImQaJSs1Kq+bO9OtXihpaihZFaal5CjXEXCFSGcQUQ4REIkREDBFDalq/P/Z51vnse9e6596bO+/P+/W6rzxZZ5+999lrr7XXfsbvf//7APL5R6ygI1BO6Q+UTZ+sWueac2a2AfJj3u4RbuOyOq2FmNnf2GuvvYL8yiuvBHmrrbYKsuXt4qi91LzM7RZpx5+zKYNdE3gc2zOBxzCbWWK/g+8Ti+oD8qY6LpVjOafY5JaKEm6LvPzyy0E2E6aZxQBgwIABQeaIPu6T2H3F/ct9xia12HXmdQCPNxvfbJ7jZ7DMYUIIIYQQjYAWQUIIIYQoJA1qDmPVJ0dV9evXL8im+mJzGKu7OPqrSorzasdgL3ZWtXIEiUWYsAqXt+X9WSpvbuNoIq5gL3NYdcxUlTJT8T0RS62fMoHV9rhVj80Vjp9//nkAeXOLIsKaFo7cYdPowIEDg3z00UcH2SK2WLXO1cxZRW+q/4ULF4a2ww47LMg8J7z11ltBHjFiBADg9NNPj+63tWDnzOaJgw8+GAAwd+7c0LbZZpsFmaM17fuxiFwgb8rgcWNzJpfB4fmTI21jEbw8v7IJhOcHc0lImWR4H7yNRY1xYsVUSY+2yKabbhpkSyKZisDj+4b7z57HbIrkhJR8X/D3zLzG446/x24mfI9U/T6QjzBrDKQJEkIIIUQhaVBN0C233BLkXr16BTnm7JxyfOK3E36Tt1UrrxrZyYvfTvjNwPbHJTZSuQ1sVcurXj53PjYXhWVnvLZAXYrqxrR1Kc0Ma//WX3/9ep1bXbQ3nFfkzjvvrHFb5QxadlLX0Ark3nHHHaGNndb33nvvILMzs705srMu5/Ox3DZ8PE63z7moeEzHAiOOOuqoGn5Zy+arr74KGnbOkzVjxgwA+eKnXLgypt1hjQBf99R8bTngzIkdyI9tLlfCeZtMO5PS7jA29/P5sMWAZdYamGaCS+nwPdjWYW2L9S/neErl6mOnc7sfUvmnWOZ7xJ7dfL9xAWXuS9s35w7idQCXwmkMpAkSQgghRCHRIkgIIYQQhaRBzWFPP/10kFn9zM5opnZjVRyr2lglGsvtwblBGM4f8sILLwTZ1G6sJq2k2ks5BLJ68YorrghyWzOHxcxBdTEXpXJ/cL9wjhKjvtWCU+fD7bNnzwaQv0/69u1bcR+VnL1FmVT/XXbZZQDyjpPMvvvuG2Q2qZu5i+cPVucvWLAgyDY/pMzibDLp2rVrkC03CTtntza++eabYPrjMWYuCakyFrESRTxeeVt2amYTluXgYfPmEUccEWQ2e7Bp5K9//SsAoE+fPqGNj81Ou9aP3Iep+YifH+a+MHPmzNA2a9YstGVSOZrsecxO8ttss02Q2fWEndztvuB7JVXaivvMZDad9u/fP8jjx48PsuV54vxcKdNoYyBNkBBCCCEKiRZBQgghhCgkDWoO+9vf/hbkQw45JMgcSWV5A1KqVpZZzWkpuTntO6tXWUXLavBYxFKqIq5tyyo8NslZinggX4G5LbOs5qC33347yFz+wKJKgLKpynL5APmcEtzPrOI1lSu3DRkyJHpsU9efeeaZoe3666+veP6VIt5EZWy8nX/++aHt0UcfDTJHcbGJ0kzYvC2b0Xfaaacgm7qf+4kjyTgyke89O/YBBxxQ25/T4lhllVVCJOT9998f2vfff38A+eiwVL6f2D3N5g3O28LlESyaj01OPHaZWA6va665JrRxqSXO7WPRSqnzTbkv2DnddtttoY2jB9s6/LyysZSq3j5hwoQg83xrfc2mSH5G8z5iJjMejzx2n3322SAPGzYMQD76uilzdUkTJIQQQohCokWQEEIIIQpJo1WRZ1PDSSedFOTrrrsOQN4TnFWYnKiJ1a5m8mD1GqtdY2YtJlU9mI9tqkJWz++yyy5BLpoJDChfS472S5m4zKOfo2+4P7lkxR577BFkU41vu+22oY2j+Vg1Gqs0z33Lfc8lGMxEyonc2PzGKmBO9NmlSxcA9Y9cKxIpk6GNKzZFcnLCadOmBdnKWADA448/Xm2/O+ywQ5BffPHFINv9wvcp34d8z/I9YGOdK5G3Rmz+Y3PihRdeCCA//3LywpjrAZs0uA85Yui8884Lso2bsWPHVjzH3r17B/mXv/wlgPzYnTp1apDZfGn9z22p/uLoJ3sGcVJNfk60Rdjk9OqrrwbZ5j8bU0DehGkmKQBYtGhRkC0yk/spZQ7j+8XuI3ZVeP/994PMyWvtnDnCkO+VjTbaCI2JZnYhhBBCFBItgoQQQghRSBrUHJZSh19yySVBPuGEEwAAe+65Z2jjyAM2T7Fqz2D1Gkc9sKqNo7tMhWpJ0YC8mY3Vqj179gSQj7DgZF5FIWZOTEXU2TUD8rXcDI5G+Pe//x1kNj/97ne/A5BPipeq7xY7Nz4fVtVy/ZnLL78cQL5O1VlnnRVkvnf5nM1UM3jw4Oj5iDLcD2zCNBPFXXfdFdr4erP5kZP9bbjhhtX2yyp+Poap0lk9z/3PZlmubG3mXL5vWjN8Xc20yJFvHIEVMzPwteZ5kscj78NMzlynjxOS9ujRI8jct926dQMAXHvttaGNTVm8P5sreOxz0kyeV1hm87rR1s3abA5mc7E9E7mGJo87NhHzNYpFh6VcS2IR3zzuuM/YRGn9y9uy6bOxadt3hBBCCCFEggbVBNUmf4ppVvgthN/uWBvA2gLbN7+dLFy4MMi8OuU3+Vj6bX4T5FIY9uZQRO1PJfi6c/4VcxwG4tXn+a2CV/oxrRGXQeC+57cCPg/TFPJbaSpu3wAAIABJREFUKu+XtVeWM2PAgAHVjgvk7wPOMzVp0iQAQL9+/UIbv9G0JmL9s6w5j3ifqbdsu+bsoMtagZdffjnI7KxpucY4AIIddFk7Zw7OfC/wOOc5gbXJ5oDJWuXWiF37WB+fccYZQeYSJTfffHOQTfvN45nnVHZUfeihh4JsY2z48OGhbcqUKUHmfDCsubMSS1zVnccmH9u0GJMnTw5tjz32WJBvvPHGIHNAhVGkHF88P+68885BtjHGcylfC3ZK59Iitj+2mPC4YmJV6XmscdADawjnzZsHID9/pErsNAbSBAkhhBCikGgRJIQQQohC0mh5gioRU9sC6XTZtn0qz0OqUnIslwyr2vh7lgJe1AynnmdHPFOHch+yzGaNmOmEzVBsOmNi901tcn9YP6ec+hi+PzbbbDMArdcExjSGKaAu++Sq1WwyYbM25yix7Tm3Dd8jHAwRy2fFZls2s7/xxhtBNjNaW3GM5v6Ilbyx+xkALrroomrf46CSxYsXB5nNjAMHDgyymdS4j7gPuL+43cbYjjvuGNrYDMP9ZbAj72uvvRbkSqUw2roJjOEcd2+99VaQzemcg5B23333ILMZ2gISgHz/xUjNvda/bEbjZy2bLS13ETtn8/mMGjWqxnNYVqQJEkIIIUQh0SJICCGEEIWk0cxhlTzy2RySqlYcU7XVxtM/Vm2YzTKpvDJNWbm2tcH5Ja666qogn3LKKUG268rXkSMG+LpzhIH1aSwvFH9eVY71f8rMarBaP7VfPn+LRuL7silzWLRWuC/t2nGE3bHHHhtkvrc4WsiigSySiNsAYPPNNw+yqdJZ5c5p+C0CBcibNldZZRUAbcdkUun+Zzifj93TPC/zNWFTNpsZbfxzRC27FXC5EiuPA5RzF7FZZNdddw3ypptuWu082FTH/cnw+OZ7oSiwOZnzZFmePK7UzpG0HJnL19DGbsrsxSZOfo5Xuvbc17fddhuAfGQi93VjI02QEEIIIQqJFkFCCCGEKCTNpi9MpWdPqd1i0US1iQoy9TB/P2VSqYsquWgcd9xxQeYIEzMnAOUEh9yfnKySVdgcoWPUxhxZqWwG9yGbZCxqgiMmUvuIpY2fP39+aCtSMs26JFjkhJNsPrR9sOqcTSN8vxxzzDFBtggTVusfeOCBQeZSOB07dgSQT/rG9x6bATj6ZcaMGQDyyTlTyeBaMrFIsErzGfeRRQFxH/F45DHB19WOwePZSpEA5fIYQN7kYtf4j3/8Y2hLlcqx8+Dj8nkybcWsWV/YvMilKcwsySYnTiD68MMPB5m3sT7heZ5JJZk12DzH45Ujwawv2czKJmvuazbLNhTSBAkhhBCikGgRJIQQQohC0mzmsFgEV1VYnWvmitpUAY5tw/tKJcxrynolrYUJEyYAACZOnBjahgwZEt3W+ojV2pz07Pzzzw9y3759q32PSUVuVYL7kKO4Lr74YgDlGmJVzzNlLjX1cpHMYZUi8Hj8sIo7VkUaKCc15KSIXJWaE7yxit4SrfG2fO05YZ6p8DmRH9ckYzMBm1XM1GL3OZBPItdaqI8ZiCu1z549G0B+HKTcDbj/LXryt7/9bWiLmUIBYM6cOUG28c9jlOtJMTZO+bipSNKi89JLLwWZa3Ja/3bo0CG0sdmXE07y3GzjkaO9+L7gOZTNp7Y9m7J4HHOkqEVx8lzCx+A5QeYwIYQQQogGotk0QbXRusScVWtT9iD2BsPf47cmXslWOqciVSM2DjroIADAyJEjQ1sspT1Qvj78ps1vEEOHDg0yX3d746+vk3pMY1gV0xBwH/MbK8P7MAderlS93Xbb1frcWjoxh9pUP5gTJJdT4Lc/7lN2NLbrzNc+VvICiGts+B5imTUZzzzzDIC8Uy7nQeG8I+yAaW+WrDVqjZqg+hALTmFNEF9rHit8Lc0h+sEHHwxtnBuIyyawJsg0d/z2Xxstv1GU+beu8D3PWhPTtg4fPjy0xcYokM8fZd9jzRvL/Fzl+8LGMR+Dz4efBb179wYAdOrUKbSxNqqx8z1JEySEEEKIQqJFkBBCCCEKSaPpmSqpK1MqtUrUJo9QJbNVyrErlXuiaHBuB8vts++++4a28ePHR79n/cgmEjaNxfKLAJXVnXUxjXHfxsqx8LFSTqAsr7322rnvtzVi44N/Kzstm8mEryGru9ncxWYpMz/x9/geiVUX53PjnCGXXnppkHv27FntnDkvTWq/rLa3yuRsDuP7tC3Dc3CsvBCPO75msb7jwAl2gOU+YKdcM3dwbpm6PAfkGB2Hrz1fIxunbG7mvG3m4F4V2742c2VqfBs8xniOsWNzuRV+Bm2zzTZBtvm4IZEmSAghhBCFRIsgIYQQQhSSZosO46gBJlUCoVIuGVal1qUafKqCfZH5xz/+EeQf/OAHAIDvfe97oW3cuHHR71kfpcxblaI/uC9S1awrlXGoVP6iNvA+LF08571pS5g5mHP4sBqdf7e1s4mD0+bzmOYSCWZSS1UlT5mfrNQFm2K4ZAvvw6L42OzFKnU2e3MUis0VnD+qKStYNyex654agzzu2HRy1llnAchXfU+VOeB7zOAyKHfccUeQrQwKH5vPR+awOFwWiK+3Pdt4HuzcuXOQucQGj9NYxDTfN6n51p4BlgMIyOclYhO35f7i5zY/b1LRyA2FNEFCCCGEKCRaBAkhhBCikDSbOYypS5IsJhU1FDOdpTzaGZnDMjj1+o9//GMA+SrCKXOB9Qf3SyrahKlv2YxKUWOx/dYmIWPsXklVuG6NsNnKIrfY7MW/nxMj2jXgKA6u8J5KNmoqcd4vH4/vJ97GVOa87dy5c4PMKnwbu7wtq99Zhc99aaa6mNmvrcO/0+ZgnotT0Voc0fXPf/4TAHDiiSeGNo4oZHMpm2c22mgjAMAtt9wS2nhsxsxybGZPjceiJ1G061pVfueddwDkzVMvvvhikGfNmhVkHoM2plPPzFREdcwlhecSHrvWv5zElMsUNfZ4lCZICCGEEIWk2TRBqbwD/AZQ3/wwlXIDpd5wOMdCkeHrbg6P/KZsKe+rbmvXPaXFSfWnfS/l4BzbNnW+lUhtm7rv7E2IHfVaI9778Fuee+650G5Oh3zvc9kDdi62PmFNUsrhnJ0Z27dvDyA/5nm/nGsopkXk7/Hb4tNPPx1k0wywgzM75bIzNN9Ddl9zGY+2kicoVhKFieUJSjnFslaNNXe2PWuPuRQGF0jlt3vrL3OsBoAHHnig2udAPCihvtaDtg6XvOBcXaaF4+tqwQRAfkyz1j92nXlurpSLi/uf5xXWFJmDNo/B2mj9GgrdSUIIIYQoJFoECSGEEKKQNJo5rFLpCjY/sFq2Uo6f2lQMj5HKf8HtldTgRXG64xwOBqsnt9122yCzGSXmRFwbU5X1R8ppuS7V5St9L7Wv1H1l9+aQIUMq/IqWzZdffhnU0Wx+MtNFbcpY2D3ApSm4r1OqdlOv87W3chVA/h5i04eZ2tj8Mnr06GrnA5THcWps8xzD52mOu5xfpS1TyVSdqgqeyv1j5smbbroptPE9w/3B+YUGDx4MID/XsDlk4MCBQbb+4nNLOeHXxTTeFuFSMpZnCyj305IlS6Lf4zHB/W4BB2yGjgUvVMXM3exEzyU7eOzGSmGw+Zq/1xhIEySEEEKIQqJFkBBCCCEKSbNFh3FOnpQJg9WfJrOqrjYRZqbm5yiWVGmOopi7KnHAAQcE2dSanMae+yDWRykzJW8bu9bcn6myGUwsooWp1Ld16fvGVsk2Nt9++20wg/Xo0SO0m6kqZcKIlUDhfmQ1Ovc7m7hsrHNOITav8D7YVGemKv6co01iJhEe56myOoyp4tkMV5eyO60N7iO+rnb/c9/zdUi5LNj9w9GAPD9wf3EVcTONcbkNjkCLRQTVZrwWfQ5nkyLn1LKxxC4fHD3GYzPmIsLjg/smZV6zffAx+Jnfv3//IFs1e44emzp1apD79u0bZC710VBIEySEEEKIQqJFkBBCCCEKSbOZw1gNOnHixCCn1LWmjmO1HKvtUiYYU6GmzGWsPu3Xr1+N51wU0xlHQlnyLVZ7sjqc+8NMJ6lEZhxVwti1TJU2YRVupSRplRIypqKH+DfFzAStvWzG119/HUybrGqORealxoddAzaNcGI1NmVxVIiRqk6f6gfry1SiPpZt32x+4XuI98smPotumT17dmhLRR61Nbhv7ZqkytzwdeXEejaPH3TQQaGNkyWymYzLaey6664AymU3gLyZlrF7hc+XzfOiDJuceK6z8ciRWE8++WSQ2YzM/WdjvjYuDmwCN/eBVEQfz6e9e/cGUC7tAQA77LBDkC3ZamMhTZAQQgghCokWQUIIIYQoJM1mDmOVdEpVzZhqj7dNRXHEzBmpWiSxirlFh6/rpEmTAAAXX3xxaPv5z38eZL5mZm5htSgnSON2NnHZPjgJ3y677BLkVNV6O8+GME3yPRFLwtfa60m1a9cOw4cPB5BPqGbRJGyK4PpDnPTwlVdeAQAMGjQotLFKfcyYMUF+5JFHgrz33nsDACZPnhzahg4dGuSnnnoqyDFT7HrrrRfa+H5i1X/Xrl0B5OtPHXrooUG+5557ghyLhOMEoKkEcG0BNkkuWLAgyGa+YJN1KoEeV4a39unTp4c2jkpis+ibb74Z5GHDhgHIu0Kw+Y371qqPp+YSUYbHMY8bm7/YZM3bct9wbciYOYxl3h/fO2ZeYxMo32+MHYM/nzFjRpDZ9NmnT5/oPpYFaYKEEEIIUUiaTRN07733BpmdK1OOVvbWz055qRIIqZwgBr/p8/c4x4LIsJU8vz1fe+21Qea3vlj6c3uLA/L92aFDhyDbmze/CfAbK2uIuG/tzSOlHeT7I1bhnrflN13ext5o+K2qtWLXYIMNNghtLBv8Jshssskm1do4hwdz5JFHVmvba6+9otum2rfaaqtqbabxSXHUUUdF20eNGlXj94oCv8WPGDEiyOYMmyqrwU62nDOre/fuAIB99tkntPHbfyyPGADMnDkTADBu3LjQZtohIK5V4L7nsgqiDGtmOfjgjTfeAJDX7O63335Nd2I18NBDDwHIa9vtfAFg8803b9TjSxMkhBBCiEKiRZAQQgghCkmjmcMqOaveeOONQX788ceDzPkoGHO6Zae8VB6QmKM1nw+b33h/bdkhsr789Kc/BQAMGDAgtMXSsQNldTe3sRmNTVys+rRcInyMQw45JMislq+Ur6cuTtK8bcqMJkRrJZZTi+fXSy+9dJmPEcvDxs7QsVxEvD3npGkIij5211133SDzPGzPvEp51pqDXr16Acg7QLPJNZZzrCFpeVdECCGEEKIJ0CJICCGEEIXEpcoMRDd27n0AcytuKJie3vsWn+NdfVtv1L9tmxbfv+rbetPi+xZQ/y4DterfOi2ChBBCCCHaCjKHCSGEEKKQaBEkhBBCiEKiRZAQQgghCokWQUIIIYQoJFoECSGEEKKQaBEkhBBCiEKiRZAQQgghCokWQUIIIYQoJFoECSGEEKKQaBEkhBBCiEKiRZAQQgghCokWQUIIIYQoJFoECSGEEKKQaBEkhBBCiEKiRZAQQgghCokWQUIIIYQoJFoECSGEEKKQaBEkhBBCiEKiRZAQQgghCokWQUIIIYQoJFoECSGEEKKQaBEkhBBCiELS4hdBzrlezjnvnFuh9P/xzrmjmvu8RN0o9WGfun5WYZ+HO+eeWvazE0IIUUSadBHknJvjnPvCOfepc+4959y1zrnVm/IcxLJRWoR+5JxbubnPpbFwzg13zr3d3OfRWqBxvcQ597Fz7r/OuWOccy3+JUvUjPq2baP+bR5N0N7e+9UBbAFgSwCnNcM51Ann3PLNfQ4tAedcLwDDAHgA+zTryYiWxt7e+3YAegI4D8BvAFwT21DjqdWhvm3bFLp/m221571/B8ADAAaUVqM722fOuTOcczdU2odzbjnn3GnOubnOuYXOuX8559YsffaAc+74Ktu/4JzbryT3d8494pz70Dn3mnPuANruWufc35xz45xznwHYoYF+dmvnUACTAFwL4DD+oHTNLnPO3V96q5jsnOsd24lzbqhzbp5zbnjks5Wdcxc4594qaQuvcM6tWsM5Oefcpc65xc65Gc65neiDrs65e0p9/IZz7ugqx7nYOTe/9Hdxqe07yO7LriWN5afOua51uUhFxnu/2Ht/D4AfADjMOTcgNp5q6mfnXAfn3H2lN9MPnXMT7M3UOfcb59w7pXvsNe5v0biob9s2Re3fZlsEOee6A9gDwHPLsJvDS387ANgAwOoALi19djOAMXS8jZGtdO8vPegeAXATgHUBHAjg8tI2xg8B/AFAOwDyO8k4FMCNpb9dnXOdqnx+IIDfA2gP4A1k1y+Hc243ZH2zv/d+fOQY5wHoB2AQgD4AugH4XQ3ntDWAWQA6ADgdwFjn3Nqlz24B8DaArgBGATjHObdj6bP/A/C90nE2A7AVgNO8958B2B3AfO/96qW/+TUcX0Tw3k9Bdu2HlZqqjqea+vkXpe92BNAJwG8BeOfchgCOBzC49Oa6K4A5TfBzBKG+bdsUrX+bYxF0t3PuY2QX8wkA5yzDvg4C8Gfv/Wzv/acATgVwoMucqO8CMMg515O2Heu9/x+AvQDM8d7/03v/tff+OQB3AhhN+/63936i9/5b7/3SZTjHNoFzbiiyReRt3vtpyBYeP6yy2V3e+yne+6+RLZQGVfl8NIArAexeGmhVj+EA/BjAz7z3H3rvlyC7Pw6s4dQWArjYe/+V9/5WAK8B2LO0yB4C4Dfe+6Xe++cBXI1sIQdk98OZ3vuF3vv3kS3eDqnd1RC1ZD4AW5CG8QTgf6i5n78C0AVAz1K/TvDeewDfAFgZwMbOuRW993O897Oa9BcJQ33btilM/zbHImik934t731P7/2x3vsvlmFfXQHMpf/PBbACgE6lzrkf5c4Zg+zBDGQP861LKruPS4uygwB0pn3NW4bzaoscBuBh7/2i0v9vQhWTGIAFJH+OTDPHnIxsEfVS4hgdAawGYBr1y4Ol9hTvlAaZMRfZfdEVgA1S/qxbSY7dOzJ7NSzdAHxYknk8VernPyHTJD7snJvtnDsFALz3byC7h84AsNA5d4tMlc2G+rZtU5j+bSke4J8hu7BG59SGVZiPbEFj9ADwNYD3Sv+/GcAY59w2AFYB8HipfR6AJ0qLMftb3Xv/U9oXP1gLTcneewCA7Z1zC5xzCwD8DMBmzrnN6rCr0QBGOudOSny+CMAXADahflmz5EifoltJg2T0QHZfzAewtnOuXZXP3inJsXvHzF7q+2XEOTcY2URqpmS+pjX2s/d+iff+F977DZA54P/c/Ae89zd5700r6QGc30Q/SZRQ37Ztita/LWUR9DwyM9aKzrktkflv1IabAfzMObe+y0LtzwFwa8kcAwDjkF3wM0vt35ba7wPQzzl3SOmYKzrnBjvnNmq4n9SmGIlMnbkxMhPXIAAbAZiAsnmpNswHsBOAk5xzP636Yal//g7gIufcugDgnOvmnNu1hn2uC+DEUh+OLp3XOO/9PAD/BXCuc24V59xAAD8CYA73NwM4zTnX0TnXAZlN2z57D8A6ruRkL2qPc24N59xeyPyxbvDeT6+6TaV+ds7t5ZzrU1rcLkZ2733rnNvQObejy9IzLEU2GX9bdf+icVDftm2K2r8tZRH0/wD0BvARMt+Mm2r5vX8AuB7AkwDeRHZxT7APS/4/YwHszPssmUh2QWYqm4/MjHM+MpulqM5hAP7pvX/Le7/A/pA5oR9U8sGqFd77t5AthE5x8aSXv0GmTp3knPsEwKMANqxhl5MB9EX2hvIHAKO89x+UPhsDoBeyPr4LwOne+0dLn50N4BkALwKYDuDZUhu89zOQLZJml1S+LUJt28K51zm3BJmW9f8A/BnAETVsX1M/9y39/1MATwO43Hv/OLLxeR6yvl6AbAF8asP/FFEF9W3bptD96/LuFEIIIYQQxaClaIKEEEIIIZoULYKEEEIIUUi0CBJCCCFEIdEiSAghhBCFpNZRPQDQoUMH36tXrwY/CXbO/vrrr6Py8ssvn/sXAJZbrryG433E9vfVV1+FtpVWWqnafqvKDcWcOXOwaNEiV3nL5qWx+ratM23atEXe+5qSObYImrp/v/nmmyB/8sknAIC11lortOVTO5X57LPPgvzpp58CADp1qlqdpeloDf3bFH3Lc/F7770X5G7dusU2rzUff/xxkHn+bdeuXWzzBqU19C3QvHPzt99mUeyLFy8ObTx211yznEXkrbfeCvLKK2eB1p071zblX8NT2/6t0yKoV69eeOaZZ+p/VgmWLi1XpeBB8f777wfZBsXaa68d2ngxwwuf//3vf0H+4IMsWvrdd98NbT17lnPkcSeuscYa9fsBNbDllls2+D4bg8bq27aOc25u5a2an6bu348++ijI//nPfwAA++yzT2hbccUVo9+bOnVqkJ944gkAwC9/+cvGOMVa0Rr6tyn6dtGiRUG+4IILgnzeeect037Hjh0b5Pbt2wd5hx0av2Z1a+hboHnnZnsReeCBB0Ibj9099tgjyCecELLTYP311wcAnHLKKaGNn9Gpl6CGpLb9K3OYEEIIIQpJnTRBlajNSm/Bgqy81MyZM0Pbl19+GeQuXboEeZVVVgmyqdrGjx8f2hYuXBhk1v4wn3/+OQDggAMOCG22ugWA559/PsimFWJN0XrrrRfkxjCXCdGaYTPzbrvtFmQeV1988UXu39piWt9f/epXoe2Pf/xjkLldNDysiT/++OOD3LVrOXfoRRddBAA49thjQ5uZQqrC2qRLLrkEQPl5AABz58Zf3JtCKyTimBZ3wIABoe32228P8ocffhjke+65p9r3mKbQ/tQHaYKEEEIIUUi0CBJCCCFEIWlQc1hK3TVx4sQgm7f5uuuuG9rYwTkV8WWOVmwuW221cuF5PvZ3vvOdIJsJi1XxFq0CAJtsskm147GKlj3ehw0bFvt5QhQWHrvMOuusE2Qbpxzxw9FjbGZeYYXylGQOmKuvvnpo+/Wvfx3khx9+OMiPPPJInc9d1Mzs2bODzNFBHJxy1VVXAcj3EUeS8RzOc+n8+fMB5INi2KVh2rRpQZY5rPmwe4DdQk477bQg77///kFmN5KNNspqkdvzHsg/21sSLfOshBBCCCEamQbVBDH85sDhsltvvTWAvOYmlauH3wzMSS+Vl8IcoAFg1VVXrXYe/MbBjnu8OrV2Xr1y3hLeBzttC9FWib3JPfroo9FteWzyeDRSgROsFYptz2ONnXI5X01N3696PFE7Bg8eHGTWpE+ePDnIG2+8MYB8H6U06axBGjNmDADgsssuC20c6MIaetF82DP4yiuvDG0sz5o1K8jDhw+v9n0OQmqMFDQNgTRBQgghhCgkWgQJIYQQopA0mjmM1adsUrJ2dqTjnEGsMmUH56eeegoAMGTIkNDGalfOabHVVlsF2Uxj7JTJKjrOcxIzh/E58O+QOUwUgZgz4/XXXx/9nMcSjyF2djbY7M2OtGwas7HL5mveLzvumimFAy7EssF9y7ncLEiFt+EcQHfeeWeQef787ne/G+SHHnoIQH4O52oBrSXTfltnzz33BABsv/32oe2KK64I8g9+8IMg77XXXkG2nE9ckaGlIk2QEEIIIQqJFkFCCCGEKCSNZg5jFTerxMwU9fTTT4e2119/Pcicw4dzjbzzzjsA8upuNqNxmn42Ve28884A8pFmU6ZMCTKfx09+8hMAQMeO5cKzqegw0XCYiSOlfk9dd7uXOBKJI0z4vnvllVcA5NXvHIHSo0ePIPN5mJl10003DW2cn6qIsLmDIzF5rLAJq1JkFl9vNpOZeY1NYDyOWb7vvvsAAEceeWTlHyDqTP/+/YPM86P1HUcJWY4YIN+fHCVsZs+UewO7S4jmw8pl8LiaNGlSkLmcCs+9N9xwAwDgt7/9bWOf4jIjTZAQQgghCokWQUIIIYQoJE0SHdanT58gv/nmmwDyEVpciZa/1759+yDHkiSyCvbggw8O8o477hhkU8Ged955oY1V+L/4xS+qbRuLZgHSSd1E7aiULI/NIn/4wx+CfM011wSZo/xmzJhR62NblAqfQyyhHwCstdZaQV6yZEm1Y/H9XEQ6dOgQZI7K5D616wbkx3GMVDp92webxTfbbLMgc9JGq2DNanslSFw22LzZu3fvIHMU1+OPPw4gn8Syc+fOQeZ5+6WXXgqyjUO+l9js+atf/SrIl156af1+gFhmzD2Fn4lPPPFEkLmMlZVQAYB9990XQH4MttQSGi3nTIQQQgghmpBG0wSxpoffnM2B+bXXXgttI0aMCPKtt94aZNbYWKHGV199NbRx3glzgAaAqVOnBtk0CkcccURoM20UkH9jNceuTp06hTZ28OTfJOpO6s3cCmUy48ePDzI7wHJ/WD+xho7fWDm9/zHHHAMg79R55plnBpkdMdnx2Y7NDvtFxcYKa275WlkuLyDvHGvaXd6WNXKpvFxWFoOdKw844IAgc1+//fbbdfkpIgH3Bfchl9DgIIHjjjsOAHD11VeHNi6PMGjQoCDPmTMnyBaowPlnLLcMANxyyy1BNm095ycSTYP1JQeq7LbbbkG++OKLg8w5/syhuqVqf5iWeVZCCCGEEI2MFkFCCCGEKCQNag5jswSrz9ipyhypWH19xx13BJnzC7EZzUxcG264YWgbPXp0kDnfzw9/+MMgX3jhhQDy5gx2vuZztlTtnM+CzS+i6eDcQGwOY2dmU69yG6fvZ3Pqn//8ZwDp/COstuV7147NZtOiYoEIfC1Y5rHZs2fPIJuZg53a+RozZvZm9t577yBvsMEGQWbzqpXQYKdddnAXtYP7pVevXkHmscRz9JNPPgkgP0/y/Hn//fcHmQNZrG+mT58e2njMc9kMM7/KHNb02NzKz0nO1cfPaL4HFi9eDCCfJ4pN3S2Tx9qHAAAgAElEQVQJaYKEEEIIUUi0CBJCCCFEIWk0cxjD0T9mivrxj38c2rbYYosgc4TAv/71ryBbpML+++8f2lgV/+677wbZcoYAwMMPPwwgXxaBq13ffvvtQbbcFGwaYXVeLIpJNA4cgcL5RdgEYqYqjjRiVT33nanf+XNW8af63ExunPukqHDVdoMjO5m33nqrWlsqUoT7lPvH4Cg/LnXC/W4mmDfeeCO0qRJ53eE5br311gsyz5lswjI4PxP3PUeNHXLIIUHefPPNAZTdFYB8mZuUy4JoWmzMc99wdOjAgQOD/NhjjwXZTJscUS1zmBBCCCFEC0KLICGEEEIUkgY1h7Eqm1XcLJupgVPpcxKtm2++OcicDPH73/9+tWPMmzcvyGwme+SRR4JsFeUtvTsAnHzyyUHu169fkC1NfEwlD+QjJ1g9LDPZshGrIs+J2jg6jCOMLHKBow9TJi67B1kly/2ZSt5nEQ+cCKyofPDBB9XazKxRFb6GNgb5Gqfg7xljx44NMptdWEVv0SgcdSpzWN3hMcjRdexOwMloZ86cCSBvvnruueeCzGUV2GXBojQ5ape3nTJlSv1+gGhQJkyYACD+nATycy8/B609FQXakpAmSAghhBCFRIsgIYQQQhSSRosOY9U3y1aLhBNnLViwIMjdu3cPMkd/WY0SjhQ5/fTTg8wmtwsuuCDIN9xwAwDg73//e2ibOHFikLmWVOx3sLovVRFX1B2+J2I1Zdgcxv3BsplZ2DTJanlO3mXH4H7jxHyp8zG5pda9aUo4CZ7BCRJT1CXhaCx678EHH4xuu9deewX5xhtvBJCPXBF1h8cBm7V4jFlNNwAYNmwYgLxrAu+jb9++QWbTiM3/HIHGY/71118Pspk6RdNj0WFWFR7I3wsMzw/mwtAa5s2Wf4ZCCCGEEI1Ak+QJYg2KaVbYyZKdrqy6MFCuOA+U39pZc8O5ZH76058GmatVmxMf5yvgtwzTJgBlhy9+Y+GVLDt+SRNUO/itMOUsb3DleKscDeSdofkt1LQG3N+sdeD+sn7k1Pzct3wfcLvtjz8vKvPnz6/WlnKMZmzMpwInOC8TzyHmjP7OO+9E98vlNEwTFNNWidrD9z7Pk9zP/fv3D7KVqWGnZy6rwPM1Ozt36tQJQN7hmvML8Thnh2nRtNjY4zl2xowZQf7e974XZL53zIpjlp+WjDRBQgghhCgkWgQJIYQQopA0qDkslWuFVd+mVltnnXWqtQHA3XffHWR2fDTnuJ/97GehjdVv7Jg3ePDgIJtjFx+P1eucN+b9998HkDeZpEw4SuWekTJ31dQGANdee22QjzjiiGqfm7ocyDvL831lpg92hmX1a8ysmXLUY4fqmMM0q+e5knmRYJOywf2Uwu6B1JzA8P3E84LBwRI77rhjtc9TTpti2XjttdeCzKUSzDH6iiuuCG3cB/vtt1+QOQDmv//9LwDg2GOPrdYG5M1vbDITjQ/Pm2bmZNeCl19+OciWvw/Ij2m7BzhvW0tFmiAhhBBCFBItgoQQQghRSBrNHFYpBwurTDkKgUtlTJo0KcjbbrstgHK6daCcOwgAevXqFWRWu3fr1q3a8WJqO6AcpcKV7DkSopLppy0SK3VQKcqL4fxMHMHH0VbWR2yaZNMLm6I4ksjMJawu51T/HIFoKl4+Lt8nrLblivGmwj/nnHNCG1fGLjpdu3YNMpsU60ulXFy33HJLkI8++uhqn8dKe4j6scsuuwSZ50krVwOUrzf3vY1nIB81xiUyLCeQuSAA5RIcANChQ4fosUXjEysbxH3OJmnelt1IWpO7iDRBQgghhCgkWgQJIYQQopA0qDmMYXMYqzNNzclJEbnaM5ufWD36k5/8BEC+3AYn1Hv11VeDfN111wXZKspzQkaOaImZR1ilztFERSmbUV+z31VXXQWg3FdA/vpyEjW+rnZ/fPzxx6GN1al8DlxR3kxmfH+xWYuPYQn7+LdxYkU+T44etH08/vjjKDqVIj04QpMxsyVXn05F6XH/cHJFY9y4cUFmc5hFr6jEQsPBZmZ2WXjjjTeCbBGaPXv2DG08frj0BidDjD0HDj744CCfe+65QeZniWh8eNxZv/LY50gxjszlMW3jWFXkhRBCCCFaKFoECSGEEKKQNFrtsJhqDChH9/C2c+bMCTKruzkix/Z3/vnnh7aRI0cGmRNxsTrPqlyzapfrnTBmHuHoIN4X/47W5P1eV2ImMP693C+/+93vgmwmJY4YYjMTm61YTRo7HpsbU0n2bN/8OUebxMyXrNblzznigfvc7gm+v4qKmbVSJlI2kzB1qSTNY8zuF44INPN2VWxbjkYSywZHybLpmCN0rZ7cySefHNrYxHXzzTcHecyYMUG2eZnNXuwKYeZrIN//ovHhuZmjwgyeb9k0xmPP5giOCKxNYtXmQJogIYQQQhSSBtUE8Rsfr9555Rh7K+TcQP/3f/8XZH4zeOihhwDkNRKcWv3KK68MMmsibKXKKdm5+nzMCZhLL/Dx+DfV5e22NXPZZZcBAP70pz+FNnaG49W95fnha8b5fmJV3YHyW3xK48NyrDQLf4+PzQ6V5lCdcrJmLRXnK7LjcXXyojrf2htiLHcUkE+nz6S2NyqV0GAtBPd17C01VXFe1A7Wgk6cODHI2223XZDbt28fZBsXrM2fPn16kNdcc80g87h5+umnAQB9+/YNbaxBYqyfY2VURMPD483mbA5aWbhwYZBZs87z7dprrw0gP2/yeG1JfVmMJ7kQQgghRBW0CBJCCCFEIWm0shkpc5g5vHHOkI4dOwaZ80qwmvyaa64BAGy//fahjc0rm222WZA5J5CZY2rjyNyuXTsAeXMIpwIvigns0ksvDfIJJ5wAIF85nUtTxEqQpBznUn1g17WS2bQqduyUEyXLdmxO78/H4PNk0xirhg1WBxcJM4elVNmc14uxfq1N5XjG+oyPt2jRouj3TN5pp51C29lnnx3k0047LXoMkYfHBDu1cjvPBRYwwHmEeMz06dMnyDz2rG957LLMZhbLL8SlNETjEXMH4MAQzvfGY5D7z1wN2Mm6klm8uSjGU10IIYQQogpaBAkhhBCikDSoOYxVX6w+ZTOIqUrZ5MBqtFjkAQAMGjQIQN4c9sQTTwTZqswDedXsFltsAQAYPXp0aGNV64MPPhhkq2zMKeAZ/h0tVbVXX5YuXRrMGVwl3SLwOCKM+47NmkbqOsXKIABlc0mqXEddcjKl7iu7N1NRZ7xtrLQG50bhEi1tHTYH2+/mnErM/fffH2QeY9a/tSmVwdj3OFqTzWEc3WcqfL5POUpU1A42SafmYnMbAMpz5rPPPhvaOKqXTZm8Tffu3XPfr3psPp59z+Zy0XTYWOdxxXn0eN5kNwnL18YmUF4fsMmtuZEmSAghhBCFRIsgIYQQQhSSRosOS0WKGZxEi6MQ+Husdv/9738PAHjyySdD29Zbbx3kIUOGBDlWFoPNJJy0iSsbm9p9vfXWC22s7ksl7WsLLLfccsH0w2pwS4vPkRkp05Gps1ldzgm0Kl2/VHQYt8eiEbg/2UQSixpjMw1HsfC2XC7AvsdJHx999NFq595W4WtrptGUWYvT5rO6O5bUsjbRf7YN9ynzwgsvBHmHHXYAkI8C23///SseQ+ThhIZskmJTB0fw7rjjjgCACRMmhLY333wzyCeeeGJ0388//zyA/BzO5jKeQ/j5IBofnmMt+Si7JHBCUp7T2fxsffbSSy+FNiuVAuSfMc2NNEFCCCGEKCQNqgniNz0mVsiScwPxW0bqDdE0EvzGzvkqUtokk/ncUkU9bVt+6+fzZFK/tbWy0korBYfwq666KrRfdNFFAICpU6eGNi6UyY7R7ETbVlhnnXUA5N+EDj/88CD/9a9/bepTalIs/T0AXHjhhbX+HuddijlG1yZnUMxhnjWLXArHNEHS/iwbnOuJ88FwsMi///3vIJuWzhydgXw/jx07NshcWsPm/ClTpoS29957L8g8n6cCVUTjwGPTtLtszeE5n+dFLqFk7bNmzQptrEFih/jmRpogIYQQQhQSLYKEEEIIUUga1BwWMy0BedNRLFcMq7jZEZMdV03tymnY2TSWykFjarlUdfHddtut2nmyWpYdgvnc2HGvrcGVnS+//PIat+V+tjwQ7MiaqtTOmPo1lRsoZXq0PudjfPDBB0GOmVZTad7ZRMpOe3YPsjrYTGQin/uDr1vMCZ7bUmbvWJp9Hq/cZ1ytXDQMfP153HGwAJunLHcUm4jZLMKlS8xkCZSr0t94442hbd68edFjmEO+aHpsjuX5mINLOA+QuawAZVMqPydnzJgR5J133rnhT7aeSBMkhBBCiEKiRZAQQgghCkmDmsM4yovNEjHV+Kabbhra2MzEKlhWg9v3OAKJ1XIMq+7MzMH7YpUvp+S33CZ8Pnw8jnhJHbtocN+a6ShWeV20fmxcsWmQxznn9eK5IPa9VM6gmBmdxzPvQ+awhofnNe4LjhTj3Grrr78+gLwLwaRJk4LM+aLYHG7RptzGrg58HmyKE40Pu5bYPcDjjmV+llqpDKA8Zrl/W+p4lSZICCGEEIVEiyAhhBBCFJIGNYcxXHWWo2lMvcZVuVllllKfmmqco0PY7FKXkgz8PU4Nb+fE58C/g8+Zk8gJUQRiCQ65FEKlCE2GxzHD4zSmUufvcUX5GDwPpJIzijxs/ufSRtzPHD26YMECAPnIH57vOSkeRxKZCZTnUTapcUI+Nr+JxofHqz0r2ezF447dTDixsCVG5P7l6LGWhDRBQgghhCgkWgQJIYQQopA0qDmMEyNxxVj2Jjf12WabbRba7r333iD36NEjum9TZ7PKnVWm3M4qc1PtpSrcs/q3S5cuAPI1yXi//DtqUwVbiLZEzMzM9bsYHoP2PTZDc6RlamzGzGuc1JLNNZXOV+aw2sFzOFcF52rgW2yxRZD3228/AMANN9wQ2lZbbbUg77TTTkHmqDEzn40YMSK0DR06NMh33313/X6AWGbYbGnjjc2hL7/8cpDZfM3uIhbdx89JrhPXktCTXAghhBCFpEE1Qfx2x3lCKmFvE0A+JwQ7ysUqvPNbC7/1sYbI3gD5zZRzA/Xv3z/IMe0OO34JUWRi2pRRo0YF+Uc/+lGQP/744yCbU2Wq/EklYppkoFzhGihrdFlTJOoOV4gfP358kIcPHx7khx9+OMj29v/222+HNnacZa0RO8m+8MILAPLlMXiOfuSRR4LMedtE4xMLduBn8XPPPVftcyCfM8ysO2eeeWZou/TSSxv+ZBsAaYKEEEIIUUi0CBJCCCFEIWm0PEF1cUpkdTc7JbNsDs7syMxyrHwDy6m8JKlzroQcLUXRiJmL2bTM44crgs+cObNaG+fnYlU7q9fNubJbt26hjc0n22+/fZBjZjCN0bpzyimnRGV2deD52hyc+/XrF9p23XXXIPP9wSaugw46CEA+jxCbOq+44oog19eMKuoHjzEbu7Nnzw5tr7/+epA/+eSTILMJ/NRTTwUAjB49OrSx3JKQJkgIIYQQhUSLICGEEEIUEldHE9D7AFTSt2709N53rLxZ86K+rTfq37ZNi+9f9W29afF9C6h/l4Fa9W+dFkFCCCGEEG0FmcOEEEIIUUi0CBJCCCFEIdEiSAghhBCFRIsgIYQQQhQSLYKEEEIIUUi0CBJCCCFEIdEiSAghhBCFRIsgIYQQQhQSLYKEEEIIUUi0CBJCCCFEIdEiSAghhBCFRIsgIYQQQhQSLYKEEEIIUUi0CBJCCCFEIdEiSAghhBCFRIsgIYQQQhQSLYKEEEIIUUi0CBJCCCFEIdEiSAghhBCFRIsgIYQQQhQSLYKEEEIIUUi0CBKtFufcHOfczs19HkII0RZwzj3lnDs88dkGzrlPm/iUGp0WvQgqPeS+cM596pz7yDl3v3Oue3Ofl6iOc26oc+6/zrnFzrkPnXMTnXODm/u8RNPjnPuhc+6Z0rh91zn3gHNu6DLuc7xz7qiGOkdRf9S/LYtSP9jft/TM/NQ5d1BDHcd7P9t7v3qFc4kuopxzw5xzTzrnVnDOeedcr4Y6r2WlRS+CSuxduvBdALwH4K/NfD6iCs65NQDch6xv1gbQDcDvAfyvOc+rtjjnVmjuc2grOOd+DuBiAOcA6ASgB4DLAXy/Oc9LNAzq35aH9351+wPwFkrPzNLfjU1xDs655ZxzNa0n9gQwrinOpc5471vsH4A5AHam/+8BYGZJ3hPAcwA+ATAPwBlVvnsogLkAPgDw/6ruS38N2k9bAvg48dnhAJ4CcAGAjwC8CWB3+nxNANcAeBfAOwDOBrB86bPeAP5T6sNFAG4EsFbs/gCwUWnfY0r/7wrgTgDvl9pPpO+dAeAOADeU7p+jmvsatoW/Ul9+CmB04vOVkT1A55f+Lgawcumz9sgW0u+X7pP7AKxX+uwPAL4BsLS0/0ub+7cW8U/92/L/avOcA7AagJtK8+rHAKYA6FD67ClkL7D/BbAEwIMA1i591geAp/08BeAsAE8D+ALArVX68WLa9kUAA0v79QA+K22zf+nzYwC8UTqnuwF0KbWvUNr+hNI8vgjAeQCWa7Br1tydVtsOLXXcdQD+Vfr/cACbItNmDUSmJRpZ+mzj0gUeCmAlZA/gryrdHPqrdz+tUbp5rwOwO4D29NnhpWt/NIDlAfy0NEG60ud3AbgSwHcArFsakD8pfdYHwIjS5NoRwJNVBtYcADsD2ALZG9BepfblAEwD8LtS/28AYDaAXUufn1E6p5GlbVdt7mvYFv4A7AbgawArJD4/E8CkUj93LE2IZ5U+WwfA/qVx3g7A7QDupu+Ohxar6l/9Veqj8MysYZvjkC00Vi3NyVsCWL302VMAXgfQt9RXEwCcXfostgiag+wFdEVkC5anABxe5XjdAbxVkm1R04s+3wXAQgCDAKyCTLP4nyrbP4psId0T2WLp8Ppcn9hfazCH3e2c+xjAYmQPxD8BgPd+vPd+uvf+W+/9iwBuBrB96TujANzrvX/Ke/8lsoehb4ZzLwTe+0+QLTg9gL8DeN85d49zrlNpk7ne+797779BtlDqAqBT6fM9AJzsvf/Me78QwEUADizt9w3v/SPe+/95798H8GeU+9gYBuAeAId67+8rtQ0G0NF7f6b3/kvv/ezSeR1I33vae3936f75omGvSGFZB8Ai7/3Xic8PAnCm935hqT9/D+AQAPDef+C9v9N7/7n3fgky7UDVvhbNi/q3bfAVgA4A+njvv/HeP+O9Z4fna7z3r3vvP0e2WB1Uw77+4b1/1Xv/VQ33xR4AHqhhHwcBuNp7/7z3fimAUwBs75xbj7Y5z3v/kfd+LoC/ABhT4TfWmtbgCzHSe/+oc255ZHbnJ5xzGyNbEZ4HYACyt/2VkXUYkJlC5tkOvPefO+c+aNrTLhbe+1eRaX3gnOuPzNR0MYCHACyg7T53zgHA6sj8h1YE8G6pDcg0M/NK++kE4BJkC512pc8+qnLoYwA84b0fT209AXQtLZ6N5ZG91RjzIBqaDwB0cM6tkJgQuyIzURtzS21wzq2GbAG8G7I3PgBo55xbvrR4Fs2P+reVUXpuLqamfgCuRdYvt5X8Oa8HcBr16QLa/nNkc3WK2syjewD4Rw2fd0WmNQSQvVQ75z5C5ltq58LHCfdVQ9AaNEEAgNKKdSwym+NQZDbNewB0996vCeAKAPYkfRdAWEU651ZF9hYjmgDv/QxkA21AhU3nIXOe7uC9X6v0t4b3fpPS5+cg0y5t6r1fA8DBKPexcQyAHs65i6rs903a51re+3be+z34NOv360QNPI2sP0cmPp+PbIFq9Ci1AcAvAGwIYOtSX29Xarf+Vn81P+rfVkbpubk6/c0vacfP8N5vhOxZui8ybUy9DlHT/51zK5WO8Whie6DKfeOca4dsofwObcNR4XxfLTOtZhHkMr6P7OK8ikwz8KH3fqlzbisAP6TN7wCwt3Nu21InnIHqD0/RQDjn+jvnfmHqy1IagzHI/AOSeO/fBfAwgAudc2uUIgx6O+dMTd4OmW/XYudcNwC/iuxmCbK3y+2cc+eV2qYAWOKc+41zblXn3PLOuQEK2W9cvPeLkZmeL3POjXTOreacW9E5t7tz7o/ITNanOec6Ouc6lLa9ofT1dsicKz92zq0N4PQqu38PmW+XaCbUv20D59yOpflwOWSBIV8B+LaBdl+1H7cHMM17/xmQLcqQaRR5m5sB/Mg5N9A5tzKAcwFM8N6/Tdv82jm3lnOuB4ATkTlhNwitYRF0bylB0yfI7MiHee9fBnAsgDOdc0uQDbbb7Aulz08AcAsyrdCnyByvWkXIditkCYCtAUx2zn2GbPHzErK3v0ocisyc+QoyU9cdyHyGgMynYAtk6tz7AYyN7cB7/zEyf7HdnXNnlQbaXshs2RZRcDWy6BbRiHjvLwTwcwCnIYsEmgfgeGSOmGcDeAZZpMh0AM+W2oDMdLoqsr6ahCwqhbkEwKhSvrC/NPLPEAnUv22Crsjm0k8AvIxMS3NTA+37YgBjnHMfO+f+jHho/OkAbipts5/3/kFkTvV3IXte90B1zdS9AJ5HFhF+FzJLQ4NgETptGufc6shCAft6799s7vMRQggh2jrOuZnIonZn1vP7KyDTVK3vvZ/TkOdmtAZNUL1wzu1dUtd+B1mI/HRk4XxCCCGEaEScc6sgizSr1wKoqWiziyBkkWSWtKsvgAN9EdReQgghRDPjvV/qvT+/uc+jEoUwhwkhhBBCVKUta4KEEEIIIZJoESSEEEKIQlKnjNEdOnTwvXr1aqRTqR1ffvllkL/9tpzaYMUVVwzy8ssv36TnVBNz5szBokWLWnyOopbQt62RadOmLfLed2zu86hEc/bvN99kCYG/+KJcneSTTz4JMpvk11yznMVg5ZVXBpAf201Na+jf5uzbjz7KErivuuqqoS01/y5dujTIliF+9dVrSkbcuLSGvgUar3+//rqc9Pvjj8vJ9Tt06NBgx7CxDwALFy6MHqOxxndt+7dOi6BevXrhmWeeqf9ZLQN2Md95p5xE8rPPPgtyly5dgrzWWms13YlVYMstt2zuU6gVzdm3rRnn3NzKWzU/Td2/vLBZvDjL2v/SSy+FtkceeSTIPBnvtttuQe7bty8AoHPnzo12npVoDf1b377lPrJFSaytJu68804AwCabbBLa2rdvH2R+CL7++uvV9r3ddtuhEvayu9xyDWu4aA19CzTe2H3//feDfM899wT5Rz/6UYMdg192Lr744iD/+Mc/DnJjje/a9m+Lrh3Gg+aWW24BAGy00UahrWvXcvmQv//970Hedtttgzxq1KhaHy/mJF6biUCIImDjg8cEP+R4DE6ePDnIjz/+OICyZgcAPv20XK9xvfXKdRJvuqmcs800R/vtt19oO+6444LMD96q51j1PEV16jLfff7550HmOfX5558HACxZsiS0DRhQrpbDL6TvvvtukE2DtPHGG4e2c889N8iDBpVrdjb04kdk3HZbyC+ceylhlnVBdMkllwT5tddeCzIvunhB1Bzo7hJCCCFEIdEiSAghhBCFpMWZw15++eUg/+tf/wry6adn9fZWW2216PfYBHbdddcF+cEHsxI17GuQQupzIfJUMi+deeaZQWbfHjaP/OUvWSko9uGbMWNGkN94440gb7311kFed911AQAvvPBCaOOxzWN+5MhUYXORImZm4j78/e9/H+SxY8tl+9gJ2kycbJqcPXt2kD/44IMgs6+QOU/PnVt227j66quDzP4qv/nNbwAAW2yxRY2/B5BLQ13o3bt3kLnP/vnPfwZ5n332AQB07Bj3L07NDzNnZkmib7755tC27777BnmNNdao72k3ONIECSGEEKKQtAhN0FdffRXkp59+Osj8JrLKKqsAiK/0gfwq9LDDDgvyRRddBCDvUN2zZ89lPGMhBJAPaX/llVeCfPbZZwfZnKc33XTT0Na9e/cgpzRITz75JABg1113DW1/+tOfgnzAAQcs07kXhdo4i5933nkAgGnTpoU2DpseMWJEkDfccMMgn3TSSQDyju4c9s7av0WLFgXZtufQb5bffvvt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
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
<div class="prompt input_prompt">In&nbsp;[6]:</div>
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
<span class="n">num_training_examples</span> <span class="o">=</span> <span class="mi">1000</span>

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
<h3 id="Init-and-Train-MLP-Model">Init and Train MLP Model<a class="anchor-link" href="#Init-and-Train-MLP-Model">&#182;</a></h3><blockquote><p>☝🏻 This is the place where you might want to play with model configuration.</p>
<p>⚠️ Be aware though that the training of the neural network with current parameters may take up to 15 minutes depending on the hardware.</p>
</blockquote>
<ul>
<li><code>layers</code> - configuration of the multilayer perceptron layers (array of numbers where every number represents the number of nayron in specific layer).</li>
<li><code>max_iterations</code> - this is the maximum number of iterations that gradient descent algorithm will use to find the minimum of a cost function. Low numbers may prevent gradient descent from reaching the minimum. High numbers will make the algorithm work longer without improving its accuracy.</li>
<li><code>regularization_param</code> - parameter that will fight overfitting. The higher the parameter, the simplier is the model will be.</li>
<li><code>normalize_data</code> - boolean flag that indicates whether data normalization is needed or not.</li>
<li><code>alpha</code> - the size of gradient descent steps. You may need to reduce the step size if gradient descent can't find the cost function minimum. </li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Configure neural network.</span>
<span class="n">layers</span> <span class="o">=</span> <span class="p">[</span>
    <span class="mi">784</span><span class="p">,</span> <span class="c1"># Input layer - 28x28 input pixels.</span>
    <span class="mi">25</span><span class="p">,</span>  <span class="c1"># First hidden layer - 25 hidden units.</span>
    <span class="mi">10</span><span class="p">,</span>  <span class="c1"># Output layer - 10 labels, from 0 to 9.</span>
<span class="p">];</span>
<span class="n">normalize_data</span> <span class="o">=</span> <span class="kc">True</span>  <span class="c1"># Flag that detects whether we want to do features normalization or not.</span>
<span class="n">epsilon</span> <span class="o">=</span> <span class="mf">0.12</span>  <span class="c1"># Defines the range for initial theta values.</span>
<span class="n">max_iterations</span> <span class="o">=</span> <span class="mi">350</span>  <span class="c1"># Max number of gradient descent iterations.</span>
<span class="n">regularization_param</span> <span class="o">=</span> <span class="mi">2</span>  <span class="c1"># Helps to fight model overfitting.</span>
<span class="n">alpha</span> <span class="o">=</span> <span class="mf">0.1</span>  <span class="c1"># Gradient descent step size.</span>

<span class="c1"># Init neural network.</span>
<span class="n">multilayer_perceptron</span> <span class="o">=</span> <span class="n">MultilayerPerceptron</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">layers</span><span class="p">,</span> <span class="n">epsilon</span><span class="p">,</span> <span class="n">normalize_data</span><span class="p">)</span>

<span class="c1"># Train neural network.</span>
<span class="p">(</span><span class="n">thetas</span><span class="p">,</span> <span class="n">costs</span><span class="p">)</span> <span class="o">=</span> <span class="n">multilayer_perceptron</span><span class="o">.</span><span class="n">train</span><span class="p">(</span><span class="n">regularization_param</span><span class="p">,</span> <span class="n">max_iterations</span><span class="p">,</span> <span class="n">alpha</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">costs</span><span class="p">)),</span> <span class="n">costs</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Gradient Steps&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Cost&#39;</span><span class="p">)</span>
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
<h3 id="Illustrate-Hidden-Layers-Perceptrons">Illustrate Hidden Layers Perceptrons<a class="anchor-link" href="#Illustrate-Hidden-Layers-Perceptrons">&#182;</a></h3><p>Each perceptron in the hidden layer learned something from the training process. What it learned is represented by input theta parameters for it. Each perceptron in the hidden layer has 28x28 input thetas (one for each input image pizel). Each theta represents how valuable each pixel is for this particuar perceptron. So let's try to plot how valuable each pixel of input image is for each perceptron based on its theta values.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Setup the number of layer we want to display.</span>
<span class="c1"># We want to display the first hidden layer.</span>
<span class="n">layer_number</span> <span class="o">=</span> <span class="mi">1</span> 

<span class="c1"># How many perceptrons to display.</span>
<span class="n">num_perceptrons</span> <span class="o">=</span> <span class="nb">len</span><span class="p">(</span><span class="n">thetas</span><span class="p">[</span><span class="n">layer_number</span> <span class="o">-</span> <span class="mi">1</span><span class="p">])</span>

<span class="c1"># Calculate the number of cells that will hold all the images.</span>
<span class="n">num_cells</span> <span class="o">=</span> <span class="n">math</span><span class="o">.</span><span class="n">ceil</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">num_perceptrons</span><span class="p">))</span>

<span class="c1"># Make the plot a little bit bigger than default one.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">10</span><span class="p">))</span>

<span class="c1"># Go through the perceptrons plot what they&#39;ve learnt.</span>
<span class="k">for</span> <span class="n">perceptron_index</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">num_perceptrons</span><span class="p">):</span>
    <span class="c1"># Extract perceptron data.</span>
    <span class="n">perceptron</span> <span class="o">=</span> <span class="n">thetas</span><span class="p">[</span><span class="n">layer_number</span> <span class="o">-</span> <span class="mi">1</span><span class="p">][</span><span class="n">perceptron_index</span><span class="p">][</span><span class="mi">1</span><span class="p">:]</span>

    <span class="c1"># Calculate image size (remember that each picture has square proportions).</span>
    <span class="n">image_size</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">perceptron</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]))</span>
    
    <span class="c1"># Convert image vector into the matrix of pixels.</span>
    <span class="n">frame</span> <span class="o">=</span> <span class="n">perceptron</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">image_size</span><span class="p">,</span> <span class="n">image_size</span><span class="p">))</span>
    
    <span class="c1"># Plot the image matrix.</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="n">num_cells</span><span class="p">,</span> <span class="n">num_cells</span><span class="p">,</span> <span class="n">perceptron_index</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">frame</span><span class="p">,</span> <span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;Greys&#39;</span><span class="p">,</span> <span class="n">vmin</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">amin</span><span class="p">(</span><span class="n">frame</span><span class="p">),</span> <span class="n">vmax</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">amax</span><span class="p">(</span><span class="n">frame</span><span class="p">))</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Percep. #</span><span class="si">%s</span><span class="s1">&#39;</span> <span class="o">%</span> <span class="n">perceptron_index</span><span class="p">)</span>
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
<img src="data:image/png;base64,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t13RY8a3qqoxVVW96H9qBE6PrarqHa/f0hFk1PIopRwtaZmqqr40r48lMfeR49uzkePbc5Fj27PR6uObZTMSiUQikUi0JfImKJFIJBKJRFuix8hhiUQikUgkEl1BMkGJRCKRSCTaEnkTlEgkEolEoi3RJbPEAQMGVPPPP78kaciQpnHy2LFjJUn+G/sk6T3veU+0X331VUnStGlN/6ZFF20aS77yyiud9k+dOnWm4xk/fny0+/fvH+3OjmPEiBHR99RTT0V74YUXjvaYMWMkSX379u307zyGiRObmXn//W/Di6tfv37RN3RoI3vw5Zdf1oQJE7q9z8ygQYOqYcOGzdT/2muvSaqPt/uk+ngtskgj+5ISKy12OF7LLNOsbejz9/zzz0cfx/6ll16K9vDhw6Pt75k+fXqn38fxmDy5kSk7ZUqz7t6gQYM6/R2LL9706erTp89Mn0s88cQTo6uqWqjTP3YjDBw4sPIYcnx69+4tqX4O33yzWTuWa8Hn3uMl1dcE1+B8880X7cGDB0uSJkxoGqt7H5Dq48TXeA74GKXmOErSqFHNQtLeYzg3+T7ObY6l9wfOi4UWag7nU0891e3Hd7755qu833AMPHb8vWwPGDAg2l57PP/+TKm+p3LMBw4cKEl6/fXXo2/SpEk8tmiPG9c0HPZc7NWr+RzO9cg56tfwmsHv4Gt5zJ5j/Fx+35NPPtntx1ZqXHe9hrhWFlxwQUn19ci/87y8/PLLkprjJdXPRWfXLr6P+4O/l3+X6mPtuffGG290ejwck9GjR0uqr21fS6T63vze97432p5znBdc548//vgcjW+XboLmn39+bb755pKkDTfcMPqvuuoqSdJ6660Xfddcc020v/CFL0T79ttvl9S84ZCk4447LtpXXHFFp/3e8LhB33LLLdH+wAeaZpZrr712tK+//npJ0p577hl9O+20U7QPOuigaF966aWSpMUWW6zTv/NifM8990T7nHPOmel9G220kSTpiCOOUCtg2LBh+uY3vympvlE+8kijkO8GG2wQfX/6U9PL6qc//Wm0DzjgAEn1yczFddttt0Xb4yJJ5557riTpkEMOib6vf/3r0T799NOjzbHzZswLHxf2Eks07X3+8Y9/SJKefvrp6PvEJz4R7csua5oHn3nmmdH2BZEXVH7Hqquu+h+1AIYMGaIddthBUn18fDHiZsUbFD4E7LLLLpKks88+O/pefPHFaC+55JLRXm211aK95pprSpLuvvvu6PvVr37V6ft+85vfRNtrZ4EFFoi+J55oet+deOKJ0f7c5z4nSXr44YejjxvilltuGW3e2Hnv4g341772tWjvsMMO3X58hw4dqq985SuS6ufSY8ffy/aHPvShaB955JGSpLvuuiv6vIdJ9b2dF90VV1xRkvTXv/41+u6///5or7zyytH+xS9+MdPn+eIuSR//+MejzZtS34Bx/33ggQeizbm76aabRvuXv/ylJGnVVVeNPl6oN9hgg24/tlLjHH3+85+XVL8J+PKXG8ULfP2RpPe9L4yba+flhz9seIN6vKT6jQjft8kmm0T7vPPOk1S/6dx5552jze/mWPta+K9/Natw8Hi8J0jS+eefL0n6+9//Hn377bdftH/yk59E++STT4629wLeS2yxxRbR/shHPjJH49ulm6CBAwfGD/XFUWpO0r/9rWmc/H//93+19xme3Nxcuel++MMfjjYZpD322EOStP3220cffzzvMrkRbrzxxpLqGzcHjhdFXzR5PLzIv//974827z5983T44YdHnweUF5zujP79+wc7wwuRn5R/97tmmZiDDz442h/96Eej7fNw+eWXR58nuFS/qeXE/vSnPy1J+uMf/xh9vHlcbrnlos1j++IXvyhJWmedpgkqzzdvVjxvfvCDpsHoZz7zmWivu+660eZTrW/sTj311Ojbf//91WqYOnWqnn22Ud6Hm5Wfzslscl35JkGSLrroIknSgQceGH3HHntstM2aSfWLzW9/+1tJ0qOPPhp9H/nIR6LNfYMXMTO2vFklOJZ+6CKLt/TSzQoA/I5777032r454l5z2mmndfp93RUDBgyIh0A+APoCxnPCseXNjC98vDjxwZKsGx86rr76akl1lscPU9KsWSFfgDlnyNaz3+uRbBTnyY9//ONoc1/2fu35J9WvL62CwYMH65Of/KSkOvPia9duu+0WfTxH3MfWWGMNSfU1QUbn4osvjvYLL7ww02vIwH/sY02jaLKmPA5fA3hTzuPh5/mhg+rAlVde2el3cD8yW/T4449HH8mZOUXGBCUSiUQikWhL5E1QIpFIJBKJtkSX5LD55psv6ERSyqa2qeNao5fq8pIp0c022yz6SI05Zkiqx56YxqNMwhic++5r1mozdSg1JRHS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aWxXafv3byUt2tb+XUffOZegSuN7tKTBkh5ONd+VCSml8zr6zrkAVRrb70h6PKU0UbX1+1vVYk/mZlRifItaNufr/k/SWEkz2v7dbibZByE1c+hKSmmEpCWKotjs0z6WwJxFjO3cjRjfuRcxtnM35rbxjbIZgUAgEAgEKom4CQoEAoFAIFBJNLUcFggEAoFAIDC7CCYoEAgEAoFAJRE3QYFAIBAIBCqJLpkl9uzZs+jbt68kad55583948ePlyRRWuvfv39ujx07NreHDBkiSZo4cWLuq1vuSFOnTs1tfsf06bXMt+eeey739erVK7f5GT4eft+CC9YzBd9///3cHjeuborZu3fvWX6Hv1eSJkyYkNvdu9dP3ZQpUyRJ3brV7ynnm28+SdLrr7+ud955p35wDYq+ffsWgwYNklT+zQsssIAk6d133819PXv2zG2eq5aWFknl8zBp0qTc5th6HvH7Wltbcx/nB4+H49yvX79Zvu9///vfLMfO4+fx8HcMGFA3/X7rrbdm+X38Ds7Lp5566s2iKD6jBke/fv2KwYMHSyqfA59DjgfXT58+fXJ78uSamfIbb9QNXbnOPeel+pqQpLfffltS+bwuvPDCuc0x5bj7u997773cxznyzjvv5Lbnntc7j3fm30f4uznHONZPP/10w49vnz59ioEDB0oqH/tnPlM77Ndeq3vY8e8cW6+FadPqPnvc47j3zTNPPVPaeynPH9cV91eOsz+D38HP4Dj7mPh37iX8HZx3bvOzeDxjxoxp+LGVamvXe47XqyS98krN25N7F9fPQgvVDZy9/82YMSP38frJMXvzzTdze8yYWoF2rleC+z/HxOuRew3Hmu/zOHH/4GdxTLkX+Jhef71eZJ7X+WeeeaZT49ulm6C+ffvqBz/4gSRp4403zv333HPPLAe++uqr5/avfvWr3B4+fLgk6W9/q/sj+YRJ5R/E7/BGut566+W+L33pS7nNQfTxSNKWW24pSTrkkENy37///e/cvvnmm3N7qaWWklTePHnxv+++umu4LyhSfZPhYvzlL38pSdpxxx3VDBg0aJB22203SeWNYq+99pJUPqeLL754bnPT9GLkBefvf8+FgUsXz5VWWim3fZPMRfvwww/nNseAm/h3v/tdSeWN4ZRTTsntvffeO7fvvPNOSdLTTz/d7u/4/ve/n9uXX375LL+P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
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
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Make training set predictions.</span>
<span class="n">y_train_predictions</span> <span class="o">=</span> <span class="n">multilayer_perceptron</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_train</span><span class="p">)</span>
<span class="n">y_test_predictions</span> <span class="o">=</span> <span class="n">multilayer_perceptron</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_test</span><span class="p">)</span>

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
<pre>Training Precision: 93.8000%
Test Precision: 80.6000%
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Plot-Test-Dataset-Predictions">Plot Test Dataset Predictions<a class="anchor-link" href="#Plot-Test-Dataset-Predictions">&#182;</a></h3><p>In order to illustrate how our model classifies unknown examples let's plot first 64 predictions for testing dataset. All green clothes on the plot below have been recognized correctly but all the red clothes have not been recognized correctly by our classifier. On top of each image you may see the class that has been recognized on the image.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># How many images to display.</span>
<span class="n">numbers_to_display</span> <span class="o">=</span> <span class="mi">64</span>

<span class="c1"># Calculate the number of cells that will hold all the images.</span>
<span class="n">num_cells</span> <span class="o">=</span> <span class="n">math</span><span class="o">.</span><span class="n">ceil</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">))</span>

<span class="c1"># Make the plot a little bit bigger than default one.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">15</span><span class="p">,</span> <span class="mi">15</span><span class="p">))</span>

<span class="c1"># Go through the first images in a test set and plot them.</span>
<span class="k">for</span> <span class="n">plot_index</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">):</span>
    <span class="c1"># Extract digit data.</span>
    <span class="n">digit_label</span> <span class="o">=</span> <span class="n">y_test</span><span class="p">[</span><span class="n">plot_index</span><span class="p">,</span> <span class="mi">0</span><span class="p">]</span>
    <span class="n">digit_pixels</span> <span class="o">=</span> <span class="n">x_test</span><span class="p">[</span><span class="n">plot_index</span><span class="p">,</span> <span class="p">:]</span>
    
    <span class="c1"># Predicted label.</span>
    <span class="n">predicted_label</span> <span class="o">=</span> <span class="n">y_test_predictions</span><span class="p">[</span><span class="n">plot_index</span><span class="p">][</span><span class="mi">0</span><span class="p">]</span>

    <span class="c1"># Calculate image size (remember that each picture has square proportions).</span>
    <span class="n">image_size</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">digit_pixels</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]))</span>
    
    <span class="c1"># Convert image vector into the matrix of pixels.</span>
    <span class="n">frame</span> <span class="o">=</span> <span class="n">digit_pixels</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">image_size</span><span class="p">,</span> <span class="n">image_size</span><span class="p">))</span>
    
    <span class="c1"># Plot the image matrix.</span>
    <span class="n">color_map</span> <span class="o">=</span> <span class="s1">&#39;Greens&#39;</span> <span class="k">if</span> <span class="n">predicted_label</span> <span class="o">==</span> <span class="n">digit_label</span> <span class="k">else</span> <span class="s1">&#39;Reds&#39;</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="n">num_cells</span><span class="p">,</span> <span class="n">num_cells</span><span class="p">,</span> <span class="n">plot_index</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">frame</span><span class="p">,</span> <span class="n">cmap</span><span class="o">=</span><span class="n">color_map</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="n">label_map</span><span class="p">[</span><span class="n">predicted_label</span><span class="p">])</span>
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
