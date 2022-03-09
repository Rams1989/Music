<html>
 <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
 <style type="text/css">
	 .navigation {
   list-style: none; /* Отключение отображения маркеров. */
   width: 220px;  /* Ширина меню. */
}
.navigation li {
   margin-top: 5px; /* Отступ между блоками по высоте, необходимый для того чтобы пункты меню не сливались */
   font-family: Verdana, Arial, Helvetica, sans-serif; /* Тип шрифта пунктов меню */
   font-size: 14px; /* Размер текста меню */
}
.navigation li a {
   display: block; /* Изменение отображения на блочное для того, чтобы иметь возможность задать внутренние отступы.  */
   padding: 4px 15px;  /* Отступы внутри блоков. */
   background: #8c8c8c; /* Цвет блоков меню. */
   color: #e5e5e5; /* Цвет текста в блоках меню. */
   text-decoration: none; /* Устранение подчёркивания ссылок. */
   position: relative; /* Это необходимо при использовании Internet Explorer 6 для того, чтобы ссылка по всей своей площади была «кликабельной». */
}
.navigation li a:hover {
   background: #dfdfdf; /* Цвет фона при наведении курсора мыши */
   color: #000000;  /* Цвет текста при наведении курсора мыши */
}
</style>
</head>
<body>
<style>
   body {
    background: #000000 url(https://github.com/Rams1989/music_base/blob/main/devushka_shliapa_chb_132197_1920x1080.jpg?raw=true); /* Цвет фона и путь к файлу */
    background-repeat: no-repeat;
    background-position: center center;
    background-attachment: fixed;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
 }
  </style>	
  <!-- Описание ссылок в меню и сами ссылки. -->
<ul class="navigation"> 
   <li><a href="music.html" target="_blank">Музыка</a></li>
   <li><a href="https://www.internet-technologies.ru/articles" target="_blank">Видео</a></li>
   <li><a href="https://www.internet-technologies.ru/templates/" target="_blank">Обои</a></li>
   <li><a href="https://www.internet-technologies.ru/books" target="_blank">Стихи</a></li>
   <li><a href="https://www.internet-technologies.ru/scripts" target="_blank">Анекдоты</a></li>
   <li><a href="http://talk.internet-technologies.ru/" target="_blank">О сайте</a></li>
</ul>
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" />

<style>
main.container-fluid {margin:0;padding:0;}
.nightmode {
 background-color:#121212;
 background-image: linear-gradient(to right, #274046, #E6DADA);
 color:#fff;
 text-shadow:1px 1px 1px black;
}
.daymode {
 background-color: #87ceeb;
 background-image: linear-gradient(to bottom left, #87ceeb 0%,#fff 100%);
 color:#333;
 text-shadow:1px 1px 10px white;
}
.clocktext {
 display:block;
 margin:0;
 padding:1px 0 0 0;
 width:100%;
 text-align:center;
 line-height:1.2;
 white-space:nowrap;
}
#date {
 font-size:1.3rem;
 padding-top:15px;
}
#time {
 font-size:5rem;
 margin:1px 0 0 0;
}
#time span {
 display:inline-block;
 padding:0;
 vertical-align: baseline;
 text-align:left;
 width: 2em;
 margin:0 0 0 0.5em;
 font-size:1.5rem;
 line-height:1.5;
 white-space:normal;
}
@media (min-width: 576px) {
#date {font-size:2rem;}
#time {font-size:8rem;}
#time span {font-size:2rem;line-height: 2;}
}
@media (min-width: 768px) {
#date {font-size:3rem;}
#time {font-size:11rem;}
#time span {font-size:3rem;line-height: 2;}
}
@media (min-width: 992px) {
#date {font-size:4rem;}
#time {font-size:13rem;}
#time span {font-size:4rem;line-height: 2;}
}
@media (min-width: 1200px) {
#date {font-size:4.5rem;}
#time {font-size:18rem;}
#time span {font-size:4.5rem;line-height: 2;}
}
</style>

<main class="container-fluid nightmode text-center">
 <time id="date" class="clocktext"> </time>
 <time id="time" class="clocktext"> <span> </span> </time>
</main>

<script>
var now, dd, td;
var months = ["Январь","Февраль","Март","Апрель","Май","Июнь","Июль","Август","Сентябрь","Октябрь","Ноябрь","Декабрь"];
var days = ["Воскресенье","Понедельник","Вторник","Среда","Четверг","Пятница","Суббота"];

document.addEventListener("DOMContentLoaded", init, false);
function init(){
 dd = document.getElementById("date");
 td = document.getElementById("time");
 updateTime();
 setInterval(updateTime,1000);
}
function updateTime(){
 var clockdata = getClockStrings();
 dd.innerHTML = clockdata.datehtml;
 td.innerHTML = clockdata.timehtml;
 dd.dateTime = now.toISOString();
 td.dateTime = now.toISOString();
}
function getClockStrings(){
 now = new Date();
 var year = now.getFullYear();
 var month = months[now.getMonth()];
 var date = now.getDate();
 var day = days[now.getDay()];
 var hour = now.getHours();
 var minutes = now.getMinutes();
 var seconds = now.getSeconds();
 var meridian = hour < 24 ? "AM" : "PM"; //
 var clockhour = hour > 24 ? hour - 24 : hour;
 if (hour === 0) {clockhour = 24;}
 var clockminutes = minutes < 10 ? "0" + minutes : minutes;
 var clockseconds = seconds < 10 ? "0" + seconds : seconds;
 var datehtml = day + ", " + month + " " + date + ", " + year;
 var timehtml = clockhour + ":" + clockminutes + "<span>:" + clockseconds + " " + meridian + "</span>";
 return {"datehtml":datehtml,"timehtml":timehtml};
}
</script>
	</body>  
	  

 
 
