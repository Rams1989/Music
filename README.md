<html>
 <head>
  <meta charset="utf-8">
 <style>
body {
    background: #c7b39b url(https://github.com/Rams1989/music_base/blob/main/portal_svechenie_iarkij_148108_1920x1080.jpg?raw=true); /* Цвет фона и путь к файлу */
   color: #fff; /* Цвет текста */
	 background-size: cover; 
-moz-background-size: cover; 
-o-background-size: cover; 
-webkit-background-size: cover;		
   }
 </style>
<!-- подключаем стили и скрипты -->
   <link href="css/styles.css" rel="stylesheet" type="text/css" />
   <script type="text/javascript" src="js/jquery-1.7.2.min.js"></script>
   <script type="text/javascript" src="js/jquery-ui-1.8.21.custom.min.js"></script>
   <script type="text/javascript" src="js/main.js"></script>
</head>
   <body>
	<div class="player">
    <div class="pl"></div>
    <div class="title"></div>
    <div class="artist"></div>
    <div class="cover"></div>
    <div class="controls">
        <div class="play"></div>
        <div class="pause"></div>
        <div class="rew"></div>
        <div class="fwd"></div>
    </div>
    <div class="volume"></div>
    <div class="tracker"></div>
</div>
<ul class="playlist hidden">
    <li audiourl="01.mp3" cover="cover1.jpg" artist="Artist 1">01.mp3</li>
    <li audiourl="02.mp3" cover="cover2.jpg" artist="Artist 2">02.mp3</li>
    <li audiourl="03.mp3" cover="cover3.jpg" artist="Artist 3">03.mp3</li>
    <li audiourl="04.mp3" cover="cover4.jpg" artist="Artist 4">04.mp3</li>
    <li audiourl="05.mp3" cover="cover5.jpg" artist="Artist 5">05.mp3</li>
    <li audiourl="06.mp3" cover="cover6.jpg" artist="Artist 6">06.mp3</li>
    <li audiourl="07.mp3" cover="cover7.jpg" artist="Artist 7">07.mp3</li>
</ul>
.example {
    margin: 50px auto 0;
    width: 400px;
}
.player {
    background: transparent url("../images/spr.png") no-repeat scroll center top;
    height: 162px;
    position: relative;
    width: 326px;
    z-index: 2;
}
.title, .artist {
    font-family: verdana;
    left: 167px;
    position: absolute;

    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select: none;
}
.title {
    color: #FFFFFF;
    font-size: 14px;
    font-weight: bold;
    top: 23px;
}
.artist {
    color: #EEEEEE;
    font-size: 12px;
    top: 40px;
}
.pl {
    background: transparent url("../images/spr.png") no-repeat scroll -274px -175px;
    cursor: pointer;
    height: 34px;
    left: 270px;
    position: absolute;
    top: 20px;
    width: 32px;
}
.pl:hover {
    top: 21px;
}
.cover {
    background: transparent url(../data/cover1.jpg) no-repeat scroll center top;
    border-radius: 5px 5px 5px 5px;
    height: 94px;
    left: 20px;
    position: absolute;
    top: 20px;
    width: 94px;
}
.controls {
    cursor: pointer;
    height: 23px;
    left: 167px;
    position: absolute;
    top: 65px;
    width: 138px;
}
.controls .play, .controls .pause, .controls .rew, .controls .fwd {
    background: transparent url("../images/spr.png") no-repeat scroll 0 0;
    float: left;
    height: 100%;
    width: 33%;
}
.controls .play {
    background-position: -8px -171px;
}
.controls .pause {
    background-position: -8px -198px;
    display: none;
}
.controls .rew {
    background-position: -54px -171px;
}
.controls .fwd {
    background-position: -100px -171px;
}
.controls .play:hover {
    background-position: -8px -170px;
}
.controls .pause:hover {
    background-position: -8px -197px;
}
.controls .rew:hover {
    background-position: -54px -170px;
}
.controls .fwd:hover {
    background-position: -100px -170px;
}
.hidden {
    display: none;
}
.controls .visible {
    display: block;
}
.volume {
    height: 11px;
    left: 186px;
    position: absolute;
    top: 96px;
    width: 112px;
}
.tracker {
    height: 15px;
    left: 20px;
    position: absolute;
    top: 126px;
    width: 285px;
}
.ui-slider-range {
    background: transparent url("../images/spr.png") no-repeat scroll 5px -222px;
    height: 100%;
    position: absolute;
    top: 0;
}
.ui-slider-handle {
    cursor: pointer;
    height: 10px;
    margin-left: -5px;
    position: absolute;
    top: 2px;
    width: 10px;
    z-index: 2;
}
.volume .ui-slider-handle {
    background: url("../images/spr.png") no-repeat scroll -201px -188px rgba(0, 0, 0, 0);
    height: 13px;
    width: 13px;
}
.playlist {
    background-color: #333333;
    border-radius: 5px 5px 5px 5px;
    list-style-type: none;
    margin: -10px 0 0 2px;
    padding-bottom: 10px;
    padding-top: 15px;
    position: relative;
    width: 326px;
    z-index: 1;
}
.playlist li {
    color: #EEEEEE;
    cursor: pointer;
    margin: 0 0 5px 15px;
}
.playlist li.active {
    font-weight: bold;
}
// inner variables
var song;
var tracker = $('.tracker');
var volume = $('.volume');

