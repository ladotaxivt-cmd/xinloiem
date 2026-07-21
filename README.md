<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Xin Em Tha Thứ</title>

<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;500&display=swap" rel="stylesheet">

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
}

body{
background:#000;
overflow:hidden;
display:flex;
justify-content:center;
align-items:center;
height:100vh;
font-family:'Poppins',sans-serif;
}

/* nền sao */
body::before{
content:"";
position:fixed;
width:100%;
height:100%;
background:
radial-gradient(circle,#ffffff22 1px,transparent 1px);
background-size:35px 35px;
opacity:.2;
animation:move 30s linear infinite;
}

@keyframes move{
from{transform:translateY(0);}
to{transform:translateY(35px);}
}

/* Book */

.book{
position:relative;
width:700px;
height:450px;
perspective:2500px;
}

.page{
position:absolute;
width:100%;
height:100%;
background:#050505;
border:1px solid #600;
box-shadow:0 0 30px rgba(255,0,0,.25);
padding:40px;
transform-origin:left;
transition:1.6s;
backface-visibility:hidden;
display:flex;
justify-content:center;
align-items:center;
overflow:hidden;
}

.page h1{
color:#ff3030;
font-family:"Dancing Script",cursive;
font-size:50px;
text-shadow:0 0 15px red;
margin-bottom:25px;
text-align:center;
}

.page p{
color:#ff4d4d;
font-size:23px;
line-height:1.8;
text-align:center;
}

.page:nth-child(1){
z-index:4;
}

.page:nth-child(2){
z-index:3;
}

.page:nth-child(3){
z-index:2;
}

.page:nth-child(4){
z-index:1;
}

.flip{
transform:rotateY(-180deg);
}

/* Chữ rơi */

.falling{
position:absolute;
top:-60px;
font-size:28px;
color:#ff2e2e;
font-family:"Dancing Script";
animation:fall linear forwards;
pointer-events:none;
text-shadow:0 0 10px red;
}

@keyframes fall{

0%{
transform:translateY(-50px);
opacity:0;
}

20%{
opacity:1;
}

100%{
transform:translateY(110vh);
opacity:0;
}

}

/* nút */

button{

position:fixed;
bottom:40px;
padding:15px 40px;
background:#8b0000;
border:none;
color:white;
font-size:18px;
border-radius:40px;
cursor:pointer;
transition:.4s;
box-shadow:0 0 20px red;
}

button:hover{

background:red;
transform:scale(1.08);

}

@media(max-width:800px){

.book{
width:95%;
height:500px;
}

.page h1{
font-size:38px;
}

.page p{
font-size:18px;
}

}
</style>
</head>

<body>

<div class="book">

<div class="page">
<div>
<h1>Gửi Em ❤️</h1>
<p>
Bi  đã suy nghĩ rất nhiều về những điều đã xảy ra.
Có lẽ Bi  đã khiến em buồn, thất vọng và tổn thương.
Điều đó làm Bi  thật sự hối hận.
</p>
</div>
</div>

<div class="page">
<div>
<h1>Bi Xin Lỗi...</h1>
<p>
Bi không muốn biện minh cho lỗi lầm của mình.
Bi  chỉ muốn thừa nhận rằng Bi đã sai
và mong có cơ hội để sửa đổi.
</p>
</div>
</div>

<div class="page">
<div>
<h1>Điều Bi  Mong Muốn</h1>
<p>
Bi không dám yêu cầu em phải tha thứ ngay.
Chỉ mong em cho Bi  thêm một cơ hội
để chứng minh bằng hành động,
rằng Bi  có thể trở thành phiên bản tốt hơn mỗi ngày.
</p>
</div>
</div>

<div class="page">
<div>
<h1>Cảm Ơn Em ❤️</h1>
<p>
Dù kết quả thế nào,
Bi vẫn biết ơn vì những kỷ niệm chúng ta đã có.

Nếu em còn một chút niềm tin,
Bi sẽ mong em sẽ suy nghĩ lại.

Bi  vẫn luôn ở đây chờ em ...
</p>
</div>
</div>
<div class="page">
<div>
<h1>Đã bật chế độ hối lỗi 100%, mong được khoan hồng❤️</h1>
<p>
"Thôi mà, đừng giận Bi nữa nha. Bi biết mình chưa đúng và sẽ cố gắng sửa và sẽ tích cực hơn . Bi chỉ mong được thấy em cười với Bi như trước thôi. Cho Bi ôm một cái để làm lành nhé? ❤️🥺"
" HAPPY ANIVERSARY 1Y2M"
</p>
</div>
</div>
</div>

<button onclick="nextPage()">Lật Trang 📖</button>

<script>

const pages=document.querySelectorAll(".page");
let index=0;

function nextPage(){

if(index<pages.length){

pages[index].classList.add("flip");
index++;

}else{

pages.forEach(p=>p.classList.remove("flip"));
index=0;

}

}

/* Chữ rơi */

const texts=[
"Xin lỗi ❤️",
"Bi nhớ em",
"Tha thứ cho Bi ",
"Yêu em",
"Bi  sẽ thay đổi",
"Cảm ơn em",
"❤️",
"Bi sẽ chờ em"
];

function createText(){

let span=document.createElement("span");
span.className="falling";

span.innerHTML=texts[Math.floor(Math.random()*texts.length)];

span.style.left=Math.random()*100+"vw";

span.style.animationDuration=4+Math.random()*5+"s";

span.style.fontSize=(22+Math.random()*18)+"px";

document.body.appendChild(span);

setTimeout(()=>{
span.remove();
},9000);

}

setInterval(createText,500);

</script>

</body>
</html>
