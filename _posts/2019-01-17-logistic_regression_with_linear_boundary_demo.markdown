---
permalink: /tutorial/logistic_regression_with_linear_boundary
---
<html>
<head><meta charset="utf-8" />

<title>logistic_regression_with_linear_boundary_demo</title>

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
<h1 id="Logistic-Regression-With-Linear-Boundary-Demo">Logistic Regression With Linear Boundary Demo<a class="anchor-link" href="#Logistic-Regression-With-Linear-Boundary-Demo">&#182;</a></h1><p><em>Source: 🤖<a href="https://github.com/trekhleb/homemade-machine-learning">Homemade Machine Learning</a> repository</em></p>
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
<blockquote><p><strong>Demo Project:</strong> In this example we will try to classify Iris flowers into tree categories (<code>Iris setosa</code>, <code>Iris virginica</code> and <code>Iris versicolor</code>) based on <code>petal_length</code> and <code>petal_width</code> parameters.</p>
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
<h3 id="Load-the-Data">Load the Data<a class="anchor-link" href="#Load-the-Data">&#182;</a></h3><p>In this demo we will use <a href="http://archive.ics.uci.edu/ml/datasets/Iris">Iris data set</a>.</p>
<p>The data set consists of several samples from each of three species of Iris (<code>Iris setosa</code>, <code>Iris virginica</code> and <code>Iris versicolor</code>). Four features were measured from each sample: the length and the width of the sepals and petals, in centimeters. Based on the combination of these four features, <a href="https://en.wikipedia.org/wiki/Iris_flower_data_set">Ronald Fisher</a> developed a linear discriminant model to distinguish the species from each other.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Load the data.</span>
<span class="n">data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;../../data/iris.csv&#39;</span><span class="p">)</span>

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
      <th>sepal_length</th>
      <th>sepal_width</th>
      <th>petal_length</th>
      <th>petal_width</th>
      <th>class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5.1</td>
      <td>3.5</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>SETOSA</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4.9</td>
      <td>3.0</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>SETOSA</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.7</td>
      <td>3.2</td>
      <td>1.3</td>
      <td>0.2</td>
      <td>SETOSA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.6</td>
      <td>3.1</td>
      <td>1.5</td>
      <td>0.2</td>
      <td>SETOSA</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5.0</td>
      <td>3.6</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>SETOSA</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5.4</td>
      <td>3.9</td>
      <td>1.7</td>
      <td>0.4</td>
      <td>SETOSA</td>
    </tr>
    <tr>
      <th>6</th>
      <td>4.6</td>
      <td>3.4</td>
      <td>1.4</td>
      <td>0.3</td>
      <td>SETOSA</td>
    </tr>
    <tr>
      <th>7</th>
      <td>5.0</td>
      <td>3.4</td>
      <td>1.5</td>
      <td>0.2</td>
      <td>SETOSA</td>
    </tr>
    <tr>
      <th>8</th>
      <td>4.4</td>
      <td>2.9</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>SETOSA</td>
    </tr>
    <tr>
      <th>9</th>
      <td>4.9</td>
      <td>3.1</td>
      <td>1.5</td>
      <td>0.1</td>
      <td>SETOSA</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Plot-the-Data">Plot the Data<a class="anchor-link" href="#Plot-the-Data">&#182;</a></h3><p>Let's take two parameters <code>petal_length</code> and <code>petal_width</code> for each flower into consideration and plot the dependency of the Iris class on these two parameters.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># List of suppported Iris classes.</span>
<span class="n">iris_types</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;SETOSA&#39;</span><span class="p">,</span> <span class="s1">&#39;VERSICOLOR&#39;</span><span class="p">,</span> <span class="s1">&#39;VIRGINICA&#39;</span><span class="p">]</span>

<span class="c1"># Pick the Iris parameters for consideration.</span>
<span class="n">x_axis</span> <span class="o">=</span> <span class="s1">&#39;petal_length&#39;</span>
<span class="n">y_axis</span> <span class="o">=</span> <span class="s1">&#39;petal_width&#39;</span>

