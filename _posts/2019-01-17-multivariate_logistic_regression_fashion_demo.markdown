---
layout: none
permalink: /tutorial/multivariate_logistic_regression_fashion
---
<html>
<head><meta charset="utf-8" />

<title>multivariate_logistic_regression_fashion_demo</title>

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
<blockquote><p><strong>Demo Project:</strong> In this example we will train clothes classifier that will recognize clothes types (10 categories) from <code>28x28</code> pixel images.</p>
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
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Plot-the-Data">Plot the Data<a class="anchor-link" href="#Plot-the-Data">&#182;</a></h3><p>Let's peek first 25 rows of the dataset and display them as an images to have an example of clothes we will be working with.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
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
    <span class="c1"># Extrace image data.</span>
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
<img src="data:image/png;base64,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82b2GZI+v3odp3wBiQPuDCRtY68Qgps990fivDkZSV88OYTg2oQzAIwC8BqA1wGMScsQQhiHZBB/P+37MpvURmNzOfgzgFWQmBZPRf3r+N8AbkASnPABgC+RjMcAgNT/504A2/E5U1PZDkhMZZORmFXPReI03WpY1uTeMTGztwHsEkJ4u5HHd0LyNbRSCGF8U96bmH/Sr5FZAFYNIXzQ2vcjhKgfGptFa9PhcymYWWck0QyN6mSibWJmu1qSz2QxJCHyryMJ+RRCtAM0Nou2QIefBKUhtOe29n2IJucnqDjJrgpgv1AGtaYQHQSNzaItUApzmBBCCCFETTq8JkgIIYQQIg9NgoQQQghRSuod/goAXbt2DX379m2mW0n49ttKZvUpU6ZE2c12yy5byYnXuXPnWtsB4IsvKskwZ86snUi4d+/eUf7BD5p3Hjh+/HjMmDGjzeewaYm6rcb331dSkXz88cdR/vrrr6PM9bzQQgsBAFZYoZLjq7nrsyajR4+eEUKoK+txm6At1G97pD3Ur+q2cbSHugVavn55vH3nnXcAAAssUFnQ3cddIPu+Znr0SJJ5L7poJRdjNu9p81Pf+m3QJKhv374YNWpUvfbll1VDfvy0adOifPbZZ0f5m2++AQAccMABsax///61tgPA66+/HuXrr7++1j1cfPHFUV58cU46W5vG/g5n0KBBDT6mNWhI3TYXPHm94IILovzBB5Wod54o9eyZJI0+4YQTYhl3upbAzCZU36v1aQv12x5pD/Wrum0c7aFugca/d5mGvLsmTqzkoNxxxx0BAEsssUQsYyUCKxm+++67KJ9xxhkAgA022CCW8eQpDx7bm+Jjtr7126BJUDXqM2HwSc4///nPWHbNNddEedasWVFeaqmlouwvyCuuuKLqffDsdMklk8SwXIndunWLcp8+lezfRx99NADg0EMPrfo7RNPx5JNJVvXtttsull177bVRPvbYY6PMk93zzz8fALDYYovFsqeeeirKW265Za1rNcUgIURHoCEvHf4gffjhh6N8ww03AMi+GOuDj+dHHXVULOOx/9JLL43y8ssvX+e5mvrl2VHIG9PGjRsX5VtuuSXKzz//fJT79esX5fXWWw8AcPfdd8ey5557Lspsmdl5552jfPvttwOovFMBYPXVK3lRN9lkkygPHToUQNay05KoxQghhBCilGgS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CYG/+KJcneSTTz4JMpvk11yznMVg5ZVXBpAf201Na+jf5uzbjz7KErivuuqqoS01/y5dujTIliF+9dVrSkbcuLSGvgUar3+//rqc9Pvjj8vJ9Tt06NBgx7CxDwALFy6MHqOxxndt+7dOi6BevXrhmWeeqf9ZLQN2Md95p5xE8rPPPgtyly5dgrzWWms13YlVYMstt2zuU6gVzdm3rRnn3NzKWzU/Td2/vLBZvDjL2v/SSy+FtkceeSTIPBnvtttuQe7bty8AoHPnzo12npVoDf1b377lPrJFSaytJu68804AwCabbBLa2rdvH2R+CL7++uvV9r3ddtuhEvayu9xyDWu4aA19CzTe2H3//feDfM899wT5Rz/6UYMdg192Lr744iD/+Mc/DnJjje/a9m+Lrh3Gg+aWW24BAGy00UahrWvXcvmQv//970Hedtttgzxq1KhaHy/mJF6biUCIImDjg8cEP+R4DE6ePDnIjz/+OICyZgcAPv20XK9xvfXKdRJvuqmcs800R/vtt19oO+6444LMD96q51j1PEV16jLfff7550HmOfX5558HACxZsiS0DRhQrpbDL6TvvvtukE2DtPHGG4e2c889N8iDBpVrdjb04kdk3HZbyC+ceylhlnVBdMkllwT5tddeCzIvunhB1Bzo7hJCCCFEIdEiSAghhBCFpMWZw15++eUg/+tf/wry6adn9fZWW2216PfYBHbdddcF+cEHsxI17GuQQupzIfJUMi+deeaZQWbfHjaP/OUvWSko9uGbMWNGkN94440gb7311kFed911AQAvvPBCaOOxzWN+5MhUYXORImZm4j78/e9/H+SxY8tl+9gJ2kycbJqcPXt2kD/44IMgs6+QOU/PnVt227j66quDzP4qv/nNbwAAW2yxRY2/B5BLQ13o3bt3kLnP/vnPfwZ5n332AQB07Bj3L07NDzNnZkmib7755tC27777BnmNNdao72k3ONIECSGEEKKQtAhN0FdffRXkp59+Osj8JrLKKqsAiK/0gfwq9LDDDgvyRRddBCDvUN2zZ89lPGMhBJAPaX/llVeCfPbZZwfZnKc33XTT0Na9e/cgpzRITz75JABg1113DW1/+tOfgnzAAQcs07kXhdo4i5933nkAgGnTpoU2DpseMWJEkDfccMMgn3TSSQDyju4c9s7av0WLFgXZtufQb5bffvvt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
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
<span class="n">num_training_examples</span> <span class="o">=</span> <span class="mi">3000</span>
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
<span class="n">regularization_param</span> <span class="o">=</span> <span class="mi">25</span>  <span class="c1"># Helps to fight model overfitting.</span>
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
      <td>-6.077491</td>
      <td>-0.054096</td>
      <td>-0.072268</td>
      <td>0.031625</td>
      <td>0.074728</td>
      <td>0.090190</td>
      <td>0.137357</td>
      <td>-0.128473</td>
      <td>-0.072395</td>
      <td>0.011406</td>
      <td>...</td>
      <td>-0.071843</td>
      <td>-0.054607</td>
      <td>0.139552</td>
      <td>0.056198</td>
      <td>0.197529</td>
      <td>0.005156</td>
      <td>-0.083541</td>
      <td>-0.040630</td>
      <td>-0.009371</td>
      <td>-0.009137</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-6.871615</td>
      <td>-0.002022</td>
      <td>-0.002043</td>
      <td>-0.013173</td>
      <td>-0.019387</td>
      <td>0.199802</td>
      <td>-0.046613</td>
      <td>0.038926</td>
      <td>0.143524</td>
      <td>0.172239</td>
      <td>...</td>
      <td>0.100372</td>
      <td>0.056467</td>
      <td>-0.019896</td>
      <td>-0.024661</td>
      <td>-0.012431</td>
      <td>-0.004531</td>
      <td>-0.009489</td>
      <td>-0.003141</td>
      <td>-0.013222</td>
      <td>-0.016581</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-5.484414</td>
      <td>-0.001377</td>
      <td>0.065189</td>
      <td>-0.223125</td>
      <td>-0.037388</td>
      <td>-0.061283</td>
      <td>-0.142390</td>
      <td>0.096851</td>
      <td>-0.069638</td>
      <td>-0.006118</td>
      <td>...</td>
      <td>-0.031186</td>
      <td>0.160019</td>
      <td>0.142373</td>
      <td>0.137873</td>
      <td>0.064698</td>
      <td>0.043028</td>
      <td>-0.085860</td>
      <td>-0.019212</td>
      <td>0.172103</td>
      <td>0.179450</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-6.479539</td>
      <td>-0.025596</td>
      <td>-0.025370</td>
      <td>0.149444</td>
      <td>-0.010553</td>
      <td>-0.003944</td>
      <td>0.052908</td>
      <td>0.111660</td>
      <td>-0.075223</td>
      <td>-0.063640</td>
      <td>...</td>
      <td>0.180960</td>
      <td>-0.030979</td>
      <td>-0.028157</td>
      <td>-0.190387</td>
      <td>-0.125556</td>
      <td>-0.126413</td>
      <td>-0.066519</td>
      <td>-0.051773</td>
      <td>-0.048392</td>
      <td>-0.028799</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-5.916161</td>
      <td>-0.001441</td>
      <td>-0.024669</td>
      <td>0.023222</td>
      <td>0.064555</td>
      <td>-0.013986</td>
      <td>-0.024218</td>
      <td>-0.027205</td>
      <td>-0.021830</td>
      <td>-0.085304</td>
      <td>...</td>
      <td>-0.077075</td>
      <td>0.155594</td>
      <td>-0.070225</td>
      <td>-0.066349</td>
      <td>0.160192</td>
      <td>0.074204</td>
      <td>0.037278</td>
      <td>-0.004909</td>
      <td>-0.080100</td>
      <td>-0.003308</td>
    </tr>
    <tr>
      <th>5</th>
      <td>-10.188132</td>
      <td>-0.000555</td>
      <td>-0.000587</td>
      <td>-0.041603</td>
      <td>-0.000990</td>
      <td>-0.005956</td>
      <td>-0.008254</td>
      <td>-0.023400</td>
      <td>-0.032593</td>
      <td>-0.061880</td>
      <td>...</td>
      <td>-0.056071</td>
      <td>-0.030024</td>
      <td>0.052833</td>
      <td>-0.038149</td>
      <td>-0.042217</td>
      <td>-0.107069</td>
      <td>-0.038814</td>
      <td>0.019141</td>
      <td>-0.089063</td>
      <td>-0.003123</td>
    </tr>
    <tr>
      <th>6</th>
      <td>-4.696624</td>
      <td>0.087019</td>
      <td>0.022476</td>
      <td>0.068921</td>
      <td>-0.200872</td>
      <td>-0.088585</td>
      <td>0.084472</td>
      <td>-0.050343</td>
      <td>0.062190</td>
      <td>-0.034068</td>
      <td>...</td>
      <td>-0.041652</td>
      <td>-0.046297</td>
      <td>-0.032799</td>
      <td>0.014693</td>
      <td>-0.286354</td>
      <td>-0.072298</td>
      <td>0.229458</td>
      <td>0.103750</td>
      <td>0.052720</td>
      <td>-0.094161</td>
    </tr>
    <tr>
      <th>7</th>
      <td>-9.695491</td>
      <td>-0.000492</td>
      <td>-0.000397</td>
      <td>-0.000271</td>
      <td>-0.000577</td>
      <td>-0.004215</td>
      <td>-0.002173</td>
      <td>-0.001870</td>
      <td>-0.002409</td>
      <td>-0.003127</td>
      <td>...</td>
      <td>-0.036599</td>
      <td>-0.040486</td>
      <td>-0.014132</td>
      <td>-0.008360</td>
      <td>-0.003225</td>
      <td>-0.002326</td>
      <td>-0.001465</td>
      <td>-0.007164</td>
      <td>-0.004659</td>
      <td>0.000013</td>
    </tr>
    <tr>
      <th>8</th>
      <td>-6.024387</td>
      <td>-0.007143</td>
      <td>-0.010259</td>
      <td>-0.046641</td>
      <td>-0.034966</td>
      <td>0.056934</td>
      <td>0.012818</td>
      <td>0.040539</td>
      <td>0.104894</td>
      <td>0.079651</td>
      <td>...</td>
      <td>-0.029042</td>
      <td>0.079349</td>
      <td>-0.017436</td>
      <td>0.021008</td>
      <td>-0.067486</td>
      <td>-0.120647</td>
      <td>-0.120105</td>
      <td>-0.044941</td>
      <td>-0.008850</td>
      <td>-0.033903</td>
    </tr>
    <tr>
      <th>9</th>
      <td>-8.194469</td>
      <td>0.000054</td>
      <td>-0.000283</td>
      <td>-0.000571</td>
      <td>-0.000219</td>
      <td>-0.015695</td>
      <td>-0.005539</td>
      <td>-0.002578</td>
      <td>-0.001912</td>
      <td>-0.002804</td>
      <td>...</td>
      <td>-0.010609</td>
      <td>-0.018612</td>
      <td>-0.045792</td>
      <td>-0.009738</td>
      <td>-0.005582</td>
      <td>0.034933</td>
      <td>0.029350</td>
      <td>0.033669</td>
      <td>0.045969</td>
      <td>0.003467</td>
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
<h3 id="Illustrate-Hidden-Layers-Perceptrons">Illustrate Hidden Layers Perceptrons<a class="anchor-link" href="#Illustrate-Hidden-Layers-Perceptrons">&#182;</a></h3><p>Each perceptron in the hidden layer learned something from the training process. What it learned is represented by input theta parameters for it. Each perceptron in the hidden layer has 28x28 input thetas (one for each input image pizel). Each theta represents how valuable each pixel is for this particuar perceptron. So let's try to plot how valuable each pixel of input image is for each perceptron based on its theta values.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># How many images to display.</span>
<span class="n">numbers_to_display</span> <span class="o">=</span> <span class="mi">9</span>

