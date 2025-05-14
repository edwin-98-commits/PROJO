index.html and style.css.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Your One-Stop Shop</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>🚀 Whatever You Need is Right Here!</h1>
    <nav>
      <ul>
        <li><a href="#">Shop</a></li>
        <li><a href="#">Reviews</a></li>
        <li><a href="#">Cart 🛒 (<span id="cart-count">0</span>)</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section class="product-list">
      <div class="product" data-name="Smart Gadget" data-price="49.99">
        <h2>Smart Gadget</h2>
        <p>$49.99</p>
        <button class="add-to-cart">Add to Cart</button>
      </div>
      <div class="product" data-name="Time Saver Pro" data-price="89.99">
        <h2>Time Saver Pro</h2>
        <p>$89.99</p>
        <button class="add-to-cart">Add to Cart</button>
      </div>
    </section>

    <section class="cart">
      <h2>Your Cart</h2>
      <ul id="cart-items"></ul>
      <p>Total: $<span id="total-price">0.00</span></p>
    </section>
  </main>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: 'Segoe UI', sans-serif;
  margin: 0;
  padding: 0;
  background: #f3f4f6;
  color: #333;
}

header {
  background-color: #4f46e5;
  color: white;
  padding: 1em;
  text-align: center;
}

nav ul {
  list-style: none;
  display: flex;
  justify-content: center;
  gap: 2rem;
  padding: 0;
}

nav a {
  color: white;
  text-decoration: none;
}

.product-list {
  display: flex;
  justify-content: space-around;
  padding: 2em;
}

.product {
  background: white;
  padding: 1em;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

button.add-to-cart {
  background-color: #10b981;
  color: white;
  border: none;
  padding: 0.5em 1em;
  margin-top: 1em;
  cursor: pointer;
  border-radius: 5px;
}

.cart {
  background: #fff;
  padding: 1em;
  margin: 2em auto;
  width: 80%;
  max-width: 600px;
  border-radius: 8px;
  box-shadow: 0 0 10px #ccc;
}
const cartItems = [];
const cartList = document.getElementById('cart-items');
const totalPriceEl = document.getElementById('total-price');
const cartCountEl = document.getElementById('cart-count');

document.querySelectorAll('.add-to-cart').forEach(button => {
  button.addEventListener('click', () => {
    const product = button.closest('.product');
    const name = product.dataset.name;
    const price = parseFloat(product.dataset.price);

    cartItems.push({ name, price });
    updateCart();
  });
});

function updateCart() {
  cartList.innerHTML = '';
  let total = 0;

  cartItems.forEach(item => {
    const li = document.createElement('li');
    li.textContent = `${item.name} - $${item.price.toFixed(2)}`;
    cartList.appendChild(li);
    total += item.price;
  });

  totalPriceEl.textContent = total.toFixed(2);
  cartCountEl.textContent = cartItems.length;
}