<span class="c1"># Plot the scatter for every type of Iris.</span>
<span class="k">for</span> <span class="n">iris_type</span> <span class="ow">in</span> <span class="n">iris_types</span><span class="p">:</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span>
        <span class="n">data</span><span class="p">[</span><span class="n">x_axis</span><span class="p">][</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;class&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="n">iris_type</span><span class="p">],</span>
        <span class="n">data</span><span class="p">[</span><span class="n">y_axis</span><span class="p">][</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;class&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="n">iris_type</span><span class="p">],</span>
        <span class="n">label</span><span class="o">=</span><span class="n">iris_type</span>
    <span class="p">)</span>

<span class="c1"># Plot the data.    </span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="n">x_axis</span> <span class="o">+</span> <span class="s1">&#39; (cm)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="n">y_axis</span> <span class="o">+</span> <span class="s1">&#39; (cm)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Iris Types&#39;</span><span class="p">)</span>
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
<img src="data:image/png;base64,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V5599tma/g1N351NO3bsoKysjM6dO/Phhx/yrW99K9shSYalYxGbMMcMWz+RSJ1FJmoykpWtGAszMXy+LrH2kEaOHMmcOXNYtGgR27dvr/NXezxz587lvffeo6ysjKuvvrqmvXr67muuuYa7776bJ554Imq//v3789prr1FZWRl7yJppu2vbvHkz77//Pr169YobR8+ePXn//ffZsmVLVHvt6b6rnzG89957uDv33HNPo+9Pmpd0LGIT5phh6ycSqbPIRE1GsrIVY2Emhr27JdYe0l577cWJJ57IRRddVPPXfxgtW7bk9ttvZ8qUKXzyySesXr2aN998s2Z79dTatfXs2ZPy8nKuvvpqPJgIcc2aNcyaNYuhQ4eyfft2pkyZAkRu/VxxxRWMGTOGPffcM24Mbdu25YILLuDyyy+vSTZTpkxh+/btUetCAOy5557ceeed/Nd//Re7d++OdzhppsIueNOqRStaWstG+4WtgQhbP5FInUUmajKSla0YCzMxDP0ttIpZe6FVm0h7kkaPHs1rr70WlRhinzFUP2SurUuXLowePZp77rmHrVu3csEFF9CvXz8OOeQQVqxYwYQJE+rsc9999/Hhhx/Sq1cvBgwYwJgxY9h3330xM5566immT5/OQQcdRO/evSkuLub666+v2XfOnDl069at5uvll1/mhhtuoLi4mN69e3PQQQcxffp0nnrqKSLrLUUbNGgQhxxyiJYPLTDDDhzGhGMm0KVtFwyjS9suTDx2ItcOvjaq7drB1zLx2ImN9ptwzIRQD1HjnTfevmH7Jdo3W7IVY8FOu53qUUkSTdNui+QeTbvdmEPOUiIQyVHpqFnIJbked+EmBhHJSemoWcgl+RB3YT5jEJGclY6ahVySD3ErMYhITklHzUIuyYe4lRhEJKeko2Yhl+RD3EoMIpJT0lGzkEvyIW4lhhQ58cQTee6556Labr/9dk477TQGDBgAwN/+9jf23ntvysrK6Nu3Lz//+c+j+s+ePZsjjjiCvn37UlZWxtlnn837778PwJgxY3j88ccBGDJkCOXlX404q6ioYMiQITXnGD58eM22Z599lvLycvr168egQYO44ooros5ZVlbGOeeck5pfgkgKpKNmIZfkQ9walZQiDU27ffHFF9e0HXfcccycOZMdO3YwaNAgvvvd7zJ48GCWLVvGT3/6U5555pma8f/PPPMMa9asoXv37nXO99FHH/Hss89y2mmn1RvTsmXLuOSSS5g1axZ9+/alsrKSSZMm1WxfuXIllZWVzJs3j23bttG2bdtU/CpEkjbswGGhC99y6QM1rFyPu2ATQ6rHESc67XabNm0oKytj/fr1ANx4441ceeWVUUVhDc1eOm7cOK677roGE8NNN93EVVddRd++fYHI/Es/+clParZPmzaN888/n5UrVzJjxgzOPffchN6zSKIysZZDrtUI5Fo8YRRkYkjHOOLa026PHDkyatrteD799FPefPNNjj/+eCAyVXbsraWGHH300Tz11FPMnTuXdu3axe2zbNmyOreOanv00Ud5/vnnWbVqFXfddZcSg6RVvP/vwq7bEK9fPtQ25Fo8YRXkM4Z0jSOub9rt2ubNm8ehhx5K165dOeWUU+jcue5IhE2bNlFWVkbv3r255ZZb6j3f+PHjmThxYpNiraiooKSkhO7duzN06FAWL17MJ5980qRjiYQR7/+7sOs2xOuXD7UNuRZPWAWZGNI1jjjMtNvHHXccr732GsuXL+f++++vWSqzf//+LFq0CICOHTuyZMkSxo4dy9atW+s930knncSOHTuYP39+3O39+/evM/12tWnTprFq1Sp69OhBz5492bx5c52pvUVSKRNrOeRajUCuxRNWQSaGdI0jTmTa7dLSUn71q19x4403AvCLX/yC6667jpUrV9b02b59e6PnHD9+PDfddFPcbePGjeP666/njTfeAKCqqop7772XqqoqHnvsMZYuXcqaNWtYs2YNM2bM0EypklaZWMsh12oEci2esAoyMaRzHHG8abfr8+///u/84x//YM2aNQwcOJA77riD73//+/Tp04fBgwezcuXKRu/7f/vb36ZTp05xtx1yyCHcfvvtjB49moMPPpgBAwbwzjvvMG/ePLp27cp+++1X0/f4449nxYoVbNiwIbE3LBJSvP/vwq7bEK9fPtQ25Fo8YRXstNv5OFIgn2jabYlHo5KyG0/YabcLNjFIeunfQyT35MR6DGa2PzAF+DrgwCR3vyOmjwF3AN8GtgNj3H1ROuMSkWhh/5IfduCwhPo2Z8lcCeTSVUQ8ab1iMLMuQBd3X2Rm7YCFwOnuvqJWn28DPyWSGI4E7nD3Ixs6bn1XDH379q23bkAyx91ZtWqVrhjyROxYe4jc069dNwCRe+Mj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
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
<h3 id="Prepara-the-Data-for-Training">Prepara the Data for Training<a class="anchor-link" href="#Prepara-the-Data-for-Training">&#182;</a></h3><p>Let's extract <code>petal_length</code> and <code>petal_width</code> data and form a training feature set and let's also form out training labels set.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Get total number of Iris examples.</span>
<span class="n">num_examples</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>

