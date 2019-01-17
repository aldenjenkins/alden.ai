---
permalink: /tutorial/univariate_linear_regression
---
<html>
<head><meta charset="utf-8" />

<title>univariate_linear_regression_demo</title>

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
<h1 id="Univariate-Linear-Regression-Demo">Univariate Linear Regression Demo<a class="anchor-link" href="#Univariate-Linear-Regression-Demo">&#182;</a></h1><p><em>Source: 🤖<a href="https://github.com/trekhleb/homemade-machine-learning">Homemade Machine Learning</a> repository</em></p>
<blockquote><p>☝Before moving on with this demo you might want to take a look at:</p>
<ul>
<li>📗<a href="https://github.com/trekhleb/homemade-machine-learning/tree/master/homemade/linear_regression">Math behind the Linear Regression</a></li>
<li>⚙️<a href="https://github.com/trekhleb/homemade-machine-learning/blob/master/homemade/linear_regression/linear_regression.py">Linear Regression Source Code</a></li>
</ul>
</blockquote>
<p><strong>Linear regression</strong> is a linear model, e.g. a model that assumes a linear relationship between the input variables <code>(x)</code> and the single output variable <code>(y)</code>. More specifically, that output variable <code>(y)</code> can be calculated from a linear combination of the input variables <code>(x)</code>.</p>
<p><strong>Univariate Linear Regression</strong> is a linear regression that has only <em>one</em> input parameter and one output label.</p>
<blockquote><p><strong>Demo Project:</strong> In this demo we will build a model that will predict <code>Happiness.Score</code> for the countries based on <code>Economy.GDP.per.Capita</code> parameter.</p>
</blockquote>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># To make debugging of linear_regression module easier we enable imported modules autoreloading feature.</span>
<span class="c1"># By doing this you may change the code of linear_regression library and all these changes will be available here.</span>
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
<li><a href="https://github.com/trekhleb/homemade-machine-learning/blob/master/src/linear_regression/linear_regression.py">linear_regression</a> - custom implementation of linear regression</li>
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

<span class="c1"># Import custom linear regression implementation.</span>
<span class="kn">from</span> <span class="nn">homemade.linear_regression</span> <span class="k">import</span> <span class="n">LinearRegression</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Load-the-Data">Load the Data<a class="anchor-link" href="#Load-the-Data">&#182;</a></h3><p>In this demo we will use <a href="https://www.kaggle.com/unsdsn/world-happiness#2017.csv">World Happindes Dataset</a> for 2017.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Load the data.</span>
<span class="n">data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;../../data/world-happiness-report-2017.csv&#39;</span><span class="p">)</span>

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
      <th>Country</th>
      <th>Happiness.Rank</th>
      <th>Happiness.Score</th>
      <th>Whisker.high</th>
      <th>Whisker.low</th>
      <th>Economy..GDP.per.Capita.</th>
      <th>Family</th>
      <th>Health..Life.Expectancy.</th>
      <th>Freedom</th>
      <th>Generosity</th>
      <th>Trust..Government.Corruption.</th>
      <th>Dystopia.Residual</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Norway</td>
      <td>1</td>
      <td>7.537</td>
      <td>7.594445</td>
      <td>7.479556</td>
      <td>1.616463</td>
      <td>1.533524</td>
      <td>0.796667</td>
      <td>0.635423</td>
      <td>0.362012</td>
      <td>0.315964</td>
      <td>2.277027</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Denmark</td>
      <td>2</td>
      <td>7.522</td>
      <td>7.581728</td>
      <td>7.462272</td>
      <td>1.482383</td>
      <td>1.551122</td>
      <td>0.792566</td>
      <td>0.626007</td>
      <td>0.355280</td>
      <td>0.400770</td>
      <td>2.313707</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Iceland</td>
      <td>3</td>
      <td>7.504</td>
      <td>7.622030</td>
      <td>7.385970</td>
      <td>1.480633</td>
      <td>1.610574</td>
      <td>0.833552</td>
      <td>0.627163</td>
      <td>0.475540</td>
      <td>0.153527</td>
      <td>2.322715</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Switzerland</td>
      <td>4</td>
      <td>7.494</td>
      <td>7.561772</td>
      <td>7.426227</td>
      <td>1.564980</td>
      <td>1.516912</td>
      <td>0.858131</td>
      <td>0.620071</td>
      <td>0.290549</td>
      <td>0.367007</td>
      <td>2.276716</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Finland</td>
      <td>5</td>
      <td>7.469</td>
      <td>7.527542</td>
      <td>7.410458</td>
      <td>1.443572</td>
      <td>1.540247</td>
      <td>0.809158</td>
      <td>0.617951</td>
      <td>0.245483</td>
      <td>0.382612</td>
      <td>2.430182</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Netherlands</td>
      <td>6</td>
      <td>7.377</td>
      <td>7.427426</td>
      <td>7.326574</td>
      <td>1.503945</td>
      <td>1.428939</td>
      <td>0.810696</td>
      <td>0.585384</td>
      <td>0.470490</td>
      <td>0.282662</td>
      <td>2.294804</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Canada</td>
      <td>7</td>
      <td>7.316</td>
      <td>7.384403</td>
      <td>7.247597</td>
      <td>1.479204</td>
      <td>1.481349</td>
      <td>0.834558</td>
      <td>0.611101</td>
      <td>0.435540</td>
      <td>0.287372</td>
      <td>2.187264</td>
    </tr>
    <tr>
      <th>7</th>
      <td>New Zealand</td>
      <td>8</td>
      <td>7.314</td>
      <td>7.379510</td>
      <td>7.248490</td>
      <td>1.405706</td>
      <td>1.548195</td>
      <td>0.816760</td>
      <td>0.614062</td>
      <td>0.500005</td>
      <td>0.382817</td>
      <td>2.046456</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Sweden</td>
      <td>9</td>
      <td>7.284</td>
      <td>7.344095</td>
      <td>7.223905</td>
      <td>1.494387</td>
      <td>1.478162</td>
      <td>0.830875</td>
      <td>0.612924</td>
      <td>0.385399</td>
      <td>0.384399</td>
      <td>2.097538</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Australia</td>
      <td>10</td>
      <td>7.284</td>
      <td>7.356651</td>
      <td>7.211349</td>
      <td>1.484415</td>
      <td>1.510042</td>
      <td>0.843887</td>
      <td>0.601607</td>
      <td>0.477699</td>
      <td>0.301184</td>
      <td>2.065211</td>
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
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Print histograms for each feature to see how they vary.</span>
<span class="n">histohrams</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">hist</span><span class="p">(</span><span class="n">grid</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span> <span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span> <span class="mi">10</span><span class="p">))</span>
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
<h3 id="Split-the-Data-Into-Training-and-Test-Subsets">Split the Data Into Training and Test Subsets<a class="anchor-link" href="#Split-the-Data-Into-Training-and-Test-Subsets">&#182;</a></h3><p>In this step we will split our dataset into <em>training</em> and <em>testing</em> subsets (in proportion 80/20%).</p>
<p>Training data set will be used for training of our linear model. Testing dataset will be used for validating of the model. All data from testing dataset will be new to model and we may check how accurate are model predictions.</p>

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
<span class="n">train_data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">sample</span><span class="p">(</span><span class="n">frac</span><span class="o">=</span><span class="mf">0.8</span><span class="p">)</span>
<span class="n">test_data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">train_data</span><span class="o">.</span><span class="n">index</span><span class="p">)</span>

