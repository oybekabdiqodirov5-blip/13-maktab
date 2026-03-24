# 13-maktab
13-maktab bilim va kunikmalar maskani 
8<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>13-Maktab</title>
<style>
/* Umumiy sozlamalar */
* { margin: 0; padding: 0; box-sizing: border-box; }
body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: #f4f7f8; }

/* Header va navigatsiya */
header { background:#1f3a93; color:white; padding:25px 0; text-align:center; }
header h1 { font-size:48px; }
nav { background:#2c3e50; display:flex; justify-content:center; flex-wrap:wrap; }
nav a { color:white; text-decoration:none; padding:12px 20px; margin:5px; border-radius:5px; transition:0.3s; }
nav a:hover { background:#1abc9c; }

/* Hero section */
.hero { height:70vh; background-image: url('13maktab.jpg'); background-size:cover; background-position:center; display:flex; flex-direction:column; justify-content:center; align-items:center; color:white; text-align:center; }
.hero h1 { font-size:60px; text-shadow: 2px 2px 8px #000; }
.hero p { font-size:24px; margin-top:10px; text-shadow:1px 1px 5px #000; }

/* Bo‘limlar */
section { padding:60px 20px; max-width:1200px; margin:auto; }
section h2 { text-align:center; margin-bottom:40px; color:#1f3a93; }
.cards { display:flex; flex-wrap:wrap; justify-content:center; gap:25px; }
.card { background:white; padding:25px; width:300px; border-radius:12px; box-shadow:0 6px 15px rgba(0,0,0,0.1); transition:0.3s; }
.card:hover { transform:translateY(-5px); box-shadow:0 10px 20px rgba(0,0,0,0.2); }
.card h3 { color:#1f3a93; margin-bottom:10px; }
.card p { color:#555; }

/* Kontakt formasi */
form { background:white; padding:30px; border-radius:12px; box-shadow:0 6px 15px rgba(0,0,0,0.1); max-width:600px; margin:auto; display:flex; flex-direction:column; }
form input, form textarea { width:100%; padding:12px; margin-bottom:15px; border:1px solid #ccc; border-radius:8px; }
form button { background:#1f3a93; color:white; padding:12px; border:none; border-radius:8px; cursor:pointer; transition:0.3s; font-size:16px; }
form button:hover { background:#1abc9c; }

/* Admin panel demo */
#adminPanel { display:none; text-align:center; padding:20px; background:white; margin:20px auto; border-radius:10px; max-width:600px; box-shadow:0 6px 15px rgba(0,0,0,0.1); }

/* Footer */
footer { background:#2c3e50; color:white; text-align:center; padding:25px 0; margin-top:40px; }

/* Responsive */
@media(max-width:768px){
    nav { flex-direction:column; }
    .cards { flex-direction:column; align-items:center; }
    .hero h1 { font-size:40px; }
}
</style>
</head>
<body>

<header>
    <h1>13-Maktab</h1>
</header>

<nav>
    <a href="#">Bosh sahifa</a>
    <a href="#news">Yangiliklar</a>
    <a href="#students">O‘quvchilar</a>
    <a href="#teachers">O‘qituvchilar</a>
    <a href="#contact">Bog‘lanish</a>
    <a href="#adminDemo">Admin</a>
</nav>

<section class="hero">
    <h1>13-Maktabga Xush Kelibsiz!</h1>
    <p>Bilim va tarbiya maskani</p>
</section>

<section id="news">
    <h2>Yangiliklar</h2>
    <div class="cards">
        <div class="card">
            <h3>Yangi darsliklar</h3>
            <p>2026-yilda yangi darsliklar maktabimizga yetib keldi.</p>
        </div>
        <div class="card">
            <h3>Sport musobaqalari</h3>
            <p>O‘quvchilarimiz sport musobaqalarida faol ishtirok etdilar.</p>
        </div>
        <div class="card">
            <h3>San’at ko‘rgazmasi</h3>
            <p>Maktabimiz san’at darslari natijalarini namoyish qiladi.</p>
        </div>
    </div>
</section>

<section id="students">
    <h2>O‘quvchilarimiz</h2>
    <div class="cards">
        <div class="card">
            <h3>Akmal</h3>
            <p>Matematika fanidan yetakchi o‘quvchi.</p>
        </div>
        <div class="card">
            <h3>Malika</h3>
            <p>Fan olimpiadasi g‘olibi.</p>
        </div>
    </div>
</section>

<section id="teachers">
    <h2>O‘qituvchilarimiz</h2>
    <div class="cards">
        <div class="card">
            <h3>Mr. Rustamov</h3>
            <p>Matematika fani o‘qituvchisi.</p>
        </div>
        <div class="card">
            <h3>Ms. Dilbar</h3>
            <p>Ingliz tili fani o‘qituvchisi.</p>
        </div>
    </div>
</section>

<section id="contact">
    <h2>Biz bilan bog‘lanish</h2>
    <form>
        <input type="text" placeholder="Ismingiz" required>
        <input type="email" placeholder="Email manzilingiz" required>
        <textarea placeholder="Xabaringiz" rows="5" required></textarea>
        <button type="submit">Yuborish</button>
    </form>
</section>

<section id="adminDemo">
    <h2>Admin Panel /h2>
    <form id="loginForm" style="max-width:400px;margin:auto;">
        <input type="text" id="username" placeholder="Foydalanuvchi nomi" required>
        <input type="password" id="password" placeholder="Parol" required>
        <button type="submit">Kirish</button>
    </form>
    <div id="adminPanel">
        <h3>Admin Panel</h3>
        <p>Yangilik qo‘shish, foydalanuvchilarni boshqarish va sozlamalar</p>
        <button onclick="logout()">Chiqish</button>
    </div>
</section>

<footer>
    <p>&copy; 2026 13-Maktab. Barcha huquqlar himoyalangan.</p>
</footer>

<script>
// admin login
const DEMO_USER = {username:"admin", password:"123456"};
document.getElementById("loginForm").addEventListener("submit", function(e){
    e.preventDefault();
    let user = document.getElementById("ozodbek.nazirov").value;
    let pass = document.getElementById("ozodbek0909@").value;
    
    if(user === DEMO_USER.username && pass === DEMO_USER.password){
        document.getElementById("loginForm").style.display = "none";
        document.getElementById("adminPanel").style.display = "block";
        alert("Xush kelibsiz, Admin!");
    } else {
        alert("Foydalanuvchi nomi yoki parol xato!");
    }
});

function logout(){
    document.getElementById("adminPanel").style.display = "none";
    document.getElementById("loginForm").style.display = "flex";
    document.getElementById("username").value="";
    document.getElementById("password").value="";
}
</script>

</body>
</html>