<span class="c1"># Get features.</span>
<span class="n">x_train</span> <span class="o">=</span> <span class="n">data</span><span class="p">[[</span><span class="n">x_axis</span><span class="p">,</span> <span class="n">y_axis</span><span class="p">]]</span><span class="o">.</span><span class="n">values</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">num_examples</span><span class="p">,</span> <span class="mi">2</span><span class="p">))</span>
<span class="c1"># Get labels.</span>
<span class="n">y_train</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="s1">&#39;class&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">values</span><span class="o">.</span><span class="n">reshape</span><span class="p">((</span><span class="n">num_examples</span><span class="p">,</span> <span class="mi">1</span><span class="p">))</span>
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
<span class="n">max_iterations</span> <span class="o">=</span> <span class="mi">1000</span>  <span class="c1"># Max number of gradient descent iterations.</span>
<span class="n">regularization_param</span> <span class="o">=</span> <span class="mi">0</span>  <span class="c1"># Helps to fight model overfitting.</span>
<span class="n">polynomial_degree</span> <span class="o">=</span> <span class="mi">0</span>  <span class="c1"># The degree of additional polynomial features.</span>
<span class="n">sinusoid_degree</span> <span class="o">=</span> <span class="mi">0</span>  <span class="c1"># The degree of sinusoid parameter multipliers of additional features.</span>

<span class="c1"># Init logistic regression instance.</span>
<span class="n">logistic_regression</span> <span class="o">=</span> <span class="n">LogisticRegression</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">polynomial_degree</span><span class="p">,</span> <span class="n">sinusoid_degree</span><span class="p">)</span>

<span class="c1"># Train logistic regression.</span>
<span class="p">(</span><span class="n">thetas</span><span class="p">,</span> <span class="n">costs</span><span class="p">)</span> <span class="o">=</span> <span class="n">logistic_regression</span><span class="o">.</span><span class="n">train</span><span class="p">(</span><span class="n">regularization_param</span><span class="p">,</span> <span class="n">max_iterations</span><span class="p">)</span>

