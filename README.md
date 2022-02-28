<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
 </head>
  <style>
body {
    background: #c7b39b url(https://github.com/Rams1989/music_base/blob/main/annotaciya-muzykalnogo-rabochego-stola.jpg?raw=true); /* Цвет фона и путь к файлу */
   background-size: cover; 
-moz-background-size: cover; 
-o-background-size: cover; 
-webkit-background-size: cover;		
   }
   </style>
#CDimage{
	width:260px;			
}
// Эффект 3d
#CDimage img{
	border-radius:50%;
}
#CDimage #voice{
	text-align:center;
	}
#CDimage #music{
	text-align:center;
	}
	<div id="CDimage">
 <h3> Простой музыкальный проигрыватель </h3>
<hr>
<br>
<img src="img/image.jpg" width="250" height="250">
<div id="voice">
<input id="volume" type="range"  min="0" max="1" step="0.1" onchange="setVolume()" />
</div>
<div id="music">
 Сейчас играет: <span id = "title"> Море облаков под луной </span>
 <button id = "lastMusic" onClick = "lastMusic ()"> <img src = "img / previous song.PNG" width = "50" height = "50" /> </button>
 <button id = "toggleBtn" onclick = "toggleMusic ()"> <img src = "img / play.PNG" width = "50" height = "50" /> </button>
 <button id = "nextMusic" onClick = "nextMusic ()"> <img src = "img / Next song.PNG" width = "50" height = "50" /> </button>

 <audio id = "audio" src = "music / Море облаков под лунным светом.mp3" preload>
</audio>
</div>
</div>
	var music = document.getElementById("audio");
function toggleMusic() {
     if (music.paused) {
                     music.play (); // Воспроизведение музыки
     } else {
                     music.pause (); // Приостановить музыку
     }
}
 // Устанавливаем громкость
function setVolume() {
    music.volume = volume.value;
}
 // Плейлист, вы можете обновить названия песен в своей музыкальной папке, поместив их сюда

var music1 = new Array();
	 music1 = [«Море облаков под лунным светом», «Waili P-Kyrie», «Xeuphoria-Coda»]; // Плейлист
	var num = 0;
	
	
	var name = document.getElementById("title");


 // Предыдущий
function lastMusic() {
			num = (num +2)%3;
		 	music.src ="music/"+music1[num]+".mp3";
			title.innerHTML = music1[num];
			music.play();
		
	}
 //Следующая песня

function nextMusic(){
			num = (num +1)%3;
		 	audio.src =  "music/"+music1[num]+".mp3";
			title.innerHTML = music1[num];
			music.play();
	}
	</body>
</html>
