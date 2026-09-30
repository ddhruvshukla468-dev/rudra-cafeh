<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rudra Cafe</title>

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:Arial,sans-serif;
}

body{
  background:#fff8f1;
  color:#222;
}

header{
  background:#111;
  color:white;
  padding:16px 6%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  position:sticky;
  top:0;
  z-index:100;
}

.logo{
  font-size:24px;
  font-weight:bold;
  color:#ff9f1c;
}

.cart-btn{
  background:#ff7a00;
  color:white;
  border:0;
  padding:11px 17px;
  border-radius:25px;
  font-weight:bold;
  cursor:pointer;
}

.hero{
  min-height:70vh;
  display:flex;
  align-items:center;
  padding:60px 7%;
  color:white;
  background:
  linear-gradient(90deg,rgba(0,0,0,.9),rgba(0,0,0,.35)),
  url("https://images.unsplash.com/photo-1513104890138-7c749659a591?auto=format&fit=crop&w=1600&q=80");
  background-size:cover;
  background-position:center;
}

.hero-content{
  max-width:650px;
}

.hero h1{
  font-size:clamp(45px,8vw,78px);
  line-height:1;
  margin:15px 0;
}

.hero p{
  font-size:19px;
  margin-bottom:25px;
  color:#eee;
}

.badge{
  display:inline-block;
  background:#ff9f1c;
  color:#111;
  padding:7px 14px;
  border-radius:20px;
  font-weight:bold;
}

.btn{
  display:inline-block;
  text-decoration:none;
  background:#25d366;
  color:white;
  padding:14px 22px;
  border-radius:10px;
  font-weight:bold;
}

section{
  padding:60px 6%;
}

.title{
  text-align:center;
  font-size:38px;
  margin-bottom:10px;
}

.subtitle{
  text-align:center;
  color:#777;
  margin-bottom:35px;
}

.categories{
  display:flex;
  justify-content:center;
  gap:12px;
  flex-wrap:wrap;
  margin-bottom:35px;
}

.category{
  border:0;
  background:white;
  padding:12px 20px;
  border-radius:25px;
  cursor:pointer;
  font-weight:bold;
  box-shadow:0 3px 12px #0001;
}

.category.active{
  background:#ff7a00;
  color:white;
}

.products{
  max-width:1100px;
  margin:auto;
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(230px,1fr));
  gap:22px;
}

.product{
  background:white;
  border-radius:18px;
  overflow:hidden;
  box-shadow:0 5px 22px #00000012;
}

.product img{
  width:100%;
  height:190px;
  object-fit:cover;
}

.product-info{
  padding:20px;
}

.product h3{
  font-size:22px;
  margin-bottom:7px;
}

.product p{
  color:#777;
  margin-bottom:15px;
}

