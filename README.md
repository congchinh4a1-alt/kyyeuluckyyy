```html
<!DOCTYPE html>
<html lang="vi">
<head>

<meta charset="UTF-8">
<title>Thiệp Mời Kỷ Yếu</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500&family=Playfair+Display:wght@600&display=swap" rel="stylesheet">

<style>

body{
margin:0;
font-family:'Poppins',sans-serif;
background:linear-gradient(#0b1d3a,#020617);
height:100vh;
overflow:hidden;
display:flex;
justify-content:center;
align-items:center;
color:white;
}

/* stars */

.star{
position:absolute;
width:3px;
height:3px;
background:#ffd54f;
border-radius:50%;
animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
from{opacity:0.2}
to{opacity:1}
}

/* shooting star */

.shooting{
position:absolute;
width:150px;
height:2px;
background:linear-gradient(90deg,#fff,transparent);
animation:shoot 6s linear infinite;
}

@keyframes shoot{

0%{
transform:translate(-300px,-200px) rotate(25deg);
opacity:0
}

15%{opacity:1}

100%{
transform:translate(900px,500px) rotate(25deg);
opacity:0
}

}

/* spotlight */

.spotlight{
position:absolute;
top:-200px;
left:50%;
transform:translateX(-50%);
width:700px;
height:700px;
background:radial-gradient(circle,rgba(255,255,255,0.25),transparent 70%);
}

/* curtain */

.curtain{
position:absolute;
top:0;
width:50%;
height:100%;
background:#3a0000;
transition:2s;
z-index:5;
}

.left{left:0;}
.right{right:0;}

.open .left{transform:translateX(-100%)}
.open .right{transform:translateX(100%)}

/* book */

.book{
width:440px;
height:540px;
background:#0f2347;
border-radius:14px;
padding:40px;
box-shadow:0 0 50px rgba(0,0,0,0.6);
text-align:center;
}

/* pages */

.page{
display:none;
animation:fade .8s;
}

.page.active{
display:block;
}

@keyframes fade{
from{opacity:0; transform:translateY(20px)}
to{opacity:1; transform:translateY(0)}
}

h1{
font-family:'Playfair Display',serif;
color:#ffd54f;
letter-spacing:2px;
}

button{
margin-top:25px;
padding:10px 26px;
border:none;
background:#ffd54f;
color:#081b3a;
border-radius:30px;
font-weight:500;
cursor:pointer;
transition:.3s;
}

button:hover{
transform:scale(1.05);
}

.slogan{
margin-top:10px;
opacity:.8;
font-size:14px;
}

</style>
</head>

<body>

<audio autoplay loop>
<source src="https://cdn.pixabay.com/audio/2022/03/15/audio_6c1cb4f5d0.mp3" type="audio/mpeg">
</audio>

<div class="spotlight"></div>

<div class="shooting"></div>

<div class="curtain left"></div>
<div class="curtain right"></div>

<div class="book">

<div class="page active">

<h1>12 TIN</h1>

<div class="slogan">
Thanh xuân – Những vì sao không bao giờ tắt
</div>

<p>
Chúng tôi trân trọng mời bạn đến tham dự
buổi chụp kỷ yếu của lớp.
</p>

<button onclick="next()">Mở Thiệp</button>

</div>

<div class="page">

<h1>Nội Dung</h1>

<p>

📸 Chụp ảnh tập thể lớp  
📸 Chụp concept kỷ yếu  
📸 Lưu giữ những khoảnh khắc đẹp nhất

</p>

<button onclick="back()">←</button>
<button onclick="next()">→</button>

</div>

<div class="page">

<h1>Thời Gian</h1>

<p>
📅 Ngày: ............
</p>

<p>
⏰ Thời gian: ............
</p>

<button onclick="back()">←</button>
<button onclick="next()">→</button>

</div>

<div class="page">

<h1>Địa Chỉ</h1>

<p>
📍 Địa điểm:
</p>

<p>
............................
</p>

<button onclick="back()">←</button>
<button onclick="next()">→</button>

</div>

<div class="page">

<h1>Cảm Ơn</h1>

<p>
Cảm ơn bạn đã dành thời gian đọc tấm thiệp này.
</p>

<p>
Chúng tôi rất mong bạn có thể đến
và cùng tạo nên những kỷ niệm đẹp
trong buổi chụp kỷ yếu của lớp.
</p>

<p>
Hẹn gặp bạn!
</p>

<button onclick="back()">←</button>

</div>

</div>

<script>

/* stars */

for(let i=0;i<130;i++){

let s=document.createElement("div")

s.className="star"

s.style.top=Math.random()*100+"%"
s.style.left=Math.random()*100+"%"

s.style.animationDuration=1+Math.random()*3+"s"

document.body.appendChild(s)

}

/* curtain open */

setTimeout(()=>{

document.body.classList.add("open")

},800)

/* pages */

let pages=document.querySelectorAll(".page")
let index=0

function showPage(i){

pages.forEach(p=>p.classList.remove("active"))

pages[i].classList.add("active")

}

function next(){

if(index<pages.length-1){

index++
showPage(index)

}

}

function back(){

if(index>0){

index--
showPage(index)

}

}

</script>

</body>
</html>
```