// initialization - first element in playlist
initAudio($('.playlist li:first-child'));

// set volume
song.volume = 0.8;

// initialize the volume slider
volume.slider({
    range: 'min',
    min: 1,
    max: 100,
    value: 80,
    start: function(event,ui) {},
    slide: function(event, ui) {
        song.volume = ui.value / 100;
    },
    stop: function(event,ui) {},
});

// empty tracker slider
tracker.slider({
    range: 'min',
    min: 0, max: 10,
    start: function(event,ui) {},
    slide: function(event, ui) {
        song.currentTime = ui.value;
    },
    stop: function(event,ui) {}
});
	function initAudio(elem) {
    var url = elem.attr('audiourl');
    var title = elem.text();
    var cover = elem.attr('cover');
    var artist = elem.attr('artist');

    $('.player .title').text(title);
    $('.player .artist').text(artist);
    $('.player .cover').css('background-image','url(data/' + cover+')');;

    song = new Audio('data/' + url);

    // timeupdate event listener
    song.addEventListener('timeupdate',function (){
        var curtime = parseInt(song.currentTime, 10);
        tracker.slider('value', curtime);
    });

    $('.playlist li').removeClass('active');
    elem.addClass('active');
}
function playAudio() {
    song.play();

    tracker.slider("option", "max", song.duration);

    $('.play').addClass('hidden');
    $('.pause').addClass('visible');
}
function stopAudio() {
    song.pause();

    $('.play').removeClass('hidden');
    $('.pause').removeClass('visible');
}
	// play click
$('.play').click(function (e) {
    e.preventDefault();

    playAudio();
});

// pause click
$('.pause').click(function (e) {
    e.preventDefault();

    stopAudio();
});
	// forward click
$('.fwd').click(function (e) {
    e.preventDefault();

    stopAudio();

    var next = $('.playlist li.active').next();
    if (next.length == 0) {
        next = $('.playlist li:first-child');
    }
    initAudio(next);
});

// rewind click
$('.rew').click(function (e) {
    e.preventDefault();

    stopAudio();

    var prev = $('.playlist li.active').prev();
    if (prev.length == 0) {
        prev = $('.playlist li:last-child');
    }
    initAudio(prev);
});
	// show playlist
$('.pl').click(function (e) {
    e.preventDefault();

    $('.playlist').fadeIn(300);
});

// playlist elements - click
$('.playlist li').click(function () {
    stopAudio();
    initAudio($(this));
});
	
  
	  

 
 