<span class="c1"># Decide what fields we want to process.</span>
<span class="n">input_param_name</span> <span class="o">=</span> <span class="s1">&#39;Economy..GDP.per.Capita.&#39;</span>
<span class="n">output_param_name</span> <span class="o">=</span> <span class="s1">&#39;Happiness.Score&#39;</span>

<span class="c1"># Split training set input and output.</span>
<span class="n">x_train</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[[</span><span class="n">input_param_name</span><span class="p">]]</span><span class="o">.</span><span class="n">values</span>
<span class="n">y_train</span> <span class="o">=</span> <span class="n">train_data</span><span class="p">[[</span><span class="n">output_param_name</span><span class="p">]]</span><span class="o">.</span><span class="n">values</span>

<span class="c1"># Split test set input and output.</span>
<span class="n">x_test</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[[</span><span class="n">input_param_name</span><span class="p">]]</span><span class="o">.</span><span class="n">values</span>
<span class="n">y_test</span> <span class="o">=</span> <span class="n">test_data</span><span class="p">[[</span><span class="n">output_param_name</span><span class="p">]]</span><span class="o">.</span><span class="n">values</span>

<span class="c1"># Plot training data.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Training Dataset&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">x_test</span><span class="p">,</span> <span class="n">y_test</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Test Dataset&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="n">input_param_name</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="n">output_param_name</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Countries Happines&#39;</span><span class="p">)</span>
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
<p>Now we may visualize the data sets to see theirs shape.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Init-and-Train-Linear-Regression-Model">Init and Train Linear Regression Model<a class="anchor-link" href="#Init-and-Train-Linear-Regression-Model">&#182;</a></h3><blockquote><p>☝🏻This is the place where you might want to play with model configuration.</p>
</blockquote>
<ul>
<li><code>polynomial_degree</code> - this parameter will allow you to add additional polynomial features of certain degree. More features - more curved the line will be.</li>
<li><code>num_iterations</code> - this is the number of iterations that gradient descent algorithm will use to find the minimum of a cost function. Low numbers may prevent gradient descent from reaching the minimum. High numbers will make the algorithm work longer without improving its accuracy.</li>
<li><code>learning_rate</code> - this is the size of the gradient descent step. Small learning step will make algorithm work longer and will probably require more iterations to reach the minimum of the cost function. Big learning steps may couse missing the minimum and growth of the cost function value with new iterations.</li>
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
<span class="n">num_iterations</span> <span class="o">=</span> <span class="mi">500</span>  <span class="c1"># Number of gradient descent iterations.</span>
<span class="n">regularization_param</span> <span class="o">=</span> <span class="mi">0</span>  <span class="c1"># Helps to fight model overfitting.</span>
<span class="n">learning_rate</span> <span class="o">=</span> <span class="mf">0.01</span>  <span class="c1"># The size of the gradient descent step.</span>
<span class="n">polynomial_degree</span> <span class="o">=</span> <span class="mi">0</span>  <span class="c1"># The degree of additional polynomial features.</span>
<span class="n">sinusoid_degree</span> <span class="o">=</span> <span class="mi">0</span>  <span class="c1"># The degree of sinusoid parameter multipliers of additional features.</span>

<span class="c1"># Init linear regression instance.</span>
<span class="n">linear_regression</span> <span class="o">=</span> <span class="n">LinearRegression</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">polynomial_degree</span><span class="p">,</span> <span class="n">sinusoid_degree</span><span class="p">)</span>

<span class="c1"># Train linear regression.</span>
<span class="p">(</span><span class="n">theta</span><span class="p">,</span> <span class="n">cost_history</span><span class="p">)</span> <span class="o">=</span> <span class="n">linear_regression</span><span class="o">.</span><span class="n">train</span><span class="p">(</span>
    <span class="n">learning_rate</span><span class="p">,</span>
    <span class="n">regularization_param</span><span class="p">,</span>
    <span class="n">num_iterations</span>
<span class="p">)</span>

<span class="c1"># Print training results.</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Initial cost: </span><span class="si">{:.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">cost_history</span><span class="p">[</span><span class="mi">0</span><span class="p">]))</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Optimized cost: </span><span class="si">{:.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">cost_history</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]))</span>

