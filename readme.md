*,
*:before,
*:after {
  box-sizing: border-box;
}
.hide {
  display: none !important;
}
button {
  margin: 0;
  padding: 0;
  border: 0;
  outline: 0;
  background: transparent;
}

.material-icons.md-dark { color: rgba(0, 0, 0, 0.75); }
/*------------------------
    Audio Player - AP
------------------------*/
/* Player and control panel */
.ap {
  position: absolute;
  right: 0;
  bottom: 0;
  left: 0;
  height: 50px;
  margin: auto;
  font-family: Arial, sans-serif;
  font-size: 14px;
  -webkit-user-select: none;
     -moz-user-select: none;
      -ms-user-select: none;
          user-select: none;
  color: #333;
  background: #f1f1f1;
  border-top: 1px solid #ccc;
  z-index: 9999;
}
.ap-inner {
  max-width: 1440px;
  margin: 0 auto;
}
.ap-panel {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
}
.ap-item {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-flex: 1;
  -webkit-flex: 1;
      -ms-flex: 1;
          flex: 1;
  -webkit-box-pack: center;
  -webkit-justify-content: center;
      -ms-flex-pack: center;
          justify-content: center;
  -webkit-box-align: center;
  -webkit-align-items: center;
      -ms-flex-align: center;
          align-items: center;
}
.ap--track {
  -webkit-box-flex: 1;
  -webkit-flex: 1 40%;
      -ms-flex: 1 40%;
          flex: 1 40%;
  padding: 0 20px;
}

