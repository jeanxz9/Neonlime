<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>EcoPhone Case Shop</title>
  <style>
    body { font-family: 'Arial'; background: #f2f2f2; margin: 0; padding: 0; }
    header { background: #4CAF50; color: white; padding: 20px; text-align: center; }
    .container { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; padding: 20px; }
    .product { background: white; padding: 15px; border-radius: 8px; box-shadow: 0 0 10px #ccc; text-align: center; }
    .product img { width: 100%; border-radius: 8px; }
    button { background: #4CAF50; color: white; padding: 10px 15px; border: none; border-radius: 5px; cursor: pointer; margin-top: 10px; }
    #cart { position: fixed; top: 20px; right: 20px; background: white; padding: 15px; border: 1px solid #ddd; border-radius: 8px; }
  </style>
</head>
<body>

<header>
  <h1>EcoPhone Case Shop</h1>
  <p>Custodie Biodegradabili per Smartphone - Proteggi il tuo telefono e il pianeta!</p>
</header>

<div class="container">
  <div class="product">
    <img src="https://via.placeholder.com/300x200?text=Custodia+Eco" alt="Custodia Eco">
    <h3>Custodia Eco Verde</h3>
    <p>€14.99</p>
    <button onclick="addToCart('Custodia Eco Verde', 14.99)">Aggiungi al carrello</button>
  </div>
  <div class="product">
    <img src="https://via.placeholder.com/300x200?text=Custodia+Nera" alt="Custodia Nera">
    <h3>Custodia Eco Nera</h3>
    <p>€14.99</p>
    <button onclick="addToCart('Custodia Eco Nera', 14.99)">Aggiungi al carrello</button>
  </div>
</div>

<div id="cart">
  <h3>Carrello</h3>
  <ul id="cart-items"></ul>
  <p><strong>Totale: €<span id="total">0.00</span></strong></p>
  <form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_blank">
    <input type="hidden" name="cmd" value="_cart">
    <input type="hidden" name="business" value="la-tua-email-paypal@example.com">
    <input type="hidden" name="currency_code" value="EUR">
    <input type="hidden" id="paypal-items" name="upload" value="1">
    <button type="submit">Checkout con PayPal</button>
  </form>
</div>

<script>
  let cart = [];
  function addToCart(name, price) {
    cart.push({name, price});
    updateCart();
  }
  function updateCart() {
    const cartList = document.getElementById('cart-items');
    const totalSpan = document.getElementById('total');
    let total = 0;
    cartList.innerHTML = '';
    cart.forEach(item => {
      const li = document.createElement('li');
      li.textContent = `${item.name} - €${item.price.toFixed(2)}`;
      cartList.appendChild(li);
      total += item.price;
    });
    totalSpan.textContent = total.toFixed(2);
  }
</script>

</body>
</html># Neonlime