<span class="c1"># Print model parameters</span>
<span class="n">theta_table</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">({</span><span class="s1">&#39;Model Parameters&#39;</span><span class="p">:</span> <span class="n">theta</span><span class="o">.</span><span class="n">flatten</span><span class="p">()})</span>
<span class="n">theta_table</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Initial cost: 226681.86
Optimized cost: 3476.54
</pre>
</div>
</div>

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
      <th>Model Parameters</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5.340717</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1.093946</td>
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
<p>In case if cost function value increases it may mean that gradient descent missed the cost function minimum and with each step it goes further away from it. In this case you might want to reduce the learning rate parameter (the size of the gradient step).</p>
<p>From this plot you may also get an understanding of how many iterations you need to get an optimal value of the cost function. In current example you may see that there is no much sense to increase the number of gradient descent iterations over 500 since it will not reduce cost function significantly.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[7]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Plot gradient descent progress.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="n">num_iterations</span><span class="p">),</span> <span class="n">cost_history</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Iterations&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Cost&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Gradient Descent Progress&#39;</span><span class="p">)</span>
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
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAZsAAAEWCAYAAACwtjr+AAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDMuMC4xLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvDW2N/gAAIABJREFUeJzt3Xl8VfWd//HX52YPCSGQsAYImyIqIqDgWrVTRWtH22prF0WrMh3tTDt2fm1tZ8aOfbTjTGfaahdbWx1tq91tZVqq4lYX1AIuLIIQEAQEEsJOWLJ8fn+cb/AaQ0gg957k3vfz8biPe873bN/vJeSd8z3fe465OyIiIqmUiLsCIiKS+RQ2IiKScgobERFJOYWNiIiknMJGRERSTmEjIiIpp7CRjGJma8zsb8L0l83sJ3HXSUQUNpJGZnaFmb1oZnvMrDZM32Bmlorjufs33P26o92PmVWbmZtZbgfrfNXMGs1sV3itMLPvmdmQoz1+qoQ2je1g+dVm1mxmu81sp5m9YmYXp7OOkjkUNpIWZvZ54Hbgm8BgYBDwaeAMIP8Q2+SkrYLd41fuXgr0Bz5I1M6FPTlwOuF5dy8B+gF3A782s/K2K3UUxEeiu/cn8VPYSMqZWRlwK3CDu//W3Xd55GV3/4S77w/r3Wtmd5rZHDPbA5xrZu83s5fDX9brzOyrbfZ9pZmtNbN6M/tKm2VfNbOfJ81PN7N5ZrbdzF41s3OSlj1lZl8zs+fCmcmjZlYRFj8d3reHv/JP66i97t7o7kuBjwJ1wOeTjnNxOEPYHuoyMWnZF81sQzj+62b23lCeE7oEV4VlC81seFg23szmmtnWsM1HkvZ3r5l938z+FLZ70czGhGWtbXo1tOmjh2lTC3APUASMMbNzzGx9qPMm4H/Dfq83s5pQn9lmNjSpPueHOu4wsx+Y2V/M7Lqw7Orw2X/bzOqBr4byT5nZMjPbZmaPmNnIUG5h3drws7HYzE4Iyy4ys9dCmzeY2T931DZJE3fXS6+UvoAZQBOQe5j17gV2EJ3tJIBC4BzgxDA/EdgMXBrWnwDsBs4GCoBvheP8TVj+VeDnYXoYUA9cFPb1vjBfGZY/BawCjiH6hfoUcFtYVg14R/VPPlab8luBF8P0yUAtMA3IAWYCa0LdjwXWAUOTjjkmTP8/YHFYx4CTgAFAn7DNNUBu2P8WYELS51kPnBqW3w/8MqluDoztoE1XA8+G6Vzgs8AuoCz8uzQB/xnqXwScF44/OZR9F3g6bF8B7AQ+lLSvRuC6pGM1Af8QlhcBlwA1wHGh7F+AeWH9C4CFRGdcFtYZEpZtBM4K0+XA5Lj/D+jlOrORtKgAtrh7U2tB0hnGXjM7O2ndh9z9OXdvcfd97v6Uuy8O84uAXwDvCeteBvzR3Z/26OzoX4GWQ9Thk8Acd58T9jUXWEAUPq3+191XuPte4NfApG5o+1tE3WoAs4AfufuL7t7s7vcB+4HpQDPRL+gJZpbn7mvcfVXY7jrgX9z9dY+86u71wMXAGnf/X3dvcveXgd8Blycd//fu/tfw2d9/BG2abmbbgU3Ax4APuvuOsKwFuMXd94fP7BPAPe7+Uvj3uBk4zcyqiT7npe7+YKjLHWGf7/is3P27oS17ibpZ/8Pdl4VtvgFMCmc3jUApMB6wsM7GsJ/G8Dn2dfdt7v5SF9ssKaCwkXSoByqS++Hd/XR37xeWJf8crkve0MymmdmTZlZnZjuIfgG1dm8NTV7f3feE/bVnJHB5CLjt4RfomUDy9ZTkX34NQElXGnkIw4CtSXX4fJs6DCc6m6kBPkd0hlRrZr9M6oIaTnTW1V6bprXZ3yeIrhV1V5tecPd+7l7h7tPd/bGkZXXuvi9pfiiwtnXG3XcT/XsM493/Vg6sb3OsdW3mRwK3J7VtK9FZzDB3fwL4HvB9os/rLjPrG7b7MFG4rQ1ddR12e0p6KGwkHZ4n+gv+kk6s2/Y25A8As4Hh7l4G/JDoFw5E3SXDW1c0s2Ki7qX2rAN+Fn5xtr76uPttR1CnTjGzBPAB4JmkOny9TR2K3f0XAO7+gLufSfRL1om6qFq3G3OINv2lzf5K3P3vj6S+R6Dt5/IWUd0BMLM+RP8eG4j+raqSllny/CH2tw74uzbtK3L3eQDufoe7TyHqTj2GqLsRd5/v7pcAA4E/EJ2lSswUNpJy7r4d+HfgB2Z2mZmVmlnCzCYRXXfoSCmw1d33mdmpwMeTlv0WuNjMzjSzfKLrI4f6mf458AEzuyBccC8MF7nb/sJrTx1Rl9HoTqyLmeWa2XFEXX6Dia4lAfwY+HQ4WzMz62PRAIhSMzvWzM4zswJgH7CXt7sEfwJ8zczGhe0mmtkA4I/AMRYNksgLr1PCsTtjc2fb1Em/AK4xs0mhHd8gul61BvgTcKKZXRrOcG/knWdg7fkhcLOZHQ/RQBMzuzxMnxI+xzxgD9Fn1mJm+Wb2CTMrc/dGoutEh+palTRS2EhauPt/ATcBXyD6JbcZ+BHwRWBeB5veANxqZruAfyPpr1SPRnzdSHT2sxHYxru7ZlrXXUd0ZvVlovBYR/SX8GH/D7h7A/B14LnQpTP9EKt+1Mx2Ew1ymE3UhTTF3d8K+1kAXE/U/bON6OL31WHbAuA2ogvsm4j+Kr85LPtWaPejRL887waK3H0XcD5wBdFZxSbevmDfGV8F7gtt+sjhVj6c0MX2r0TXjTYSnY1dEZZtIbqW9F9En8sEomtm+zvY3++J2vNLM9sJLAEuDIv7EoX3NqKuu3qiYfUAVwJrwjafJupalJhZ1HUqIpI+oYtxPfAJd38y7vpI6unMRkTSInRh9gtdbF8muvb2QszVkjRR2IhIupxGNKpuC9HAiUvDEGfJAupGExGRlNOZjYiIpJxudhdUVFR4dXV13NUQEelVFi5cuMXdKw+3nsImqK6uZsGCBXFXQ0SkVzGztYdfS91oIiKSBgobERFJOYWNiIiknMJGRERSTmEjIiIpp7AREZGUU9iIiEjKKWyO0hPLN/ODp2riroaISI+msDlKz9XU893Ha9A95kREDk1hc5SqBxSzt7GZ2l2HfAaUiEjWU9gcpZEDoqcar9myJ+aaiIj0XAqbo1QdwmZtfUPMNRER6bkUNkdpaL9CchPGmnqd2YiIHIrC5ijl5iQY3r9YZzYiIh1Q2HSDkQOKdWYjItIBhU03qB7Qh7X1DRr+LCJyCAqbbjByQDG79zdRv+dA3FUREemRFDbdoLqidUSautJERNqjsOkGrcOf39iiQQIiIu1R2HSDYf2KyEmYzmxERA5BYdMN8nMTDOtXxBoNfxYRaZfCppuMHFCsMxsRkUNQ2HST6gF9eGPLHg1/FhFph8Kmm4wcUMyufU1sb2iMuyoiIj2OwqabtI5I050ERETeTWHTTaorigF4Q48aEBF5F4VNNxnRvw85CWNV3e64qyIi0uMobLpJfm6CkQOKqalV2IiItKWw6UZjK0sUNiIi7UhZ2JjZcDN70sxeM7OlZvbZUN7fzOaa2crwXh7KzczuMLMaM1tkZpOT9jUzrL/SzGYmlU8xs8VhmzvMzDo6RqqNGVjC2voGGptb0nE4EZFeI5VnNk3A5919AjAduNHMJgBfAh5393HA42Ee4EJgXHjNAu6EKDiAW4BpwKnALUnhcSdwfdJ2M0L5oY6RUmMrS2hqcT1ITUSkjZSFjbtvdPeXwvQuYBkwDLgEuC+sdh9waZi+BPipR14A+pnZEOACYK67b3X3bcBcYEZY1tfdX/Dom5Q/bbOv9o6RUmMHlgCoK01EpI20XLMxs2rgZOBFYJC7bwyLNgGDwvQwYF3SZutDWUfl69spp4NjtK3XLDNbYGYL6urqut6wNsaEsNGINBGRd0p52JhZCfA74HPuvjN5WTgjSen9XTo6hrvf5e5T3X1qZWXlUR+rpCCXIWWFOrMREWkjpWFjZnlEQXO/uz8YijeHLjDCe20o3wAMT9q8KpR1VF7VTnlHx0i5sQM1Ik1EpK1UjkYz4G5gmbt/K2nRbKB1RNlM4KGk8qvCqLTpwI7QFfYIcL6ZlYeBAecDj4RlO81sejjWVW321d4xUm5MZQmr6nbT0qIbcoqItMpN4b7PAK4EFpvZK6Hsy8BtwK/N7FpgLfCRsGwOcBFQAzQA1wC4+1Yz+xowP6x3q7tvDdM3APcCRcCfw4sOjpFyYwaW0HCgmU079zG0X1G6Disi0qOlLGzc/VnADrH4ve2s78CNh9jXPcA97ZQvAE5op7y+vWOkw9jKt0ekKWxERCK6g0A30/BnEZF3U9h0s4qSfMqK8qjR8GcRkYMUNt3MzDQiTUSkDYVNChwzqJQVm3fpEdEiIoHCJgWOG1LK9oZGNu3cF3dVRER6BIVNCowf3BeA5Rt3xVwTEZGeQWGTAscOLgVg2aadh1lTRCQ7KGxSoKwoj2H9inRmIyISKGxS5LghpSzXmY2ICKCwSZnxg/uyqm4P+xqb466KiEjsFDYpMn5IKc0tru/biIigsEmZgyPSNum6jYiIwiZFRlX0oSA3wfKNum4jIqKwSZGchHHs4FKd2YiIoLBJqfGDS1m2caduWyMiWU9hk0LjB/elfs8B6nbvj7sqIiKxUtik0HFDokECS9/SdRsRyW4KmxQ6YVgUNkvW74i5JiIi8VLYpFBpYR6jK/uwaIPCRkSym8ImxSYOK2PR+u1xV0NEJFYKmxSbWNWPzTv3s1nPthGRLKawSbGJVWUALNZ1GxHJYgqbFJswtC8JQ9dtRCSrKWxSrDg/l2MGleq6jYhkNYVNGpw4rIzF63foTgIikrUUNmkwsaqM+j0HeGuHBgmISHZS2KTBxKp+ACxap640EclOCps0GD+klLwc0yABEclaCps0KMjNYfzgvrzyps5sRCQ7KWzSZMrIcl5Zt53G5pa4qyIiknYKmzSZMrKcvY3NLNOTO0UkCyls0mRqdTkAC9Zsi7kmIiLpp7BJkyFlRQzrV8TCtQobEck+Cps0mjKynAVrt+rLnSKSdRQ2aTS1upzNO/ezftveuKsiIpJWKQsbM7vHzGrNbElS2VfNbIOZvRJeFyUtu9nMaszsdTO7IKl8RiirMbMvJZWPMrMXQ/mvzCw/lBeE+ZqwvDpVbeyqKSOj6zYvvamuNBHJLqk8s7kXmNFO+bfdfVJ4zQEwswnAFcDxYZsfmFmOmeUA3wcuBCYAHwvrAvxn2NdYYBtwbSi/FtgWyr8d1usRxg/uS5/8HA0SEJGsk7Kwcfenga2dXP0S4Jfuvt/d3wBqgFPDq8bdV7v7AeCXwCVmZsB5wG/D9vcBlybt674w/VvgvWH92OUkjJNHlLNAgwREJMvEcc3mM2a2KHSzlYeyYcC6pHXWh7JDlQ8Atrt7U5vyd+wrLN8R1n8XM5tlZgvMbEFdXd3Rt6wTpowsZ/mmnezc15iW44mI9ATpDps7gTHAJGAj8D9pPv47uPtd7j7V3adWVlam5ZjTRvfHHea/0dmTPhGR3i+tYePum9292d1bgB8TdZMBbACGJ61aFcoOVV4P9DOz3Dbl79hXWF4W1u8RJo8opyA3wXM1PaZKIiIpl9awMbMhSbMfBFpHqs0GrggjyUYB44C/AvOBcWHkWT7RIILZHn1R5UngsrD9TOChpH3NDNOXAU94D/piS2FeDlOry5m3akvcVRERSZtUDn3+BfA8cKyZrTeza4H/MrPFZrYIOBf4JwB3Xwr8GngNeBi4MZwBNQGfAR4BlgG/DusCfBG4ycxqiK7J3B3K7wYGhPKbgIPDpXuK08dUsHzTLrbs3h93VURE0iL38KscGXf/WDvFd7dT1rr+14Gvt1M+B5jTTvlq3u6GSy7fB1zepcqm2eljovEKL6yu5+KJQ2OujYhI6ukOAjE4cVgZJQW5um4jIllDYROD3JwE00b153ldtxGRLKGwicnpYytYU9/Ahu26T5qIZD6FTUxar9s8V6OzGxHJfAqbmBw7qJSKknyeWamwEZHMp7CJSSJhvOeYgTy9oo6m5pa4qyMiklIKmxidO76SHXsbeXnd9rirIiKSUgqbGJ01rpKchPHE8tq4qyIiklIKmxiVFeUxdWQ5TypsRCTDKWxidt74gSzftIu3NARaRDKYwiZm540fCMCTr+vsRkQyl8ImZmMHljCsXxFPLk/Pw9tEROKgsImZmXHe+IE8V7OFfY3NcVdHRCQlFDY9wAXHD2ZvYzN/WaGzGxHJTAqbHmDa6P6UF+fx58Ub466KiEhKKGx6gLycBO+bMIjHltWyv0ldaSKSeRQ2PcSFJw5h9/4mntW90kQkA3UqbMzsZ50pkyN3xpgKSgtz+fOSTXFXRUSk23X2zOb45BkzywGmdH91sld+btSV9ujSTRxo0o05RSSzdBg2Znazme0CJprZzvDaBdQCD6WlhlnkwhOGsHNfE/P0BE8RyTAdho27/4e7lwLfdPe+4VXq7gPc/eY01TFrnDUu6kqb/epbcVdFRKRbdbYb7Y9m1gfAzD5pZt8ys5EprFdWKszL4eKJQ3h4ySYaDjTFXR0RkW7T2bC5E2gws5OAzwOrgJ+mrFZZ7IMnV9FwoJlHlmqggIhkjs6GTZO7O3AJ8D13/z5QmrpqZa+pI8sZ3r+IB1/aEHdVRES6TWfDZpeZ3QxcCfzJzBJAXuqqlb0SCeODJ1fxbM0WNu3YF3d1RES6RWfD5qPAfuBT7r4JqAK+mbJaZbkPnTwMd/jDKzq7EZHM0KmwCQFzP1BmZhcD+9xd12xSpLqiD1NGlvO7heuJei9FRHq3zt5B4CPAX4HLgY8AL5rZZamsWLb7yNQqVtbuZsHabXFXRUTkqHW2G+0rwCnuPtPdrwJOBf41ddWSD5w0lNLCXH7+wtq4qyIictQ6GzYJd09+bnF9F7aVI1Ccn8uHJ1fx58WbqN+9P+7qiIgclc4GxsNm9oiZXW1mVwN/AuakrloC8IlpIzjQ3MJvFq6PuyoiIkflcPdGG2tmZ7j7/wN+BEwMr+eBu9JQv6w2blAp00b154EX36SlRQMFRKT3OtyZzXeAnQDu/qC73+TuNwG/D8skxT45fSRvbm3QI6NFpFc7XNgMcvfFbQtDWXVKaiTvcMHxgxnct5AfP7M67qqIiByxw4VNvw6WFXVnRaR9+bkJrjmjmnmr6lmyYUfc1REROSKHC5sFZnZ920Izuw5Y2NGGZnaPmdWa2ZKksv5mNtfMVob38lBuZnaHmdWY2SIzm5y0zcyw/kozm5lUPsXMFodt7jAz6+gYvdnHpo2gpCCXu57W2Y2I9E6HC5vPAdeY2VNm9j/h9RfgWuCzh9n2XmBGm7IvAY+7+zjg8TAPcCEwLrxmEd1lGjPrD9wCTCP6bs8tSeFxJ3B90nYzDnOMXqtvYR4fO3U4f1q8kfXbGuKujohIlx3u4Wmb3f104N+BNeH17+5+WriFTUfbPg1sbVN8CXBfmL4PuDSp/KceeQHoZ2ZDgAuAue6+1d23AXOBGWFZX3d/IdyN+qdt9tXeMXq1a84YhQH3PLsm7qqIiHRZbmdWcvcngSe74XiD3H1jmN4EDArTw4B1SeutD2Udla9vp7yjY7yLmc0iOpNixIgRXW1LWg3tV8TfnjSUB/66lr8/ZwyVpQVxV0lEpNNiuwtAOCNJ6ZdHDncMd7/L3ae6+9TKyspUVqVbfOa8sRxoauFHf1kVd1VERLok3WGzOXSBEd5bb4GzARietF5VKOuovKqd8o6O0euNrizh0knD+PmLa6ndpWfdiEjvke6wmQ20jiibCTyUVH5VGJU2HdgRusIeAc43s/IwMOB84JGwbKeZTQ+j0K5qs6/2jpER/uG942hsdn74lEamiUjvkbKwMbNfEN3W5lgzW29m1wK3Ae8zs5XA34R5iO6zthqoAX4M3ADg7luBrwHzw+vWUEZY5ydhm1XAn0P5oY6REUZV9OHSScO4/8W1epKniPQapodzRaZOneoLFiyIuxqd8mZ9A+/91lN88ORh/NdlJ8VdHRHJYma20N2nHm49PSagFxoxoJiZp1Xzm4XrWbZxZ9zVERE5LIVNL/WZ88bStzCPb8xZFndVREQOS2HTS/Urzucf3zuOZ1Zu4anXM2bAnYhkKIVNL3bl9JFUDyjm1j++xv6m5rirIyJySAqbXiw/N8Etf3s8q+v28JNn3oi7OiIih6Sw6eXOPXYgF54wmDseX8m6rbpJp4j0TAqbDPBvH5hATsK4ZfZSNJRdRHoihU0GGFJWxE3vO4Ynltcy+9W34q6OiMi7KGwyxDVnjOLkEf34t4eWsnmn7iwgIj2LwiZD5CSM/7n8JPY3NXPzg4vVnSYiPYrCJoOMrizhCxeM54nltfxm4frDbyAikiYKmwxz9enVTBvVn6/932sanSYiPYbCJsMkEsZ/X34SZnDjAy/py54i0iMobDLQ8P7FfPPyk1i0fgf/MWd53NUREVHYZKoLjh/MtWeO4t55a5izeGPc1RGRLKewyWBfnDGeScP78cXfLmJV3e64qyMiWUxhk8HycxN87+Mnk5+b4Lr7FrC94UDcVRKRLKWwyXBV5cX88MopbNi2lxsfeInG5pa4qyQiWUhhkwVOqe7PNz50Is/V1HPr/70Wd3VEJAvlxl0BSY/LplSxcvMufvT0aob3L2LW2WPirpKIZBGFTRb5wozxbNi+l2/MWU7/PgVcNqUq7iqJSJZQ2GSRnITxrY9MYsfeRr74u0WUF+fx3uMGxV0tEckCumaTZfJzE9z5ySmcMLQvN9z/EvNWbYm7SiKSBRQ2WaikIJf/veZURg4o5lP3zmdejQJHRFJLYZOl+vfJ54HrpzOyfx8+dd98nlPgiEgKKWyyWEVJAQ9cPy0KnHvn8+xKBY6IpIbCJssNCIEzqiI6w3l4yaa4qyQiGUhhIwwoKeAX10/n+KF9ueH+hdz/4tq4qyQiGUZhIwCU98nn/uumcc6xA/nK75dw+2Mr9WhpEek2Chs5qDg/lx9dOYUPT67i24+t4OYHF3OgSfdSE5Gjpy91yjvk5ST478snMqSskO89WcPqLXv44Sen0L9PftxVE5FeTGc28i5mxj9fcCzf+egkXlm3nUu+/ywrNu+Ku1oi0ospbOSQLj15GL+aNZ19jS186AfzeHiJnvgpIkdGYSMdOnlEObM/cwZjBpbw6Z+/xK3/95qu44hIlyls5LCGlBXxm787jatPr+ae597girue563te+Ouloj0Igob6ZT83ARf/dvj+d7HT+b1Tbt4/x3P8OTy2rirJSK9RCxhY2ZrzGyxmb1iZgtCWX8zm2tmK8N7eSg3M7vDzGrMbJGZTU7az8yw/kozm5lUPiXsvyZsa+lvZWa6eOJQ/u8fzmRQ30KuuXc+//KHxew90Bx3tUSkh4vzzOZcd5/k7lPD/JeAx919HPB4mAe4EBgXXrOAOyEKJ+AWYBpwKnBLa0CFda5P2m5G6puTPUZXlvCHG8/g+rNG8fMX3uT9dzzDovXb466WiPRgPakb7RLgvjB9H3BpUvlPPfIC0M/MhgAXAHPdfau7bwPmAjPCsr7u/oJHX4H/adK+pJsU5uXwlfdP4IHrprG3sZkP/WAetz+2ksZmDR4QkXeLK2wceNTMFprZrFA2yN1bx9ZuAlofITkMWJe07fpQ1lH5+nbK38XMZpnZAjNbUFdXdzTtyVqnj63g4c+ezfsnDuHbj63gA999Vmc5IvIucYXNme4+maiL7EYzOzt5YTgjSfmNudz9Lnef6u5TKysrU324jFVWnMftV5zMj6+ayraGA1z6/ef4xpxlupYjIgfFEjbuviG81wK/J7rmsjl0gRHeW4c6bQCGJ21eFco6Kq9qp1xS7H0TBjH3pvdwxakjuOvp1cy4/Wk9I0dEgBjCxsz6mFlp6zRwPrAEmA20jiibCTwUpmcDV4VRadOBHaG77RHgfDMrDwMDzgceCct2mtn0MArtqqR9SYr1LczjGx88kV/Omo4Bn7z7RW68/yV9L0cky8VxI85BwO/DaORc4AF3f9jM5gO/NrNrgbXAR8L6c4CLgBqgAbgGwN23mtnXgPlhvVvdfWuYvgG4FygC/hxekkbTRw/g4c+dzY+fXs33n6rhieW1fOa8sVx31igKcnPirp6IpJnpmSWRqVOn+oIFC+KuRkZav62Br/9pGX9esonqAcXc8oHjOXf8wLirJSLdwMwWJn2F5ZB60tBnyVBV5cXc+ckp/PRTp5JIGNfcO58r736RpW/tiLtqIpImChtJm7OPqeThz57Nv148gcUbdnDxd5/lpl+9wgZdzxHJeOpGC9SNll479jZy51OruOe5NwC45oxqbnjPWMqK82KumYh0RWe70RQ2gcImHhu27+Vbj67gwZfXU1KQy7VnjuJTZ46ib6FCR6Q3UNh0kcImXss27uQ7j63gkaWb6VuYy3VnjeaaM6opVeiI9GgKmy5S2PQMSzbs4PbHVzL3tc2UFeVx3ZmjuFqhI9JjKWy6SGHTsyzZsIPvPLaCx5bVUlqYy5XTR3LNGaOoLC2Iu2oikkRh00UKm55p8fod3PmXGv68ZBN5OQk+PLmKWWePZlRFn7irJiIobLpMYdOzvbFlDz9+ZjW/XbiexuYWZhw/mFlnj+bkEeWH31hEUkZh00UKm96hdtc+7pu3hp89v5ad+5o4qaqMmadX8/6JQ3QbHJEYKGy6SGHTu+ze38TvFq7nvufXsLpuDxUl+Xz81BF8YvpIBvUtjLt6IllDYdNFCpveyd15tmYL981bw+PLa8kx44LjB3PFqcM5Y0wFiYTFXUWRjNbZsInjrs8i3cbMOGtcJWeNq+TN+gZ+9sIafrNwPX9avJGq8iIunzKcy6dWMbRfUdxVFclqOrMJdGaTOfY3NfPo0s38esE6nlm5BTM4e1wlV5wynPceN4j8XN0SUKS7qButixQ2mWnd1gZ+s2Adv1m4no079tGvOI+LThzCJScN5ZTq/upmEzlKCpsuUthktuYW5+mVdfzh5Q08unQzexubGVpWyAcmDeWSk4Zx3JBSwgP9RKQLFDZdpLDJHg0Hmpj72mYeeuUtnl5RR1OLM25gCRedOIQZJwxm/GAFj0hnKWy6SGGTnbbuOcCcxRuZ/epbzF+zFXcYOaCYGccP5oKOGUGzAAAMS0lEQVQTBjOpqp+62kQ6oLDpIoWN1O3az2PLNvPwkk3MW7WFxmZnUN8Czp8wmHPHV3La6AqK8vXFUZFkCpsuUthIsh17G3lyeS0PL9nEX1bUsbexmfzcBNNHD+DcYys559iBuj+bCAqbLlPYyKHsa2xm/pqtPLm8jqdW1LK6bg8A1QOKOefYgZwxtoJTR/WnrEiPQZDso7DpIoWNdNab9Q08taKWJ5fX8vzqevY1tpAwOGFYGaeNHsD0MQM4pbo/JQX6zrRkPoVNFyls5Ejsa2zm5Te38/zqel5YVc/L67bR2OzkJIyJVWVMGzWAySP6MXlkORUlehaPZB6FTRcpbKQ77D3QzMK125i3agvPr65nyYYdNDZH/8eqBxQzeUQ5k0eWM3lEOccOLiVHI92kl9O90URiUJSfw5njKjhzXAUQnfks3rCDl9ZuY+HabTy9cgsPvrwBgD75OZxYVcYJQ8s4YVgZJwzry6iKEgWQZCSFjUgKFeblcEp1f06p7g9Ed6let3UvL70Zhc/iDTv42Qtr2d/UAkBRXg4ThvblhKF9OX5YGccN7svYgSUaci29nrrRAnWjSVyamltYVbeHJRt2sOStHSzdsJOlb+1gz4FmAMxgRP9ixg0s5ZhBJRwzqJRxg0oYU1lCYZ5CSOKlbjSRXiI3J8Gxg0s5dnApH55SBUBLi7Omfg+vb9rFis27WVG7i5Wbd/HU67U0tUR/ICZCCFVX9KF6QB+qB7w9XVVeRG6O7m4tPYfCRqQHSiSM0ZUljK4s4cIT3y5vbG5hzZY9rNi8m9c372JV7W7e2LKH+W9sPXgmBJCbMKrKiw6Gz7B+RQwrL2JovyKG9iukok+BbsMjaaWwEelF8nISjBtUyrhBpbyfIQfL3Z263ftZW9/AG1v2sLZ+D2u2NLCmfg8L1mxj9/6md+wnPzfB0LLCED5FDAshNLC0kMrSAgaWFjCgpECDFaTbKGxEMoCZMbA0CovWwQit3J2d+5rYsG0vb23fy1s79rJh2142bI/mn125hc279tH28m3CoH+fKHgG9o3eoyAqpH+ffMqL8ynvk3dwWtePpCMKG5EMZ2aUFeVRVpTHhKF9213nQFMLm3fuo273fmp37qdu1z7qdu2n9uBrH8s27mTL7gM0t7Q/qKgoL4f+ffLpV5wX3vPpX5xHWXE+fQtz6VuYR2lhLqUH33PpWxRNF+QqqDKdwkZEyM9NMLx/McP7F3e4XnOLs3XPAbY1HGBbeN+6p/Hg/NaGA2xvaGTrngO8ubWBbXsOsHNfU4f7bD1+36QgKinIpTg/h6L8XIrzcijKz6E4vIryc9+ezsuhT0Hu28vzcinMS5Cfm6AgN4f83IS6AnsIhY2IdFpOwqgM3Wmd1dzi7N7XxM59jeza18Su1vf9rfPJy6Llu/c1sb2hkb2NzTQcaKLhQDN7DzQfHInXFbkJoyA3QUFeDgW5rUEUhVHb+dbpvNwEeQkjJ5EgL8fIzTFyD04nyE0YeTkJcnOMvET03lqevKztNgkzchJGwqJBIDlh3iz6bHPMSLSuZ0YiQdI2b2/bGx/up7ARkZTKSRhlxXmUFR/9XbEPNLWw90Aze5ICqOFAEw2NrdPN7G9qZn9jC/ubWjjQ1BLNh/dovoX9jS0caG45uO6ufU3vWLexuYXGZqepuYWmFqepxQ/ZfRgHM5KC6e3p1lCKXtF6rfPAwfAyonfC8v/40InvutbX3TI2bMxsBnA7kAP8xN1vi7lKInKU8sOZSHcEV1e1hNBpanlnEDU2t9DU/HZ5c2tZm2VNzU6LOy0ene21uIf3aN/NYd7De7OTNO20tBxi29Z1Wrd1p7kFwGlpAeft9QjvLdHkwbLiNNyhIiPDxsxygO8D7wPWA/PNbLa7vxZvzUSkt0okjPyEkY++LHskMvVTOxWocffV7n4A+CVwScx1EhHJWpkaNsOAdUnz60PZO5jZLDNbYGYL6urq0lY5EZFsk6lh0ynufpe7T3X3qZWVlXFXR0QkY2Vq2GwAhifNV4UyERGJQaaGzXxgnJmNMrN84Apgdsx1EhHJWhk5Gs3dm8zsM8AjREOf73H3pTFXS0Qka2Vk2AC4+xxgTtz1EBGRzO1GExGRHkSPhQ7MrA5Ye4SbVwBburE6vYHanB3U5uxwNG0e6e6HHc6rsOkGZragM8/gziRqc3ZQm7NDOtqsbjQREUk5hY2IiKScwqZ73BV3BWKgNmcHtTk7pLzNumYjIiIppzMbERFJOYWNiIiknMLmKJnZDDN73cxqzOxLcdenu5jZPWZWa2ZLksr6m9lcM1sZ3stDuZnZHeEzWGRmk+Or+ZExs+Fm9qSZvWZmS83ss6E8Y9sMYGaFZvZXM3s1tPvfQ/koM3sxtO9X4R6DmFlBmK8Jy6vjrP+RMrMcM3vZzP4Y5jO6vQBmtsbMFpvZK2a2IJSl7edbYXMUkp4IeiEwAfiYmU2It1bd5l5gRpuyLwGPu/s44PEwD1H7x4XXLODONNWxOzUBn3f3CcB04Mbwb5nJbQbYD5zn7icBk4AZZjYd+E/g2+4+FtgGXBvWvxbYFsq/HdbrjT4LLEuaz/T2tjrX3SclfacmfT/f7q7XEb6A04BHkuZvBm6Ou17d2L5qYEnS/OvAkDA9BHg9TP8I+Fh76/XWF/AQ0WPFs6nNxcBLwDSib5PnhvKDP+dEN7c9LUznhvUs7rp3sZ1V4RfrecAfAcvk9ia1ew1Q0aYsbT/fOrM5Op16ImgGGeTuG8P0JmBQmM6ozyF0lZwMvEgWtDl0Kb0C1AJzgVXAdndvCqskt+1gu8PyHcCA9Nb4qH0H+ALQEuYHkNntbeXAo2a20MxmhbK0/Xxn7F2fJbXc3c0s48bNm1kJ8Dvgc+6+08wOLsvUNrt7MzDJzPoBvwfGx1yllDGzi4Fad19oZufEXZ80O9PdN5jZQGCumS1PXpjqn2+d2RydbHsi6GYzGwIQ3mtDeUZ8DmaWRxQ097v7g6E4o9uczN23A08SdSP1M7PWP0aT23aw3WF5GVCf5qoejTOAvzWzNcAvibrSbidz23uQu28I77VEf1ScShp/vhU2Ryfbngg6G5gZpmcSXddoLb8qjGCZDuxIOjXvFSw6hbkbWObu30palLFtBjCzynBGg5kVEV2nWkYUOpeF1dq2u/XzuAx4wkOnfm/g7je7e5W7VxP9f33C3T9Bhra3lZn1MbPS1mngfGAJ6fz5jvuiVW9/ARcBK4j6ub8Sd326sV2/ADYCjUT9tdcS9VU/DqwEHgP6h3WNaFTeKmAxMDXu+h9Be88k6tNeBLwSXhdlcptDOyYCL4d2LwH+LZSPBv4K1AC/AQpCeWGYrwnLR8fdhqNo+znAH7OhvaF9r4bX0tbfVen8+dbtakREJOXUjSYiIimnsBERkZRT2IiISMopbEREJOUUNiIiknIKG5FuYma7w3u1mX28m/f95Tbz87pz/yKpprAR6X7VQJfCJunb64fyjrBx99O7WCeRWClsRLrfbcBZ4bkh/xRudPlNM5sfng3ydwBmdo6ZPWNms4HXQtkfwo0Sl7beLNHMbgOKwv7uD2WtZ1EW9r0kPKvko0n7fsrMfmtmy83s/nCXBMzsNoue27PIzP477Z+OZCXdiFOk+30J+Gd3vxgghMYOdz/FzAqA58zs0bDuZOAEd38jzH/K3beGW8fMN7PfufuXzOwz7j6pnWN9iOg5NCcBFWGbp8Oyk4HjgbeA54AzzGwZ8EFgvLt7661qRFJNZzYiqXc+0X2mXiF6bMEAoodSAfw1KWgA/tHMXgVeILoR4jg6dibwC3dvdvfNwF+AU5L2vd7dW4huv1NNdIv8fcDdZvYhoOGoWyfSCQobkdQz4B88ekLiJHcf5e6tZzZ7Dq4U3fL+b4ge1nUS0T3LCo/iuPuTppuJHg7WRHS3398CFwMPH8X+RTpNYSPS/XYBpUnzjwB/Hx5hgJkdE+6821YZ0SOIG8xsPNHjqVs1tm7fxjPAR8N1oUrgbKIbRrYrPK+nzN3nAP9E1P0mknK6ZiPS/RYBzaE77F6i56VUAy+Fi/R1wKXtbPcw8OlwXeV1oq60VncBi8zsJY9uid/q90TPn3mV6K7VX3D3TSGs2lMKPGRmhURnXDcdWRNFukZ3fRYRkZRTN5qIiKScwkZERFJOYSMiIimnsBERkZRT2IiISMopbEREJOUUNiIiknL/H/Zv89xURmjiAAAAAElFTkSuQmCC
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
<h3 id="Plot-the-Model-Predictions">Plot the Model Predictions<a class="anchor-link" href="#Plot-the-Model-Predictions">&#182;</a></h3><p>Since our model is trained now we may plot its predictions over the training and test datasets to see how well it fits the data.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Get model predictions for the trainint set.</span>
<span class="n">predictions_num</span> <span class="o">=</span> <span class="mi">100</span>
<span class="n">x_predictions</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="n">x_train</span><span class="o">.</span><span class="n">min</span><span class="p">(),</span> <span class="n">x_train</span><span class="o">.</span><span class="n">max</span><span class="p">(),</span> <span class="n">predictions_num</span><span class="p">)</span><span class="o">.</span><span class="n">reshape</span><span class="p">(</span><span class="n">predictions_num</span><span class="p">,</span> <span class="mi">1</span><span class="p">);</span>
<span class="n">y_predictions</span> <span class="o">=</span> <span class="n">linear_regression</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_predictions</span><span class="p">)</span>

