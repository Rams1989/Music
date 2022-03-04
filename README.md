<html>
 <head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
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
<ul class="metro">
    <li><a href="">Элемент списка</a>
      <ul>
        <li><a href="">Элемент вложенного списка</a></li>
        <li><a href="">Элемент вложенного списка</a></li>
        <li><a href="">Элемент вложенного списка</a></li>
      </ul>
    </li>
    <li><a href="">Элемент списка</a></li>
    <li><a href="">Элемент списка</a></li>
</ul>
.metro {
  list-style: none;
  padding: 0;
  margin: 30px 0 0 50px;
  border-left: 5px solid #DAE4F1;
}
.metro li {line-height: 2em;}
.metro ul {
  margin: 20px 0 20px 15px;
  padding: 0;
  border: none;
  list-style: none;
}
.metro ul:before, .metro ul:after {
  content: "";
  width: 5px;
  height: 28px;
  background: #DAE4F1;
  position: relative;
  display: block;
  left: -9px;
}
.metro ul:before {
  transform: rotate(-45deg);
  margin-top: -15px;
}
.metro ul:after {
  transform: rotate(45deg);
  bottom: -20px;
}
.metro ul li {border-left: 5px solid #DAE4F1;}
.metro ul li:first-child {
  margin-top: -5px;
  padding-top: 5px;
}
.metro ul li:last-child {
  padding-bottom: 9px;
  margin-bottom: -25px;
}
.metro a {
  text-decoration: none;
  display: block;
  font-family: 'Noto Sans', sans-serif;
  color: #4A4B4D;
}
.metro a:before {
  content: "";
  display: inline-block;
  background: #CA682D;
  width: 12px;
  height: 12px;
  left: -9px;
  position: relative;
  border-radius: 50%;
  margin-right: .5em;
}
</body>  
	  

 
 
