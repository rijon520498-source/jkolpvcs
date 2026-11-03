
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sweet Cake | Bakery & Admin</title>
<link href="https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@400;500;600;700&family=Pacifico&family=Poppins:wght@400;500;600;700;800&display=swap" rel="stylesheet">

<style>
:root{
--pink:#f66b9f;
--deep:#e84785;
--pale:#fff0f6;
--cream:#fffafd;
--text:#513344;
--muted:#987d8b;
--green:#20b86b;
--shadow:0 12px 35px rgba(221,91,145,.12);
}
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Hind Siliguri',sans-serif;background:var(--cream);color:var(--text)}
button,input,textarea,select{font:inherit}
button{cursor:pointer;border:0}
a{text-decoration:none;color:inherit}
.container{width:min(1150px,92%);margin:auto}
.topbar{background:var(--deep);color:white;text-align:center;padding:9px;font-size:14px}
header{position:sticky;top:0;z-index:20;background:#ffffffed;backdrop-filter:blur(12px);box-shadow:0 3px 20px #00000008}
.nav{height:75px;display:flex;align-items:center;justify-content:space-between;gap:15px}
.logo{font:27px 'Pacifico',cursive;color:var(--deep)}
.links{display:flex;gap:25px;font-weight:600}
.links a:hover{color:var(--deep)}
.nav-actions{display:flex;gap:9px}
.btn{padding:11px 19px;border-radius:30px;font-weight:700;transition:.2s}
.btn:hover{transform:translateY(-2px)}
.pink{background:linear-gradient(135deg,#ff8db8,#e84785);color:white}
.soft{background:var(--pale);color:var(--deep)}
.green{background:var(--green);color:white}
.dark{background:#503344;color:white}
.hero{background:radial-gradient(circle at 80% 30%,#ffe0ed,transparent 35%),linear-gradient(120deg,#fff0f6,#fffafd);padding:65px 0}
.hero-grid{display:grid;grid-template-columns:1fr 1fr;align-items:center;gap:35px}
.eyebrow{display:inline-block;background:white;color:var(--deep);padding:8px 17px;border-radius:30px;font-weight:700;box-shadow:var(--shadow)}
.hero h1{font-size:clamp(40px,6vw,68px);line-height:1.2;margin:20px 0}
.hero h1 span{color:var(--deep)}
.hero p{color:var(--muted);line-height:1.9;font-size:17px;margin-bottom:25px}
.hero-img{height:410px;width:100%;object-fit:cover;border:9px solid white;border-radius:45% 45% 25px 25px;box-shadow:var(--shadow)}
.section{padding:65px 0}
.heading{text-align:center;margin-bottom:35px}
.heading small{color:var(--deep);font-weight:700;letter-spacing:2px}
.heading h2{font-size:34px;margin:8px 0}
.heading p{color:var(--muted)}
.features{display:grid;grid-template-columns:repeat(3,1fr);gap:17px;margin-top:30px}
.feature{background:white;padding:20px;border-radius:18px;box-shadow:var(--shadow)}
.feature b{font-size:17px}
.feature p{font-size:13px;color:var(--muted)}
.filters{display:flex;justify-content:center;flex-wrap:wrap;gap:10px;margin-bottom:30px}
.filter{padding:9px 20px;border-radius:30px;background:white;color:var(--text);border:1px solid #f8dbe7}
.filter.active,.filter:hover{background:var(--deep);color:white}
.products{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
.card{background:white;border-radius:22px;overflow:hidden;box-shadow:var(--shadow);border:1px solid #fff0f6;transition:.3s}
.card:hover{transform:translateY(-7px)}
.card img{width:100%;height:230px;object-fit:cover;background:var(--pale)}
.card-body{padding:17px}
.card-body h3{font-size:19px}
.card-body p{font-size:14px;color:var(--muted);min-height:25px}
.card-bottom{display:flex;align-items:center;justify-content:space-between;gap:8px;margin-top:15px}
.price{font:700 20px 'Poppins';color:var(--deep)}
.about{display:grid;grid-template-columns:1fr 1fr;gap:35px;align-items:center;background:var(--pale);padding:35px;border-radius:28px}
.about img{width:100%;height:320px;object-fit:cover;border-radius:20px}
.about p{color:var(--muted);line-height:1.9;margin:15px 0}
footer{background:#432b3b;color:white;padding:45px 0 20px;margin-top:65px}
.footer-grid{display:grid;grid-template-columns:2fr 1fr 1fr;gap:25px}
footer p,footer a{color:#e1cbd6;line-height:2}
footer h3{margin-bottom:10px}
.copy{text-align:center;border-top:1px solid #684e60;padding-top:17px;margin-top:30px;color:#e1cbd6}
.whatsapp{position:fixed;right:20px;bottom:20px;z-index:15;background:#20b86b;color:white;padding:13px 18px;border-radius:30px;font-weight:700;box-shadow:var(--shadow)}
/* CART */
.overlay{position:fixed;inset:0;background:#0007;z-index:40;display:none}
.overlay.show{display:block}
.drawer{position:fixed;right:-440px;top:0;width:min(420px,100%);height:100%;background:white;z-index:41;padding:22px;display:flex;flex-direction:column;transition:.3s}
.drawer.show{right:0}
.drawer-head{display:flex;justify-content:space-between;align-items:center;padding-bottom:15px;border-bottom:1px solid #eee}
.close{background:var(--pale);color:var(--deep);width:35px;height:35px;border-radius:50%;font-size:22px}
.cart-list{flex:1;overflow:auto;padding:15px 0}
.cart-row{display:flex;justify-content:space-between;align-items:center;padding:13px 0;border-bottom:1px solid #f6e5ed;gap:8px}
.qty{display:flex;align-items:center;gap:9px}
.qty button{width:27px;height:27px;border-radius:50%;background:var(--pale);color:var(--deep)}
.cart-total{padding-top:15px;border-top:1px solid #eee;display:flex;justify-content:space-between;font-size:20px;font-weight:700}
/* MODALS */
.modal{position:fixed;inset:0;background:#24121dcc;z-index:60;display:none;align-items:center;justify-content:center;padding:15px}
.modal.show{display:flex}
.modal-box{background:white;border-radius:23px;padding:25px;width:min(460px,100%);max-height:92vh;overflow:auto}
.modal-head{display:flex;justify-content:space-between;align-items:center;margin-bottom:18px}
.field{margin-bottom:14px}
.field label{display:block;font-weight:600;margin-bottom:5px}
.field input,.field textarea,.field select{width:100%;padding:12px;border:1px solid #f0d5e1;border-radius:11px;background:#fffafd;outline:none}
.field input:focus,.field textarea:focus{border-color:var(--pink)}
/* ADMIN */
.admin-page{display:none;min-height:100vh;background:#fff8fb}
.admin-header{background:white;padding:15px 0;box-shadow:var(--shadow)}
.admin-nav{display:flex;justify-content:space-between;align-items:center;gap:10px}
.admin-layout{display:grid;grid-template-columns:220px 1fr;gap:22px;padding-top:25px;padding-bottom:45px}
.sidebar{background:white;border-radius:20px;padding:18px;height:max-content;box-shadow:var(--shadow)}
.sidebar h3{color:var(--deep);margin:5px 0 15px}
.side-btn{width:100%;text-align:left;padding:12px;border-radius:10px;background:white;color:var(--text);margin:3px 0;font-weight:600}
.side-btn.active,.side-btn:hover{background:var(--pale);color:var(--deep)}
.admin-main{min-width:0}
.welcome{background:linear-gradient(120deg,#ff8db8,#e84785);color:white;padding:25px;border-radius:20px;margin-bottom:20px}
.welcome h2{font-size:26px}
.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:15px;margin-bottom:22px}
.stat{background:white;padding:20px;border-radius:17px;box-shadow:var(--shadow)}
.stat span{font-size:25px}
.stat h3{font:700 25px 'Poppins';color:var(--deep)}
.stat p{color:var(--muted);font-size:13px}
.admin-card{background:white;padding:22px;border-radius:18px;box-shadow:var(--shadow);margin-bottom:20px}
.admin-card h3{margin-bottom:15px}
.admin-products{display:grid;grid-template-columns:repeat(2,1fr);gap:13px}
.admin-product{border:1px solid #f4e0e9;border-radius:14px;padding:10px;display:flex;gap:12px;align-items:center;min-width:0}
.admin-product img{width:75px;height:75px;object-fit:cover;border-radius:10px;background:var(--pale)}
.admin-product-info{min-width:0;flex:1}
.admin-product-info b{display:block;overflow-wrap:anywhere}
.admin-product-info small{color:var(--deep)}
.admin-actions{display:flex;gap:5px;margin-top:7px}
.mini{padding:6px 10px;border-radius:8px;font-size:12px;font-weight:700}
.edit{background:#fff0cf;color:#966400}
.delete{background:#ffe7ed;color:#d33163}
.add-form{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.add-form .full{grid-column:1/-1}
.preview{width:100%;max-height:180px;object-fit:contain;background:var(--pale);border-radius:12px;display:none;margin-top:10px}
.empty{text-align:center;color:var(--muted);padding:35px}
.notice{background:#fff3d8;color:#765400;padding:12px;border-radius:12px;font-size:13px;line-height:1.7;margin-bottom:15px}
.login-wrap{min-height:100vh;display:grid;place-items:center;padding:20px;background:linear-gradient(130deg,#fff0f6,#fffafd)}
.login-box{background:white;padding:35px;border-radius:25px;box-shadow:var(--shadow);width:min(400px,100%);text-align:center}
.login-box .logo{font-size:34px}
.login-box p{color:var(--muted);margin:8px 0 20px}
.login-box input{width:100%;padding:13px;border:1px solid #f0d5e1;border-radius:12px;margin-bottom:13px}
.toast{position:fixed;left:50%;bottom:25px;transform:translate(-50%,20px);background:#503344;color:white;padding:12px 20px;border-radius:30px;opacity:0;pointer-events:none;transition:.3s;z-index:100}
.toast.show{opacity:1;transform:translate(-50%,0)}
@media(max-width:800px){
.links{display:none}
.hero-grid,.about{grid-template-columns:1fr}
.hero{text-align:center}
.hero-img{height:300px}
.features{grid-template-columns:1fr}
.products{grid-template-columns:repeat(2,1fr);gap:12px}
.card img{height:160px}
.admin-layout{grid-template-columns:1fr}
.sidebar{display:flex;flex-wrap:wrap;gap:5px}
.sidebar h3{width:100%}
.side-btn{width:auto}
.admin-products{grid-template-columns:1fr}
}
@media(max-width:500px){
.logo{font-size:22px}
.nav{height:65px}
.nav-actions .btn{padding:9px 11px;font-size:12px}
.hero{padding:45px 0}
.hero h1{font-size:42px}
.heading h2{font-size:27px}
.products{grid-template-columns:repeat(2,minmax(0,1fr))}
.card-body{padding:11px}
.card-body h3{font-size:15px}
.card-body p{font-size:12px}
.card-bottom{align-items:flex-start;flex-direction:column}
.price{font-size:17px}
.card-bottom .btn{padding:8px 12px;font-size:12px}
.stats{grid-template-columns:1fr}
.add-form{grid-template-columns:1fr}
.add-form .full{grid-column:auto}
.footer-grid{grid-template-columns:1fr}
}
</style>
</head>

<body>

<div id="storePage">
<div class="topbar">🎀 Sweet Cake — প্রতিটি কেকেই ভালোবাসার ছোঁয়া! 🎂</div>
<header>
<div class="container nav">
<a class="logo" href="#">Sweet♥Cake</a>
<nav class="links">
<a href="#">হোম</a><a href="#shop">আমাদের কেক</a>
<a href="#about">আমাদের সম্পর্কে</a><a href="#contact">যোগাযোগ</a>
</nav>
<div class="nav-actions">
<button class="btn soft" onclick="openCart()">🛒 Cart <span id="cartCount">0</span></button>
<button class="btn pink" onclick="showLogin()">Admin</button>
</div>
</div>
</header>

<section class="hero">
<div class="container hero-grid">
<div>
<span class="eyebrow">🌸 Freshly Baked With Love</span>
<h1>জীবনের প্রতিটি মুহূর্ত হোক <span>মিষ্টি!</span></h1>
<p>আপনার বিশেষ মুহূর্তকে আরও সুন্দর করে তুলতে নিয়ে এসেছি ভালোবাসা দিয়ে তৈরি সুস্বাদু কেক।</p>
<a href="#shop" class="btn pink">কেক অর্ডার করুন →</a>
</div>
<img class="hero-img" src="https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=1000" alt="Sweet Cake">
</div>
</section>

<div class="container features">
<div class="feature"><b>🍰 Fresh & Delicious</b><p>প্রতিদিন তৈরি ফ্রেশ কেক</p></div>
<div class="feature"><b>🚚 Home Delivery</b><p>আপনার ঠিকানায় পৌঁছে যাবে</p></div>
<div class="feature"><b>💗 Made With Love</b><p>প্রতিটি কেকে যত্নের ছোঁয়া</p></div>
</div>

<section class="section" id="shop">
<div class="container">
<div class="heading"><small>OUR COLLECTION</small><h2>আমাদের স্পেশাল কেক 🎂</h2><p>আপনার পছন্দের কেকটি বেছে নিন</p></div>
<div class="filters">
<button class="filter active" onclick="filterProducts('all',this)">সব কেক</button>
<button class="filter" onclick="filterProducts('birthday',this)">Birthday</button>
<button class="filter" onclick="filterProducts('chocolate',this)">Chocolate</button>
<button class="filter" onclick="filterProducts('special',this)">Special</button>
</div>
<div class="products" id="productGrid"></div>
</div>
</section>

<section class="section" id="about">
<div class="container about">
<img src="https://images.unsplash.com/photo-1557308536-ee471ef2c390?w=900" alt="Bakery">
<div><small style="color:var(--deep)">OUR STORY 💕</small><h2>একটু মিষ্টি, অনেকটা ভালোবাসা!</h2>
<p>Sweet Cake-এ প্রতিটি কেক তৈরি হয় যত্ন, ভালোবাসা ও সুন্দর মুহূর্তের কথা ভেবে। আপনার আনন্দের দিনে আমরা পাশে থাকতে চাই।</p>
<a href="#shop" class="btn pink">কেক দেখুন</a></div>
</div>
</section>

<footer id="contact">
<div class="container">
<div class="footer-grid">
<div><div class="logo" style="color:#ff8db8">Sweet Cake ♥</div><p>আপনার প্রতিটি আনন্দের মুহূর্তে এক টুকরো মিষ্টি ভালোবাসা।</p></div>
<div><h3>Quick Links</h3><p><a href="#">Home</a><br><a href="#shop">Our Cakes</a><br><a href="#about">About Us</a></p></div>
<div><h3>Contact</h3><p>📍 আপনার দোকানের ঠিকানা<br>📞 আপনার ফোন নম্বর<br>🕒 সকাল ৯টা - রাত ১০টা</p></div>
</div>
<div class="copy">© 2026 Sweet Cake. Made with 💗</div>
</div>
</footer>
<a class="whatsapp" id="whatsappFloat" href="#" onclick="return openWhatsApp(event)">🟢 WhatsApp</a>
</div>

<!-- ADMIN LOGIN -->
<div class="modal" id="loginModal">
<div class="login-box">
<div class="logo">Sweet Cake</div>
<h2>Admin Login 🔐</h2>
<p>শুধু অ্যাডমিন প্রবেশ করতে পারবেন</p>
<form onsubmit="login(event)">
<input id="adminPassword" type="password" placeholder="Admin Password" required>
<button class="btn pink" style="width:100%">Login →</button>
</form>
<button class="btn soft" style="margin-top:12px" onclick="hideLogin()">ফিরে যান</button>
</div>
</div>

<!-- ADMIN PAGE -->
<div class="admin-page" id="adminPage">
<div class="admin-header">
<div class="container admin-nav">
<a class="logo" href="#">Sweet♥Cake Admin</a>
<div>
<button class="btn soft" onclick="showStore()">🌐 Store</button>
<button class="btn pink" onclick="logout()">Logout</button>
</div>
</div>
</div>

<div class="container admin-layout">
<aside class="sidebar">
<h3>🎀 Dashboard</h3>
<button class="side-btn active" onclick="showAdminTab('dashboard',this)">📊 Overview</button>
<button class="side-btn" onclick="showAdminTab('manage',this)">🎂 Manage Cakes</button>
<button class="side-btn" onclick="showAdminTab('add',this);resetProductForm()">➕ Add New Cake</button>
<button class="side-btn" onclick="showAdminTab('settings',this)">⚙️ Settings</button>
</aside>

<main class="admin-main">
<div id="dashboardTab">
<div class="welcome"><h2>Welcome to Sweet Cake! 💗</h2><p>তোমার Cake Shop-এর কন্ট্রোল সেন্টার</p></div>
<div class="stats">
<div class="stat"><span>🎂</span><h3 id="totalProducts">0</h3><p>Total Cakes</p></div>
<div class="stat"><span>💰</span><h3 id="averagePrice">৳0</h3><p>Average Price</p></div>
<div class="stat"><span>🛍️</span><h3 id="cartProducts">0</h3><p>Cart Items</p></div>
</div>
<div class="admin-card"><h3>✨ Quick Actions</h3>
<button class="btn pink" onclick="showAdminTab('add');resetProductForm()">+ নতুন কেক যোগ করুন</button>
<button class="btn soft" onclick="showAdminTab('manage')">সব কেক দেখুন</button>
</div>
</div>

<div id="manageTab" style="display:none">
<div class="admin-card">
<h2>🎂 Manage Cakes</h2>
<p style="color:var(--muted);margin:5px 0 18px">তোমার সব কেক এখান থেকে পরিবর্তন করো।</p>
<div id="adminProducts" class="admin-products"></div>
</div>
</div>

<div id="addTab" style="display:none">
<div class="admin-card">
<h2 id="formTitle">➕ নতুন কেক যোগ করো</h2>
<p style="color:var(--muted);margin:5px 0 18px">কেকের ছবি, নাম, দাম ও বিবরণ দাও।</p>
<form onsubmit="saveProduct(event)">
<input type="hidden" id="editId">
<div class="add-form">
<div class="field">
<label>কেকের নাম *</label>
<input id="cakeName" required placeholder="যেমন: Chocolate Cake">
</div>
<div class="field">
<label>দাম (টাকা) *</label>
<input id="cakePrice" type="number" min="1" required placeholder="1200">
</div>
<div class="field">
<label>ক্যাটাগরি</label>
<select id="cakeCategory">
<option value="birthday">Birthday</option>
<option value="chocolate">Chocolate</option>
<option value="special">Special</option>
</select>
</div>
<div class="field">
<label>ছবি আপলোড *</label>
<input id="cakeImage" type="file" accept="image/*" onchange="previewImage(event)">
</div>
<div class="field full">
<label>কেকের বিবরণ</label>
<textarea id="cakeDescription" rows="3" placeholder="কেক সম্পর্কে কিছু লিখুন"></textarea>
</div>
<div class="full">
<img id="imagePreview" class="preview" alt="Image preview">
</div>
<div class="full" style="display:flex;gap:10px;flex-wrap:wrap">
<button class="btn pink" type="submit">💾 Save Cake</button>
<button class="btn soft" type="button" onclick="resetProductForm()">Reset</button>
</div>
</div>
</form>
</div>
</div>

<div id="settingsTab" style="display:none">
<div class="admin-card">
<h2>⚙️ Store Settings</h2>
<div class="notice">এই ডেমো সংস্করণে তথ্য ও ছবি এই ব্রাউজারের Local Storage-এ রাখা হয়। ব্রাউজারের ডেটা মুছে ফেললে তথ্য হারাতে পারে।</div>
<div class="field"><label>WhatsApp নম্বর (দেশের কোডসহ)</label><input id="settingWhatsapp" placeholder="8801XXXXXXXXX"></div>
<button class="btn pink" onclick="saveSettings()">Save Settings</button>
<hr style="margin:22px 0;border:0;border-top:1px solid #eee">
<h3>Admin Password পরিবর্তন</h3>
<div class="field"><label>বর্তমান পাসওয়ার্ড</label><input type="password" id="oldPassword"></div>
<div class="field"><label>নতুন পাসওয়ার্ড</label><input type="password" id="newPassword"></div>
<button class="btn pink" onclick="changePassword()">পাসওয়ার্ড পরিবর্তন</button>
</div>
</div>

</main>
</div>
</div>

<!-- CART DRAWER -->
<div class="overlay" id="overlay" onclick="closeCart()"></div>
<div class="drawer" id="drawer">
<div class="drawer-head"><h2>🛒 Your Cart</h2><button class="close" onclick="closeCart()">×</button></div>
<div class="cart-list" id="cartList"></div>
<div class="cart-total"><span>মোট</span><span id="cartTotal">৳0</span></div>
<button class="btn green" style="width:100%;margin-top:15px" onclick="checkout()">WhatsApp-এ অর্ডার করুন →</button>
</div>

<!-- CHECKOUT MODAL -->
<div class="modal" id="checkoutModal">
<div class="modal-box">
<div class="modal-head"><h2>🎀 অর্ডার সম্পন্ন করুন</h2><button class="close" onclick="closeCheckout()">×</button></div>
<form onsubmit="sendOrder(event)">
<div class="field"><label>আপনার নাম *</label><input id="customerName" required></div>
<div class="field"><label>মোবাইল নম্বর *</label><input id="customerPhone" type="tel" required></div>
<div class="field"><label>ডেলিভারি ঠিকানা *</label><textarea id="customerAddress" rows="3" required></textarea></div>
<div class="field"><label>বিশেষ নির্দেশনা</label><textarea id="customerNote" rows="2"></textarea></div>
<button class="btn green" style="width:100%">🟢 WhatsApp-এ অর্ডার পাঠান</button>
</form>
</div>
</div>

<div class="toast" id="toast"></div>

<script>
// =============================
// BASIC CONFIGURATION
// =============================
const DEFAULT_ADMIN_PASSWORD = "123456";
const DEFAULT_WHATSAPP = "8801XXXXXXXXX";

// Change this password before using the site.
// This standalone demo is not a secure production login.

const starterProducts = [
{id:1,name:"Birthday Special",price:1200,category:"birthday",description:"সুন্দর ও সুস্বাদু জন্মদিনের কেক",image:"https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=700"},
{id:2,name:"Chocolate Heaven",price:1400,category:"chocolate",description:"চকলেটের দারুণ স্বাদে ভরপুর",image:"https://images.unsplash.com/photo-1606313564200-e75d5e30476c?w=700"},
{id:3,name:"Strawberry Dream",price:1500,category:"special",description:"স্ট্রবেরির মিষ্টি ভালোবাসা",image:"https://images.unsplash.com/photo-1565958011703-44f9829ba187?w=700"},
{id:4,name:"Vanilla Dream",price:1000,category:"birthday",description:"নরম ক্রিমের অসাধারণ স্বাদ",image:"https://images.unsplash.com/photo-1464349095431-e9a21285b5f3?w=700"},
{id:5,name:"Dark Chocolate",price:1600,category:"chocolate",description:"চকলেট প্রেমীদের জন্য স্পেশাল",image:"https://images.unsplash.com/photo-1571115177098-24ec42ed204d?w=700"},
{id:6,name:"Love Special",price:1800,category:"special",description:"প্রিয়জনের জন্য ভালোবাসার কেক",image:"https://images.unsplash.com/photo-1488477181946-6428a0291777?w=700"}
];

function readData(key,fallback){
try{
const value=localStorage.getItem(key);
return value===null?fallback:JSON.parse(value);
}catch(e){return fallback}
}
function saveData(key,value){
try{
localStorage.setItem(key,JSON.stringify(value));
return true;
}catch(e){
toast("Storage পূর্ণ! ছোট ছবি ব্যবহার করো।");
return false;
}
}

let products=readData("sweetcake_products",starterProducts);
let cart=[];
let currentFilter="all";
let uploadedImage="";
let editingId=null;

function money(n){return "৳ "+Number(n).toLocaleString("en-IN")}
function toast(message){
const el=document.getElementById("toast");
el.textContent=message;el.classList.add("show");
setTimeout(()=>el.classList.remove("show"),2500);
}

// =============================
// STOREFRONT
// =============================
function renderProducts(){
const grid=document.getElementById("productGrid");
const filtered=products.filter(p=>currentFilter==="all"||p.category===currentFilter);
if(!filtered.length){
grid.innerHTML='<div class="empty">এই ক্যাটাগরিতে এখনো কোনো কেক নেই 🍰</div>';
return;
}
grid.innerHTML=filtered.map(p=>`
<div class="card">
<img src="${escapeAttr(p.image)}" alt="${escapeAttr(p.name)}">
<div class="card-body">
<h3>${escapeHTML(p.name)}</h3>
<p>${escapeHTML(p.description||"Freshly baked with love")}</p>
<div class="card-bottom">
<span class="price">${money(p.price)}</span>
<button class="btn soft" onclick="addToCart(${Number(p.id)})">+ Add</button>
</div>
</div>
</div>`).join("");
}
function filterProducts(category,button){
currentFilter=category;
document.querySelectorAll(".filter").forEach(b=>b.classList.remove("active"));
button.classList.add("active");
renderProducts();
}
function escapeHTML(s){
return String(s??"").replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));
}
function escapeAttr(s){return escapeHTML(s)}

// =============================
// CART
// =============================
function addToCart(id){
const p=products.find(x=>x.id===id);
if(!p)return;
const found=cart.find(x=>x.id===id);
if(found)found.qty++;
else cart.push({...p,qty:1});
renderCart();openCart();
}
function renderCart(){
document.getElementById("cartCount").textContent=cart.reduce((a,b)=>a+b.qty,0);
document.getElementById("cartTotal").textContent=money(cart.reduce((a,b)=>a+b.price*b.qty,0));
const el=document.getElementById("cartList");
if(!cart.length){el.innerHTML='<div class="empty">তোমার কার্ট এখনো খালি 🎂</div>';return}
el.innerHTML=cart.map(p=>`
<div class="cart-row">
<div><b>${escapeHTML(p.name)}</b><br><small>${money(p.price*p.qty)}</small></div>
<div class="qty">
<button onclick="changeQty(${p.id},-1)">−</button><b>${p.qty}</b>
<button onclick="changeQty(${p.id},1)">+</button>
</div></div>`).join("");
}
function changeQty(id,n){
const p=cart.find(x=>x.id===id);if(!p)return;
p.qty+=n;if(p.qty<=0)cart=cart.filter(x=>x.id!==id);
renderCart();
}
function openCart(){
document.getElementById("drawer").classList.add("show");
document.getElementById("overlay").classList.add("show");
}
function closeCart(){
document.getElementById("drawer").classList.remove("show");
document.getElementById("overlay").classList.remove("show");
}
function checkout(){
if(!cart.length){toast("আগে কেক কার্টে যোগ করো!");return}
closeCart();document.getElementById("checkoutModal").classList.add("show");
}
function closeCheckout(){document.getElementById("checkoutModal").classList.remove("show")}

function getWhatsapp(){
return localStorage.getItem("sweetcake_whatsapp")||DEFAULT_WHATSAPP;
}
function sendOrder(e){
e.preventDefault();
const number=getWhatsapp();
if(number.includes("X")){
toast("Admin Settings থেকে WhatsApp নম্বর সেট করো।");return;
}
let msg="🎂 *NEW ORDER - SWEET CAKE* 🎀\n\n";
msg+="👤 নাম: "+document.getElementById("customerName").value+"\n";
msg+="📞 ফোন: "+document.getElementById("customerPhone").value+"\n";
msg+="📍 ঠিকানা: "+document.getElementById("customerAddress").value+"\n\n";
msg+="🍰 *অর্ডার:*\n";
cart.forEach(p=>msg+=`• ${p.name} × ${p.qty} = ${money(p.price*p.qty)}\n`);
msg+="\n💰 মোট: "+money(cart.reduce((a,p)=>a+p.price*p.qty,0));
const note=document.getElementById("customerNote").value;
if(note)msg+="\n📝 নির্দেশনা: "+note;
window.open("https://wa.me/"+number+"?text="+encodeURIComponent(msg),"_blank");
closeCheckout();
}
function openWhatsApp(e){
const number=getWhatsapp();
if(number.includes("X")){
e.preventDefault();toast("Admin Settings থেকে WhatsApp নম্বর সেট করো।");return false;
}
e.currentTarget.href="https://wa.me/"+number;
return true;
}

// =============================
// ADMIN LOGIN
// =============================
function showLogin(){document.getElementById("loginModal").classList.add("show")}
function hideLogin(){document.getElementById("loginModal").classList.remove("show")}
function login(e){
e.preventDefault();
const saved=localStorage.getItem("sweetcake_password")||DEFAULT_ADMIN_PASSWORD;
if(document.getElementById("adminPassword").value!==saved){
toast("ভুল পাসওয়ার্ড!");return;
}
hideLogin();showAdmin();document.getElementById("adminPassword").value="";
}
function showAdmin(){
document.getElementById("storePage").style.display="none";
document.getElementById("adminPage").style.display="block";
renderAdmin();updateStats();
}
function showStore(){
document.getElementById("adminPage").style.display="none";
document.getElementById("storePage").style.display="block";
renderProducts();
}
function logout(){showStore();toast("Admin থেকে Logout হয়েছে।")}

// =============================
// ADMIN NAVIGATION
// =============================
function showAdminTab(tab,button){
["dashboard","manage","add","settings"].forEach(t=>{
document.getElementById(t+"Tab").style.display=t===tab?"block":"none";
});
document.querySelectorAll(".side-btn").forEach(b=>b.classList.remove("active"));
if(button)button.classList.add("active");
if(tab==="manage")renderAdmin();
if(tab==="dashboard")updateStats();
if(tab==="settings")document.getElementById("settingWhatsapp").value=getWhatsapp();
}

// =============================
// PRODUCT MANAGEMENT
// =============================
function renderAdmin(){
const el=document.getElementById("adminProducts");
if(!products.length){el.innerHTML='<div class="empty">এখনো কোনো কেক যোগ করা হয়নি।</div>';return}
el.innerHTML=products.map(p=>`
<div class="admin-product">
<img src="${escapeAttr(p.image)}" alt="">
<div class="admin-product-info">
<b>${escapeHTML(p.name)}</b>
<small>${money(p.price)}</small>
<div class="admin-actions">
<button class="mini edit" onclick="editProduct(${p.id})">✏️ Edit</button>
<button class="mini delete" onclick="deleteProduct(${p.id})">🗑️ Delete</button>
</div>
</div>
</div>`).join("");
}
function updateStats(){
document.getElementById("totalProducts").textContent=products.length;
const avg=products.length?products.reduce((a,p)=>a+p.price,0)/products.length:0;
document.getElementById("averagePrice").textContent=money(Math.round(avg));
document.getElementById("cartProducts").textContent=cart.reduce((a,p)=>a+p.qty,0);
}
function showAddTab(){
showAdminTab("add");
}
function resetProductForm(){
editingId=null;uploadedImage="";
document.getElementById("editId").value="";
document.getElementById("formTitle").textContent="➕ নতুন কেক যোগ করো";
document.getElementById("cakeName").value="";
document.getElementById("cakePrice").value="";
document.getElementById("cakeCategory").value="birthday";
document.getElementById("cakeDescription").value="";
document.getElementById("cakeImage").value="";
document.getElementById("imagePreview").style.display="none";
document.getElementById("imagePreview").src="";
}
function previewImage(e){
const file=e.target.files[0];if(!file)return;
if(!file.type.startsWith("image/")){toast("একটি ছবি নির্বাচন করো।");return}
if(file.size>1.5*1024*1024){
toast("ছবিটি 1.5 MB-এর চেয়ে ছোট করে আপলোড করো।");e.target.value="";return;
}
const reader=new FileReader();
reader.onload=()=>{
uploadedImage=reader.result;
const img=document.getElementById("imagePreview");
img.src=uploadedImage;img.style.display="block";
};
reader.readAsDataURL(file);
}
function saveProduct(e){
e.preventDefault();
const name=document.getElementById("cakeName").value.trim();
const price=Number(document.getElementById("cakePrice").value);
const category=document.getElementById("cakeCategory").value;
const description=document.getElementById("cakeDescription").value.trim();
const old=products.find(p=>p.id===editingId);
const image=uploadedImage||(old?old.image:"");
if(!image){toast("কেকের ছবি নির্বাচন করো!");return}
if(!name||!price||price<1){toast("নাম ও সঠিক দাম দাও।");return}
let next;
if(old){
next=products.map(p=>p.id===editingId?{...p,name,price,category,description,image}:p);
}else{
next=[...products,{id:Date.now(),name,price,category,description,image}];
}
if(!saveData("sweetcake_products",next))return;
products=next;
renderProducts();renderAdmin();updateStats();resetProductForm();
showAdminTab("manage",document.querySelectorAll(".side-btn")[1]);
toast(old?"কেক আপডেট হয়েছে!":"নতুন কেক যোগ হয়েছে! 🎂");
}
function editProduct(id){
const p=products.find(x=>x.id===id);if(!p)return;
editingId=id;uploadedImage=p.image;
showAdminTab("add",document.querySelectorAll(".side-btn")[2]);
document.getElementById("formTitle").textContent="✏️ কেক পরিবর্তন করো";
document.getElementById("cakeName").value=p.name;
document.getElementById("cakePrice").value=p.price;
document.getElementById("cakeCategory").value=p.category;
document.getElementById("cakeDescription").value=p.description||"";
const img=document.getElementById("imagePreview");
img.src=p.image;img.style.display="block";
document.getElementById("cakeImage").value="";
}
function deleteProduct(id){
if(!confirm("এই কেকটি ডিলিট করতে চাও?"))return;
const next=products.filter(p=>p.id!==id);
if(!saveData("sweetcake_products",next))return;
products=next;cart=cart.filter(p=>p.id!==id);
renderProducts();renderAdmin();renderCart();updateStats();
toast("কেক ডিলিট হয়েছে।");
}

// =============================
// SETTINGS
// =============================
function saveSettings(){
const number=document.getElementById("settingWhatsapp").value.trim().replace(/\D/g,"");
if(number.length<10){toast("সঠিক WhatsApp নম্বর দাও।");return}
localStorage.setItem("sweetcake_whatsapp",number);
toast("WhatsApp নম্বর সেভ হয়েছে!");
}
function changePassword(){
const old=document.getElementById("oldPassword").value;
const next=document.getElementById("newPassword").value;
const current=localStorage.getItem("sweetcake_password")||DEFAULT_ADMIN_PASSWORD;
if(old!==current){toast("বর্তমান পাসওয়ার্ড ভুল!");return}
if(next.length<6){toast("নতুন পাসওয়ার্ড কমপক্ষে ৬ অক্ষরের হতে হবে।");return}
localStorage.setItem("sweetcake_password",next);
document.getElementById("oldPassword").value="";
document.getElementById("newPassword").value="";
toast("পাসওয়ার্ড পরিবর্তন হয়েছে!");
}

// INITIALIZE
renderProducts();
renderCart();
</script>
</body>
</html>
