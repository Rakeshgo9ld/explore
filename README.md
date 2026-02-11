<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ExploreFun – Activities Booking</title>

<!-- Razorpay -->
<script src="https://checkout.razorpay.com/v1/checkout.js"></script>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI',sans-serif}
html{scroll-behavior:smooth}
body{background:#f5f7fb;color:#333}

/* HEADER */
header{
  background:linear-gradient(90deg,#1d4ed8,#2563eb);
  color:#fff;
  padding:20px 0 40px;
  position:sticky;
  top:0;
  z-index:999;
}
.header-container{
  width:90%;max-width:1200px;margin:auto;
  display:flex;justify-content:space-between;align-items:center
}
.logo{font-size:28px;font-weight:800}
nav a{color:#fff;margin-left:20px;text-decoration:none;font-weight:500}

/* SEARCH */
.search-box{margin-top:25px;display:flex;justify-content:center}
.search-box input{
  width:100%;max-width:520px;
  padding:14px 22px;
  border-radius:30px;
  border:none;
  font-size:16px;
  outline:none;
  box-shadow:0 10px 30px rgba(0,0,0,.25);
}

/* SECTION */
.section{padding:70px 0}
.container{width:90%;max-width:1200px;margin:auto}

/* GRID */
.activity-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(320px,1fr));
  gap:30px
}

/* CARD */
.activity-card{
  background:#fff;
  border-radius:18px;
  overflow:hidden;
  box-shadow:0 15px 40px rgba(0,0,0,.12);
  transition:.4s;
  position:relative
}
.activity-card:hover{
  transform:translateY(-8px);
  box-shadow:0 30px 70px rgba(29,78,216,.35)
}
.activity-card img{
  width:100%;
  height:220px;
  object-fit:cover;
  transition:.6s
}
.activity-card:hover img{transform:scale(1.12)}

.badge{
  position:absolute;
  top:15px;left:15px;
  background:linear-gradient(90deg,#facc15,#f97316);
  padding:6px 14px;
  font-size:12px;
  font-weight:700;
  border-radius:30px;
  z-index:5
}

.activity-info{padding:20px}
.location{color:#777;margin-bottom:10px}

/* OPTIONS */
.options{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:12px;
  margin-bottom:15px
}
.options label{font-size:13px;color:#555}
.options input,.options select{
  width:100%;
  padding:8px;
  border-radius:8px;
  border:1px solid #ddd
}

/* GUEST */
.guest-select{display:flex;gap:15px;margin-bottom:15px}
.guest-select input{width:70px;padding:6px}

/* PRICE */
.price-info{font-size:14px;margin-bottom:8px}
.total{color:#e11d48;margin-bottom:15px}

/* BUTTONS */
.btn-group{display:flex;gap:10px}
button{
  border:none;
  padding:11px 15px;
  border-radius:12px;
  cursor:pointer;
  font-weight:600
}
.book-btn{background:#1d4ed8;color:#fff}
.pdf-btn{background:#e5e7eb}

/* TRUST */
.trust h2{text-align:center;margin-bottom:40px}
.trust-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
  gap:25px
}
.trust-card{
  background:#fff;
  padding:30px;
  border-radius:16px;
  text-align:center;
  box-shadow:0 10px 30px rgba(0,0,0,.1)
}

/* REVIEWS */
.reviews-section{background:#fff;padding:70px 0}
.reviews-title{text-align:center;font-size:28px;margin-bottom:40px}
.review-card{
  background:#f8fafc;
  border-radius:16px;
  padding:25px;
  box-shadow:0 10px 30px rgba(0,0,0,.08)
}

/* FOOTER */
footer{
  background:#0f172a;
  color:#cbd5e1;
  padding:35px 0;
  margin-top:60px
}
.footer-container{
  width:90%;max-width:1200px;margin:auto;
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(200px,1fr))
}
footer h4{color:#fff;margin-bottom:10px}

#noResults{text-align:center;font-size:18px;display:none}
</style>
</head>

<body>

<header>
  <div class="header-container">
    <div class="logo">ExploreFun</div>
    <nav>
      <a href="#">Activities</a>
      <a href="#">Refer & Earn</a>
      <a href="#">Login</a>
    </nav>
  </div>
  <div class="search-box">
    <input type="text" id="searchInput" placeholder="Search activity or destination">
  </div>
</header>

<section class="section">
<div class="container">
<div class="activity-grid">

<!-- CARD 1 -->
<div class="activity-card" data-name="desert safari" data-destination="dubai" data-adult-price="6499" data-child-price="4499">
<span class="badge">🔥 Best Seller</span>
<img src="DESERT SAFARI.avif">
<div class="activity-info">
<h3>Desert Safari</h3>
<p class="location">Dubai</p>
<div class="options">
<input type="date" class="booking-date">
<select class="duration"><option>Evening</option></select>
</div>
<div class="guest-select">
<input type="number" class="adult-count" value="1" min="1">
<input type="number" class="child-count" value="0" min="0">
</div>
<div class="price-info">Adult ₹6,499 | Child ₹4,499</div>
<h3 class="total">₹<span class="total-price">6,499</span></h3>
<div class="btn-group">
<button class="pdf-btn">PDF</button>
<button class="book-btn">Book Now</button>
</div>
</div>
</div>

<!-- CARD 2 -->
<div class="activity-card" data-name="burj khalifa 124" data-destination="dubai" data-adult-price="4499" data-child-price="2999">
<span class="badge">⭐ Most Loved</span>
<img src="burj khalifa.avif">
<div class="activity-info">
<h3>Burj Khalifa – 124th Floor</h3>
<p class="location">Dubai</p>
<div class="options">
<input type="date" class="booking-date">
<select class="duration"><option>Flexible</option></select>
</div>
<div class="guest-select">
<input type="number" class="adult-count" value="1" min="1">
<input type="number" class="child-count" value="0" min="0">
</div>
<div class="price-info">Adult ₹4,499 | Child ₹2,999</div>
<h3 class="total">₹<span class="total-price">4,499</span></h3>
<div class="btn-group">
<button class="pdf-btn">PDF</button>
<button class="book-btn">Book Now</button>
</div>
</div>
</div>

<div class="activity-card" data-name="miracle garden" data-destination="dubai" data-adult-price="2499" data-child-price="1999">
  <span class="badge">🌸 Seasonal Hit</span>
  <img src="Miracle Garden.jpg">

  <div class="activity-info">
    <h3>Dubai Miracle Garden</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Flexible</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹2,499 | Child ₹1,999</div>
    <h3 class="total">₹<span class="total-price">2,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="burj khalifa 148" data-destination="dubai" data-adult-price="12499" data-child-price="8999">
  <span class="badge">👑 Premium</span>
  <img src="burj khalifa.avif">

  <div class="activity-info">
    <h3>Burj Khalifa – 148th Floor</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Flexible</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹12,499 | Child ₹8,999</div>
    <h3 class="total">₹<span class="total-price">12,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="dubai city tour" data-destination="dubai" data-adult-price="3499" data-child-price="2499">
  <span class="badge">🚌 Best Value</span>
  <img src="dubai city tour.jpg">

  <div class="activity-info">
    <h3>Dubai City Tour</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Half Day</option>
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹3,499 | Child ₹2,499</div>
    <h3 class="total">₹<span class="total-price">3,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="abu dhabi city tour ferrari world" data-destination="abu-dhabi" data-adult-price="6999" data-child-price="4999">
  <span class="badge">🔥 Combo Deal</span>
  <img src="ferrari world.jpg">

  <div class="activity-info">
    <h3>Abu Dhabi City Tour + Ferrari World</h3>
    <p class="location">Abu Dhabi</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹6,999 | Child ₹4,999</div>
    <h3 class="total">₹<span class="total-price">6,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="yas island tour" data-destination="abu-dhabi" data-adult-price="3999" data-child-price="2999">
  <span class="badge">🏝 Island Tour</span>
  <img src="yas island.jpg">

  <div class="activity-info">
    <h3>Yas Island Tour</h3>
    <p class="location">Abu Dhabi</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Half Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹3,999 | Child ₹2,999</div>
    <h3 class="total">₹<span class="total-price">3,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="ferrari world" data-destination="abu-dhabi" data-adult-price="5999" data-child-price="4499">
  <span class="badge">🏎 Thrill Ride</span>
  <img src="ferrari world.jpg">

  <div class="activity-info">
    <h3>Ferrari World Abu Dhabi</h3>
    <p class="location">Abu Dhabi</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Flexible</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹5,999 | Child ₹4,499</div>
    <h3 class="total">₹<span class="total-price">5,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="aquaventure water park" data-destination="dubai" data-adult-price="6499" data-child-price="4999">
  <span class="badge">💦 Water Fun</span>
  <img src="aquaventure and lost chamber.jpg">

  <div class="activity-info">
    <h3>Aquaventure Water Park</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹6,499 | Child ₹4,999</div>
    <h3 class="total">₹<span class="total-price">6,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="lost chambers aquarium" data-destination="dubai" data-adult-price="3499" data-child-price="2499">
  <span class="badge">🐠 Family Favorite</span>
  <img src="lost chamber.avif">

  <div class="activity-info">
    <h3>Lost Chambers Aquarium</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Flexible</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹3,499 | Child ₹2,499</div>
    <h3 class="total">₹<span class="total-price">3,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="aquaventure lost chambers combo" data-destination="dubai" data-adult-price="8999" data-child-price="6999">
  <span class="badge">🔥 Combo Offer</span>
  <img src="aquaventure and lost chamber.jpg">

  <div class="activity-info">
    <h3>Aquaventure + Lost Chambers Combo</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹8,999 | Child ₹6,999</div>
    <h3 class="total">₹<span class="total-price">8,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="dubai parks and resorts" data-destination="dubai" data-adult-price="5999" data-child-price="4499">
  <span class="badge">🎢 Theme Park</span>
  <img src="dubai parks.jpg">

  <div class="activity-info">
    <h3>Dubai Parks & Resorts</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹5,999 | Child ₹4,499</div>
    <h3 class="total">₹<span class="total-price">5,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="louvre abu dhabi" data-destination="abu-dhabi" data-adult-price="2999" data-child-price="1999">
  <span class="badge">🖼 Culture</span>
  <img src="louvre museum.avif">

  <div class="activity-info">
    <h3>Louvre Abu Dhabi</h3>
    <p class="location">Abu Dhabi</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Flexible</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹2,999 | Child ₹1,999</div>
    <h3 class="total">₹<span class="total-price">2,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="global village" data-destination="dubai" data-adult-price="1999" data-child-price="1499">
  <span class="badge">🎡 Night Attraction</span>
  <img src="global village.avif">

  <div class="activity-info">
    <h3>Global Village Dubai</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Evening</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹1,999 | Child ₹1,499</div>
    <h3 class="total">₹<span class="total-price">1,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="dubai dolphinarium" data-destination="dubai" data-adult-price="2499" data-child-price="1999">
  <span class="badge">🐬 Family Show</span>
  <img src="dubai dolphirium.jpg">

  <div class="activity-info">
    <h3>Dubai Dolphinarium</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Show Ticket</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹2,499 | Child ₹1,999</div>
    <h3 class="total">₹<span class="total-price">2,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="img worlds of adventure" data-destination="dubai" data-adult-price="5499" data-child-price="3999">
  <span class="badge">🎢 Indoor Theme Park</span>
  <img src="img world.jpg">

  <div class="activity-info">
    <h3>IMG Worlds of Adventure</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹5,499 | Child ₹3,999</div>
    <h3 class="total">₹<span class="total-price">5,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="warner bros world" data-destination="abu-dhabi" data-adult-price="5999" data-child-price="4499">
  <span class="badge">🎬 Hollywood Theme</span>
  <img src="warner bros.jpg">
  <div class="activity-info">
    <h3>Warner Bros. World Abu Dhabi</h3>
    <p class="location">Abu Dhabi</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹5,999 | Child ₹4,499</div>
    <h3 class="total">₹<span class="total-price">5,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="1 hour limousine ride dubai" data-destination="dubai" data-adult-price="9999" data-child-price="0">
  <span class="badge">💎 Luxury Ride</span>
  <img src="limosuine.jpg">

  <div class="activity-info">
    <h3>1 Hour Limousine Ride – Dubai</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>1 Hour</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0" readonly>
    </div>

    <div class="price-info">Per Ride ₹9,999 (Up to 8 Guests)</div>
    <h3 class="total">₹<span class="total-price">9,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="SKI DUBAI" data-destination="dubai" data-adult-price="9999" data-child-price="0">
  <span class="badge">💎 Luxury Ride</span>
  <img src="SKI DUBAI.jpg">

  <div class="activity-info">
    <h3>Ski Dubai</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>1 Hour</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0" readonly>
    </div>

    <div class="price-info">Per Ride ₹9,999 (Up to 8 Guests)</div>
    <h3 class="total">₹<span class="total-price">9,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="legoland water park" data-destination="dubai" data-adult-price="4499" data-child-price="3499">
  <span class="badge">🧱 Family Fun</span>
  <img src="leogoland.jpg">

  <div class="activity-info">
    <h3>LEGOLAND® Water Park</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹4,499 | Child ₹3,499</div>
    <h3 class="total">₹<span class="total-price">4,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>


<div class="activity-card" data-name="motiongate dubai" data-destination="dubai" data-adult-price="5499" data-child-price="3999">
  <span class="badge">🎬 Hollywood Rides</span>
  <img src="motiongate.jpg">

  <div class="activity-info">
    <h3>Motiongate™ Dubai</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹5,499 | Child ₹3,999</div>
    <h3 class="total">₹<span class="total-price">5,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="wild wadi waterpark" data-destination="dubai" data-adult-price="5999" data-child-price="4499">
  <span class="badge">🌊 Iconic Waterpark</span>
  <img src="wild wadi.jpg">

  <div class="activity-info">
    <h3>Wild Wadi Waterpark</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Full Day</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹5,999 | Child ₹4,499</div>
    <h3 class="total">₹<span class="total-price">5,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="dubai garden glow" data-destination="dubai" data-adult-price="1999" data-child-price="1499">
  <span class="badge">✨ Night Attraction</span>
  <img src="dubai glow garden.jpg">

  <div class="activity-info">
    <h3>Dubai Garden Glow</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Evening</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹1,999 | Child ₹1,499</div>
    <h3 class="total">₹<span class="total-price">1,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="skydive dubai" data-destination="dubai" data-adult-price="39999" data-child-price="0">
  <span class="badge">🪂 Ultimate Thrill</span>
  <img src="ski diving.jpg">

  <div class="activity-info">
    <h3>Skydive Dubai</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Experience</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0" readonly>
    </div>

    <div class="price-info">Per Person ₹39,999</div>
    <h3 class="total">₹<span class="total-price">39,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="hot air balloon dubai" data-destination="dubai" data-adult-price="19999" data-child-price="0">
  <span class="badge">🎈 Sunrise Experience</span>
  <img src="hot air.jpg">

  <div class="activity-info">
    <h3>Hot Air Ballooning – Dubai</h3>
    <p class="location">Dubai Desert</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>Morning</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0" readonly>
    </div>

    <div class="price-info">Per Person ₹19,999</div>
    <h3 class="total">₹<span class="total-price">19,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="helicopter tour dubai" data-destination="dubai" data-adult-price="15999" data-child-price="9999">
  <span class="badge">🚁 Aerial View</span>
  <img src="helicopter tour.jpg">

  <div class="activity-info">
    <h3>Helicopter Tour – Dubai</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>12 Minutes</option>
        <option>17 Minutes</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹15,999 | Child ₹9,999</div>
    <h3 class="total">₹<span class="total-price">15,999</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>

<div class="activity-card" data-name="ifly dubai" data-destination="dubai" data-adult-price="4499" data-child-price="3499">
  <span class="badge">🌀 Indoor Skydiving</span>
  <img src="ifly.jpg">

  <div class="activity-info">
    <h3>iFly Dubai</h3>
    <p class="location">Dubai</p>

    <div class="options">
      <input type="date" class="booking-date">
      <select class="duration">
        <option>2 Flights</option>
      </select>
    </div>

    <div class="guest-select">
      <input type="number" class="adult-count" value="1" min="1">
      <input type="number" class="child-count" value="0" min="0">
    </div>

    <div class="price-info">Adult ₹4,499 | Child ₹3,499</div>
    <h3 class="total">₹<span class="total-price">4,499</span></h3>

    <div class="btn-group">
      <button class="pdf-btn">PDF</button>
      <button class="book-btn">Book Now</button>
    </div>
  </div>
</div>


</div>
<p id="noResults">No activities found 😕</p>
</div>
</section>

<section class="section trust">
<div class="container">
<h2>Why Book With ExploreFun ✨</h2>
<div class="trust-grid">
<div class="trust-card">💳 Secure Razorpay Payments</div>
<div class="trust-card">⚡ Instant Confirmation</div>
<div class="trust-card">💸 Best Price Guarantee</div>
</div>
</div>
</section>

<footer>
<div class="footer-container">
<div>
<h4>ExploreFun</h4>
<p>Book experiences worldwide</p>
</div>
</div>
</footer>

<script>
/* PRICE + PAYMENT */
document.querySelectorAll(".activity-card").forEach(card=>{
  const a=card.querySelector(".adult-count");
  const c=card.querySelector(".child-count");
  const t=card.querySelector(".total-price");
  const d=card.querySelector(".booking-date");
  const btn=card.querySelector(".book-btn");
  const ap=+card.dataset.adultPrice;
  const cp=+card.dataset.childPrice;

  function calc(){
    const total=(a.value*ap)+(c.value*cp);
    t.textContent=total.toLocaleString("en-IN");
    return total;
  }
  a.oninput=c.oninput=calc;

  btn.onclick=()=>{
    if(!d.value){alert("Select booking date");return;}
    const amt=calc();
    new Razorpay({
      key:"rzp_test_XXXXXXXXXX",
      amount:amt*100,
      currency:"INR",
      name:"ExploreFun",
      description:card.dataset.name,
      handler:r=>alert("Payment Success 🎉\n"+r.razorpay_payment_id)
    }).open();
  };
});

/* 🔍 SMART SEARCH */
const search=document.getElementById("searchInput");
const cards=document.querySelectorAll(".activity-card");
const no=document.getElementById("noResults");

search.addEventListener("input",()=>{
  const q=search.value.toLowerCase().trim();
  let found=0;

  cards.forEach(card=>{
    const name=card.dataset.name.toLowerCase();
    const dest=card.dataset.destination.toLowerCase();
    if(name.includes(q)||dest.includes(q)){
      card.style.display="block";
      found++;
    }else{
      card.style.display="none";
    }
  });

  no.style.display=found?"none":"block";
});
</script>

</body>
</html>