.product-bottom{
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.price{
  font-weight:bold;
  color:#e86600;
}

.add{
  border:0;
  background:#111;
  color:white;
  padding:10px 15px;
  border-radius:8px;
  cursor:pointer;
}

.about{
  background:#111;
  color:white;
  text-align:center;
}

.about p{
  max-width:650px;
  margin:15px auto 0;
  color:#ddd;
}

.contact{
  max-width:900px;
  margin:auto;
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:18px;
}

.contact-box{
  background:white;
  padding:25px;
  text-align:center;
  border-radius:15px;
  box-shadow:0 5px 18px #0001;
}

.contact-box h3{
  margin-bottom:8px;
}

.contact-box a{
  color:#e86600;
  text-decoration:none;
  font-weight:bold;
}

footer{
  background:#111;
  color:#aaa;
  text-align:center;
  padding:22px;
}

/* CART */

.cart{
  position:fixed;
  right:-420px;
  top:0;
  width:min(400px,100%);
  height:100vh;
  background:white;
  z-index:200;
  box-shadow:-5px 0 25px #0003;
  padding:25px;
  transition:.3s;
  overflow:auto;
}

.cart.open{
  right:0;
}

.cart-header{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:25px;
}

.close{
  border:0;
  background:#eee;
  width:35px;
  height:35px;
  border-radius:50%;
  cursor:pointer;
}

.cart-item{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:15px 0;
  border-bottom:1px solid #eee;
}

.qty button{
  border:0;
  width:28px;
  height:28px;
  cursor:pointer;
}

.cart-total{
  font-size:22px;
  font-weight:bold;
  margin:25px 0;
}

.whatsapp{
  display:block;
  text-align:center;
  background:#25d366;
  color:white;
  text-decoration:none;
  padding:15px;
  border-radius:10px;
  font-weight:bold;
}

@media(max-width:600px){
  header{
    padding:15px 5%;
  }

  .hero{
    padding:55px 5%;
  }

  section{
    padding:50px 5%;
  }

  .title{
    font-size:31px;
  }
}
</style>
</head>

<body>

<header>
  <div class="logo">🍕 Rudra Cafe</div>

  <button class="cart-btn" onclick="openCart()">
    🛒 Cart (<span id="cartCount">0</span>)
  </button>
</header>


<section class="hero">

  <div class="hero-content">

    <span class="badge">🔥 Fresh • Hot • Delicious</span>

    <h1>Good Food.<br>Good Mood.</h1>

    <p>
      Pizza, Biryani, Burgers and delicious snacks —
      made fresh at Rudra Cafe.
    </p>

    <a class="btn" href="#menu">
      Explore Menu
    </a>

  </div>

</section>


<section id="menu">

<h2 class="title">Our Menu</h2>

<p class="subtitle">
Choose your favourite food
</p>


<div class="categories">

<button class="category active" onclick="filterMenu('all',this)">
All
</button>

<button class="category" onclick="filterMenu('pizza',this)">
🍕 Pizza
</button>

<button class="category" onclick="filterMenu('biryani',this)">
🍛 Biryani
</button>

<button class="category" onclick="filterMenu('burger',this)">
🍔 Burgers
</button>

<button class="category" onclick="filterMenu('snacks',this)">
🍟 Snacks
</button>

</div>


<div class="products">


<div class="product" data-category="pizza">

<img src="https://images.unsplash.com/photo-1574071318508-1cdbab80d002?auto=format&fit=crop&w=800&q=80">

<div class="product-info">

<h3>Cheesy Pizza</h3>

<p>Hot and loaded with cheese.</p>

<div class="product-bottom">

<span class="price">₹ --</span>

<button class="add" onclick="addItem('Cheesy Pizza')">
Add +
</button>

</div>

</div>
</div>


<div class="product" data-category="pizza">

<img src="https://images.unsplash.com/photo-1579751626657-72bc17010498?auto=format&fit=crop&w=800&q=80">

<div class="product-info">

<h3>Special Pizza</h3>

<p>Our delicious special pizza.</p>

<div class="product-bottom">

<span class="price">₹ --</span>

<button class="add" onclick="addItem('Special Pizza')">
Add +
</button>

</div>

</div>
</div>


<div class="product" data-category="biryani">

<img src="https://images.unsplash.com/photo-1563379091339-03246963d96c?auto=format&fit=crop&w=800&q=80">

<div class="product-info">

<h3>Special Biryani</h3>

<p>Fragrant and full of flavour.</p>

<div class="product-bottom">

<span class="price">₹ --</span>

<button class="add" onclick="addItem('Special Biryani')">
Add +
</button>

</div>

</div>
</div>


<div class="product" data-category="burger">

<img src="https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&w=800&q=80">

<div class="product-info">

<h3>Classic Burger</h3>

<p>Juicy, tasty and satisfying.</p>

<div class="product-bottom">

<span class="price">₹ --</span>

<button class="add" onclick="addItem('Classic Burger')">
Add +
</button>

</div>

</div>
</div>


<div class="product" data-category="snacks">

<img src="https://images.unsplash.com/photo-1573080496219-bb080dd4f877?auto=format&fit=crop&w=800&q=80">

<div class="product-info">

<h3>French Fries</h3>

<p>Crispy and golden.</p>

<div class="product-bottom">

<span class="price">₹ --</span>

<button class="add" onclick="addItem('French Fries')">
Add +
</button>

</div>

</div>
</div>


<div class="product" data-category="snacks">

<img src="https://images.unsplash.com/photo-1521305916504-4a1121188589?auto=format&fit=crop&w=800&q=80">

<div class="product-info">

<h3>Special Snacks</h3>

<p>Perfect for a quick bite.</p>

<div class="product-bottom">

<span class="price">₹ --</span>

<button class="add" onclick="addItem('Special Snacks')">
Add +
</button>

</div>

</div>
</div>

</div>

</section>


<section class="about">

<h2 class="title">About Rudra Cafe</h2>

<p>
Welcome to Rudra Cafe. We serve delicious pizza,
biryani, burgers and snacks with fresh ingredients
and great taste.
</p>

</section>


<section id="contact">

<h2 class="title">Contact Us</h2>

<p class="subtitle">Come visit us or order on WhatsApp</p>

<div class="contact">

<div class="contact-box">
<h3>📍 Location</h3>
<p>Near Raj Khoot Hotel</p>
</div>

<div class="contact-box">
<h3>📱 WhatsApp</h3>
<a href="https://wa.me/918810964090">
8810964090
</a>
</div>

<div class="contact-box">
<h3>🍽️ Food</h3>
<p>Pizza • Biryani • Burgers • Snacks</p>
</div>

</div>

</section>


<footer>
© 2026 Rudra Cafe • All Rights Reserved
</footer>


<!-- CART -->

<div class="cart" id="cart">

<div class="cart-header">

<h2>Your Cart</h2>

<button class="close" onclick="closeCart()">✕</button>

</div>

<div id="cartItems"></div>

<div class="cart-total">
Items: <span id="totalItems">0</span>
</div>

<a id="orderButton"
class="whatsapp"
href="#"
target="_blank">
📱 Order on WhatsApp
</a>

</div>


<script>

let cart = {};


function addItem(name){

  if(cart[name]){
    cart[name]++;
  }else{
    cart[name]=1;
  }

  updateCart();

}


function removeItem(name){

  if(cart[name]){
    cart[name]--;

    if(cart[name]<=0){
      delete cart[name];
    }
  }

  updateCart();

}


function updateCart(){

  const container=document.getElementById("cartItems");

  container.innerHTML="";

  let total=0;

  Object.keys(cart).forEach(name=>{

    let quantity=cart[name];

    total+=quantity;

    container.innerHTML+=`

      <div class="cart-item">

        <strong>${name}</strong>

        <div class="qty">

          <button onclick="removeItem('${name}')">
          −
          </button>

          ${quantity}

          <button onclick="addItem('${name}')">
          +
          </button>

        </div>

      </div>

    `;

  });


  document.getElementById("cartCount").innerText=total;

  document.getElementById("totalItems").innerText=total;


  let message="Hello Rudra Cafe!%0A%0AI want to order:%0A";

  Object.keys(cart).forEach(name=>{

    message+=
    encodeURIComponent(name)
    +" x "
    +cart[name]
    +"%0A";

  });


  document.getElementById("orderButton").href=
  "https://wa.me/918810964090?text="+message;

}


function openCart(){

  document.getElementById("cart").classList.add("open");

}


function closeCart(){

  document.getElementById("cart").classList.remove("open");

}


function filterMenu(category,button){

  document.querySelectorAll(".category")
  .forEach(b=>b.classList.remove("active"));

  button.classList.add("active");


  document.querySelectorAll(".product")
  .forEach(product=>{

    if(
      category==="all" ||
      product.dataset.category===category
    ){
      product.style.display="block";
    }else{
      product.style.display="none";
    }

  });

}

</script>

</body>
</html>