<span class="c1"># Print model parameters that have been learned.</span>
<span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">thetas</span><span class="p">,</span> <span class="n">columns</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;Theta 1&#39;</span><span class="p">,</span> <span class="s1">&#39;Theta 2&#39;</span><span class="p">,</span> <span class="s1">&#39;Theta 3&#39;</span><span class="p">],</span> <span class="n">index</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;SETOSA&#39;</span><span class="p">,</span> <span class="s1">&#39;VERSICOLOR&#39;</span><span class="p">,</span> <span class="s1">&#39;VIRGINICA&#39;</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[6]:</div>



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
      <th>Theta 1</th>
      <th>Theta 2</th>
      <th>Theta 3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>SETOSA</th>
      <td>30.291853</td>
      <td>-8.404206</td>
      <td>-12.313125</td>
    </tr>
    <tr>
      <th>VERSICOLOR</th>
      <td>-2.858904</td>
      <td>1.546523</td>
      <td>-3.107221</td>
    </tr>
    <tr>
      <th>VIRGINICA</th>
      <td>-45.349540</td>
      <td>5.766294</td>
      <td>10.458614</td>
    </tr>
  </tbody>
</table>
</div>
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
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Draw gradient descent progress for each label.</span>
<span class="n">labels</span> <span class="o">=</span> <span class="n">logistic_regression</span><span class="o">.</span><span class="n">unique_labels</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">costs</span><span class="p">[</span><span class="mi">0</span><span class="p">])),</span> <span class="n">costs</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">label</span><span class="o">=</span><span class="n">labels</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">costs</span><span class="p">[</span><span class="mi">1</span><span class="p">])),</span> <span class="n">costs</span><span class="p">[</span><span class="mi">1</span><span class="p">],</span> <span class="n">label</span><span class="o">=</span><span class="n">labels</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">costs</span><span class="p">[</span><span class="mi">2</span><span class="p">])),</span> <span class="n">costs</span><span class="p">[</span><span class="mi">2</span><span class="p">],</span> <span class="n">label</span><span class="o">=</span><span class="n">labels</span><span class="p">[</span><span class="mi">2</span><span class="p">])</span>

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
<h3 id="Calculate-Model-Training-Precision">Calculate Model Training Precision<a class="anchor-link" href="#Calculate-Model-Training-Precision">&#182;</a></h3><p>Calculate how many flowers from the training set have been guessed correctly.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Make training set predictions.</span>
<span class="n">y_train_predictions</span> <span class="o">=</span> <span class="n">logistic_regression</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_train</span><span class="p">)</span>

<span class="c1"># Check what percentage of them are actually correct.</span>
<span class="n">precision</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">y_train_predictions</span> <span class="o">==</span> <span class="n">y_train</span><span class="p">)</span> <span class="o">/</span> <span class="n">y_train</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">*</span> <span class="mi">100</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Precision: </span><span class="si">{:5.4f}</span><span class="s1">%&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">precision</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Precision: 96.0000%
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Draw-Decision-Boundaries">Draw Decision Boundaries<a class="anchor-link" href="#Draw-Decision-Boundaries">&#182;</a></h3><p>Let's build our decision boundaries. These are the lines that distinguish classes from each other. This will give us a pretty clear overview of how successfull our training process was. You should see clear distinguishment of three sectors on the data plain.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Get the number of training examples.</span>
<span class="n">num_examples</span> <span class="o">=</span> <span class="n">x_train</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>

<span class="c1"># Set up how many calculations we want to do along every axis. </span>
<span class="n">samples</span> <span class="o">=</span> <span class="mi">150</span>

<span class="c1"># Generate test ranges for x and y axis.</span>
<span class="n">x_min</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">min</span><span class="p">(</span><span class="n">x_train</span><span class="p">[:,</span> <span class="mi">0</span><span class="p">])</span>
<span class="n">x_max</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">max</span><span class="p">(</span><span class="n">x_train</span><span class="p">[:,</span> <span class="mi">0</span><span class="p">])</span>

<span class="n">y_min</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">min</span><span class="p">(</span><span class="n">x_train</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">])</span>
<span class="n">y_max</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">max</span><span class="p">(</span><span class="n">x_train</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">])</span>

<span class="n">X</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="n">x_min</span><span class="p">,</span> <span class="n">x_max</span><span class="p">,</span> <span class="n">samples</span><span class="p">)</span>
<span class="n">Y</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="n">y_min</span><span class="p">,</span> <span class="n">y_max</span><span class="p">,</span> <span class="n">samples</span><span class="p">)</span>