<span class="c1"># Calculate the number of cells that will hold all the images.</span>
<span class="n">num_cells</span> <span class="o">=</span> <span class="n">math</span><span class="o">.</span><span class="n">ceil</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">))</span>

<span class="c1"># Make the plot a little bit bigger than default one.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">10</span><span class="p">))</span>

<span class="c1"># Go through the thetas and print them.</span>
<span class="k">for</span> <span class="n">plot_index</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">numbers_to_display</span><span class="p">):</span>
    <span class="c1"># Extrace thetas data.</span>
    <span class="n">digit_pixels</span> <span class="o">=</span> <span class="n">thetas</span><span class="p">[</span><span class="n">plot_index</span><span class="p">][</span><span class="mi">1</span><span class="p">:]</span>

    <span class="c1"># Calculate image size (remember that each picture has square proportions).</span>
    <span class="n">image_size</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">math</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">digit_pixels</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]))</span>
    
    <span class="c1"># Convert image vector into the matrix of pixels.</span>
    <span class="n">frame</span> <span class="o">=</span> <span class="n">digit_pixels</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">image_size</span><span class="p">,</span> <span class="n">image_size</span><span class="p">))</span>
    
    <span class="c1"># Plot the thetas matrix.</span>
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
    <span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">costs</span><span class="p">[</span><span class="n">index</span><span class="p">])),</span> <span class="n">costs</span><span class="p">[</span><span class="n">index</span><span class="p">],</span> <span class="n">label</span><span class="o">=</span><span class="n">label_map</span><span class="p">[</span><span class="n">labels</span><span class="p">[</span><span class="n">index</span><span class="p">]])</span>

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
<img src="data:image/png;base64,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PvooF154IVprLrvsMq64IjRlTHJyMn369GHDhg3k5uYC0LdvX37/+98zatQogsEgVquVZ555hu7du0f83E5ExFJnR8rJps4G6PHxFwzzfsn/LDyLgX9uON+PEKIlSOrsyGurqbPbHCuhngLIcwpCCNGY6AoK2o/fsOBXrftwiBBCtFXRFRRqego+Q4KCEEI0JqqCgk378WPBpyT3kRBCNCa6ggJ+/MqCTwXQfsmUKoQQDUVXUNChoOBVfrwHD7R2c4QQos2JqqDgqOkpeA0/ngPFrd0cIUQrqU2d3a9fPwYMGMCf/vSnek8zR7OoeXgNwE6Ag9jxKj/u4mISzm3tFgkhWkPdNBf79+/n2muvpby8nAceeKBeOb/fj8USVX8mo6unYFcBfNjwmh6qi0tbuzlCiDagffv2zJw5k6effhqtNbNnz2b8+PFcdNFFjBw5EoDHHnuMIUOGkJWVxf333w9AZWUll112GQMGDKB///68/vrrANxzzz307duXrKws7rzzzlY7r5MVVSHQRhAfVvxmNZ7SQ63dHCGi3t7/+z88G5s3dba9T2863nffCe3Ts2dPAoFAOC/RV199xdq1a0lJSWHhwoVs3ryZFStWoLVm/PjxLFmyhOLiYtLT03n33XcBOHToEKWlpbz55psUFhailKKsrKxZz60lRLSnoJQao5T6Vim1RSl1TyPbpyilipVSBTWvGyPZHgcBvNgImF4JCkKIJl1yySWkpKQAsHDhQhYuXMjAgQMZNGgQhYWFbN68mczMTD788EPuvvtuli5dSmJiIomJiTgcDn7+85/zn//8B6fT2cpncuIi1lNQSpnAM8AlQBGwUik1X2u9oUHR17XW0yLVjrpilMaHDW34cJe5WuKQQoijONFf9JGybds2TNOkffv2AMTGxoa3aa259957+eUvf3nEfl999RULFizgt7/9LSNHjmT69OmsWLGCjz/+mHnz5vH000/zySeftNh5NIdIXj7KBbZorbcBKKXmAlcADYNCi4lB48GGtnjxlsmdBkIIKC4u5qabbmLatGkodWRetNGjR/O73/2OSZMmERcXx65du7Barfj9flJSUvjpT39KUlISs2bNwuVyUVVVxaWXXkpeXh49e/ZshTM6NZEMCp2BnXWWi4ChjZS7Uil1AbAJuF1rvbNhAaXUVGAqQLdu3U66QTGGxqfs+A0f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
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
<pre>Training Precision: 93.8333%
Test Precision: 82.9000%
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Plot-Test-Dataset-Predictions">Plot Test Dataset Predictions<a class="anchor-link" href="#Plot-Test-Dataset-Predictions">&#182;</a></h3><p>In order to illustrate how our model classifies unknown examples let's plot first 64 predictions for testing dataset. All green clothes on the plot below have been recognized corrctly but all the red clothes have not been recognized correctly by our classifier. On top of each image you may see the clothes class (type) that has been recognized on the image.</p>

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