/* Info section */
.ap-info {
  width: 100%;
  position: relative;
  -webkit-align-self: flex-start;
      -ms-flex-item-align: start;
          align-self: flex-start;
  padding: 5px 0 0;
}
.ap-title {
  position: relative;
  overflow: hidden;
  padding-right: 80px;
  text-align: left;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.ap-time {
  position: absolute;
  top: 5px;
  right: 0;
}
.ap-progress-container {
  padding: 5px 0 10px;
  cursor: pointer;
}
.ap-progress {
  position: relative;
  height: 3px;
  border-radius: 5px;
  background: rgba(0,0,0,.2);
}
.ap-preload-bar,
.ap-bar {
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 0;
  border-radius: 5px 0 0 5px;
  background: rgba(0,0,0,.3);
  z-index: 999;
}
.ap-bar {
  background: #f50;
  z-index: 9999;
}
.ap-bar:after {
  position: absolute;
  top: 0;
  right: -5px;
  width: 12px;
  height: 12px;
  margin-top: -4px;
  content: '';
  border-radius: 6px;
  background: #f50;
  opacity: 0;
  -webkit-transition: opacity .3s ease;
  transition: opacity .3s ease;
}
.ap-progress-container:hover .ap-bar:after {
  opacity: 1;
}

/* Buttons */
.ap-controls {
  position: relative;
  z-index: 1000;
  display: block;
  height: 50px;
  cursor: pointer;
  -webkit-transition: background .2s ease;
  transition: background .2s ease;
  text-align: center;
  color: #fff;
  border: 0;
  outline: 0;
  background: none;
}
.ap-controls svg {
  fill: #333;
}
.ap-controls:hover svg {
  fill: #222;
}
.ap-controls:active {
  background: rgba(0,0,0,.1);
}
.ap--playback > .ap-controls,
.ap--settings > .ap-controls {
  -webkit-box-flex: 0;
  -webkit-flex: 0 25%;
      -ms-flex: 0 25%;
          flex: 0 25%;
}
.ap--pause,
.playing > .ap--play {
  display: none;
}
.playing > .ap--pause {
  display: inline;
}
.ap-volume-container {
  z-index: 9999;
}
.ap-volume {
  position: absolute;
  right: 0;
  bottom: 50px;
  overflow: hidden;
  width: 100%;
  height: 0;
  visibility: hidden;
  -webkit-transition: height .2s cubic-bezier(0.17, 0.72, 0.26, 1.23);
  transition: height .2s cubic-bezier(0.17, 0.72, 0.26, 1.23);
  background: #ddd;
  border: 1px solid #ccc;
  border-bottom: 0;
  z-index: 9999;
}
.ap-volume-btn {
  display: block;
  text-align: center;
  width: 100%;
}
.ap-volume-btn > .ap--volume-off,
.muted > .ap--volume-on {
  display: none;
}
.muted > .ap--volume-off {
  display: inline;
}
.ap-volume-container:hover {
  background: #ddd;
}
.ap-volume-container:hover .ap-volume {
  height: 120px;
  visibility: visible;
}
.ap-volume-progress {
  display: block;
  width: 4px;
  height: 100px;
  margin: 10px auto;
  background: rgba(0,0,0,.2);
  position: relative;
  border-radius: 3px;
}
.ap-volume-bar {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  background: #f50;
  height: 50%;
  border-radius: 3px;
}

.ap-active {
  background: rgba(0,0,0,.15);
  opacity: 1;
}

@-webkit-keyframes blink {
  from { opacity: 0; }
  50% { opacity: 1; }
  to { opacity: 0; }
}

@keyframes blink {
  from { opacity: 0; }
  50% { opacity: 1; }
  to { opacity: 0; }
}
.playing > .ap--pause {
  -webkit-animation: blink 1.5s linear infinite;
          animation: blink 1.5s linear infinite;
}
/* --------------------------- */

@media(max-width:880px) {
  .ap-item > .ap-controls {
    -webkit-box-flex: 1;
    -webkit-flex: 1;
        -ms-flex: 1;
            flex: 1;
  }
}
@media(max-width:550px) {
  .ap {
    min-width: 250px;
  }
  .ap, .ap-panel {
    height: auto;
  }
  .ap-panel {
    -webkit-flex-wrap: wrap;
        -ms-flex-wrap: wrap;
            flex-wrap: wrap;
  }
  .ap--track {
    margin-bottom: 10px;
    padding: 0 20px;
    -webkit-box-ordinal-group: 2;
    -webkit-order: 1;
        -ms-flex-order: 1;
            order: 1;
    -webkit-box-flex: 1;
    -webkit-flex: 1 1 100%;
        -ms-flex: 1 1 100%;
            flex: 1 1 100%;
  }
  .ap--playback,
  .ap--settings {
    -webkit-box-flex: 1;
    -webkit-flex: 1 1 50%;
        -ms-flex: 1 1 50%;
            flex: 1 1 50%;
    -webkit-box-ordinal-group: 3;
    -webkit-order: 2;
        -ms-flex-order: 2;
            order: 2;
  }
}
/*--------------------
  PlayList
--------------------*/
.pl-container {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 50px;
  left: 0;
  margin: auto;
  overflow: auto;
  font-family: Arial, sans-serif;
  font-size: 14px;
  background: #f1f1f1;
  z-index: 999;
}
.pl-lead {
  font-size: 24px;
  font-weight: 400;
  text-align: center;
  color: #333;
}
.pl-list {
  width: 100%;
  max-width: 550px;
  margin: 0 auto;
  padding: 30px 10px;
}
.pl-list > li {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -webkit-align-items: center;
      -ms-flex-align: center;
          align-items: center;
  border-bottom: 1px solid #ddd;
}
.pl-number,
.pl-title,
.pl-remove {
  margin: 0 5px;
  padding: 10px 0;
}
.pl-number {
  -webkit-box-flex: 0;
  -webkit-flex: 0 10%;
      -ms-flex: 0 10%;
          flex: 0 10%;
  text-align: center;
}
.pl-playing {
  display: none;
}
.pl-current .pl-count {
  display: none;
}
.pl-current .pl-playing {
  display: block;
}
.pl-current .pl-title {
  font-weight: 700;
}

.pl-title {
  overflow: hidden;
  cursor: pointer;
  text-align: left;
  white-space: nowrap;
  text-overflow: ellipsis;
  -webkit-box-flex: 1;
  -webkit-flex: 1;
      -ms-flex: 1;
          flex: 1;
}
.pl-title:hover {
  text-decoration: underline;
}
.pl-remove {
  opacity: 0;
  margin-right: 0;
  cursor: pointer;
  text-align: center;
  -webkit-box-flex: 0;
  -webkit-flex: 0 50px;
      -ms-flex: 0 50px;
          flex: 0 50px;
}
.pl-remove:hover {
  background: #ddd;
}
.pl-list > li:hover .pl-remove {
  opacity: 1;
}

.pl-list svg {
  fill: rgba(0,0,0, .7);
}

.pl-empty {
  position: absolute;
  top: 50%;
  left: 50%;
  font-size: 2rem;
  -webkit-transform: translate(-50%, -50%);
          transform: translate(-50%, -50%);
  letter-spacing: 2px;
  color: #ccc;
}

@-webkit-keyframes eq {
  0% { height: 3px; }
  50% { height: 20px; }
  100% { height: 3px; }
}

@keyframes eq {
  0% { height: 3px; }
  50% { height: 20px; }
  100% { height: 3px; }
}
.eq {
  display: -webkit-box;
  display: -webkit-flex;
  display: -ms-flexbox;
  display: flex;
  width: 20px;
  height: 20px;
  margin: 0 auto;
  -webkit-box-pack: justify;
  -webkit-justify-content: space-between;
      -ms-flex-pack: justify;
          justify-content: space-between;
  -webkit-box-align: end;
  -webkit-align-items: flex-end;
      -ms-flex-align: end;
          align-items: flex-end;
}
.eq-bar {
  width: 4px;
  background: rgba(0,0,0,.7);
}
.eq-bar:nth-child(1) {
  -webkit-animation: eq .8s ease-in-out infinite 0s;
          animation: eq .8s ease-in-out infinite 0s;
}
.eq-bar:nth-child(2) {
  -webkit-animation: eq .8s ease-in-out infinite .2s;
          animation: eq .8s ease-in-out infinite .2s;
}
.eq-bar:nth-child(3) {
  -webkit-animation: eq .8s ease-in-out infinite .4s;
          animation: eq .8s ease-in-out infinite .4s;
}

.ap-image {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 50px;
  left: 0;
  overflow: auto;
  display: flex;
  justify-content: center;
}
.ap-image img {
  max-width: 100%;
  max-height: 100%;
  display: block;
}