<span class="c1"># Plot training data with predictions.</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Training Dataset&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">x_test</span><span class="p">,</span> <span class="n">y_test</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Test Dataset&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">x_predictions</span><span class="p">,</span> <span class="n">y_predictions</span><span class="p">,</span> <span class="s1">&#39;r&#39;</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;Prediction&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Economy..GDP.per.Capita.&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Happiness.Score&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Countries Happines&#39;</span><span class="p">)</span>
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
<p>Calculate the value of cost function for the training and test data set. The less this value is, the better.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">train_cost</span> <span class="o">=</span> <span class="n">linear_regression</span><span class="o">.</span><span class="n">get_cost</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">regularization_param</span><span class="p">)</span>
<span class="n">test_cost</span> <span class="o">=</span> <span class="n">linear_regression</span><span class="o">.</span><span class="n">get_cost</span><span class="p">(</span><span class="n">x_test</span><span class="p">,</span> <span class="n">y_test</span><span class="p">,</span> <span class="n">regularization_param</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Train cost: </span><span class="si">{:.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">train_cost</span><span class="p">))</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Test cost: </span><span class="si">{:.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">test_cost</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Train cost: 3476.54
Test cost: 247.28
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Let's now render the table of prediction values that our trained model does for unknown data (for test dataset). You should see that predicted happiness score should be quite similar to the known happiness score fron the test dataset.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">test_predictions</span> <span class="o">=</span> <span class="n">linear_regression</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_test</span><span class="p">)</span>

<span class="n">test_predictions_table</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">({</span>
    <span class="s1">&#39;Economy GDP per Capita&#39;</span><span class="p">:</span> <span class="n">x_test</span><span class="o">.</span><span class="n">flatten</span><span class="p">(),</span>
    <span class="s1">&#39;Test Happiness Score&#39;</span><span class="p">:</span> <span class="n">y_test</span><span class="o">.</span><span class="n">flatten</span><span class="p">(),</span>
    <span class="s1">&#39;Predicted Happiness Score&#39;</span><span class="p">:</span> <span class="n">test_predictions</span><span class="o">.</span><span class="n">flatten</span><span class="p">(),</span>
    <span class="s1">&#39;Prediction Diff&#39;</span><span class="p">:</span> <span class="p">(</span><span class="n">y_test</span> <span class="o">-</span> <span class="n">test_predictions</span><span class="p">)</span><span class="o">.</span><span class="n">flatten</span><span class="p">()</span>
<span class="p">})</span>

<span class="n">test_predictions_table</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[10]:</div>



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
      <th>Economy GDP per Capita</th>
      <th>Test Happiness Score</th>
      <th>Predicted Happiness Score</th>
      <th>Prediction Diff</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.482383</td>
      <td>7.522</td>
      <td>6.638892</td>
      <td>0.883108</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1.487097</td>
      <td>7.006</td>
      <td>6.650641</td>
      <td>0.355359</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1.441634</td>
      <td>6.714</td>
      <td>6.537337</td>
      <td>0.176663</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1.252785</td>
      <td>6.652</td>
      <td>6.066687</td>
      <td>0.585313</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.872002</td>
      <td>6.454</td>
      <td>5.117701</td>
      <td>1.336299</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1.233748</td>
      <td>6.452</td>
      <td>6.019245</td>
      <td>0.432755</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1.870766</td>
      <td>6.375</td>
      <td>7.606819</td>
      <td>-1.231819</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1.070622</td>
      <td>6.357</td>
      <td>5.612702</td>
      <td>0.744298</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1.000820</td>
      <td>6.008</td>
      <td>5.438742</td>
      <td>0.569258</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1.291788</td>
      <td>5.973</td>
      <td>6.163891</td>
      <td>-0.190891</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>