<span class="c1"># z axis will contain our predictions. So let&#39;s get predictions for every pair of x and y.</span>
<span class="n">Z_setosa</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">((</span><span class="n">samples</span><span class="p">,</span> <span class="n">samples</span><span class="p">))</span>
<span class="n">Z_versicolor</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">((</span><span class="n">samples</span><span class="p">,</span> <span class="n">samples</span><span class="p">))</span>
<span class="n">Z_virginica</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">zeros</span><span class="p">((</span><span class="n">samples</span><span class="p">,</span> <span class="n">samples</span><span class="p">))</span>

<span class="k">for</span> <span class="n">x_index</span><span class="p">,</span> <span class="n">x</span> <span class="ow">in</span> <span class="nb">enumerate</span><span class="p">(</span><span class="n">X</span><span class="p">):</span>
    <span class="k">for</span> <span class="n">y_index</span><span class="p">,</span> <span class="n">y</span> <span class="ow">in</span> <span class="nb">enumerate</span><span class="p">(</span><span class="n">Y</span><span class="p">):</span>
        <span class="n">data</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">array</span><span class="p">([[</span><span class="n">x</span><span class="p">,</span> <span class="n">y</span><span class="p">]])</span>
        <span class="n">prediction</span> <span class="o">=</span> <span class="n">logistic_regression</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">data</span><span class="p">)[</span><span class="mi">0</span><span class="p">][</span><span class="mi">0</span><span class="p">]</span>
        <span class="k">if</span> <span class="n">prediction</span> <span class="o">==</span> <span class="s1">&#39;SETOSA&#39;</span><span class="p">:</span>
            <span class="n">Z_setosa</span><span class="p">[</span><span class="n">x_index</span><span class="p">][</span><span class="n">y_index</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>
        <span class="k">elif</span> <span class="n">prediction</span> <span class="o">==</span> <span class="s1">&#39;VERSICOLOR&#39;</span><span class="p">:</span>
            <span class="n">Z_versicolor</span><span class="p">[</span><span class="n">x_index</span><span class="p">][</span><span class="n">y_index</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>
        <span class="k">elif</span> <span class="n">prediction</span> <span class="o">==</span> <span class="s1">&#39;VIRGINICA&#39;</span><span class="p">:</span>
            <span class="n">Z_virginica</span><span class="p">[</span><span class="n">x_index</span><span class="p">][</span><span class="n">y_index</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>

<span class="c1"># Now, when we have x, y and z axes being setup and calculated we may print decision boundaries.</span>
<span class="k">for</span> <span class="n">iris_type</span> <span class="ow">in</span> <span class="n">iris_types</span><span class="p">:</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span>
        <span class="n">x_train</span><span class="p">[(</span><span class="n">y_train</span> <span class="o">==</span> <span class="n">iris_type</span><span class="p">)</span><span class="o">.</span><span class="n">flatten</span><span class="p">(),</span> <span class="mi">0</span><span class="p">],</span>
        <span class="n">x_train</span><span class="p">[(</span><span class="n">y_train</span> <span class="o">==</span> <span class="n">iris_type</span><span class="p">)</span><span class="o">.</span><span class="n">flatten</span><span class="p">(),</span> <span class="mi">1</span><span class="p">],</span>
        <span class="n">label</span><span class="o">=</span><span class="n">iris_type</span>
    <span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">contour</span><span class="p">(</span><span class="n">X</span><span class="p">,</span> <span class="n">Y</span><span class="p">,</span> <span class="n">Z_setosa</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">contour</span><span class="p">(</span><span class="n">X</span><span class="p">,</span> <span class="n">Y</span><span class="p">,</span> <span class="n">Z_versicolor</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">contour</span><span class="p">(</span><span class="n">X</span><span class="p">,</span> <span class="n">Y</span><span class="p">,</span> <span class="n">Z_virginica</span><span class="p">)</span>
    
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="n">x_axis</span> <span class="o">+</span> <span class="s1">&#39; (cm)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="n">y_axis</span> <span class="o">+</span> <span class="s1">&#39; (cm)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Iris Types&#39;</span><span class="p">)</span>
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
    </div>
  </div>
</body>

 


</html>
