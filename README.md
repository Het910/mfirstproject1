<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Luxe Design</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            color: #333;
            background: url('background.jpg') no-repeat center center fixed;
            background-size: cover;
        }
        header {
            background: rgba(244, 244, 244, 0.8);
            padding: 20px 0;
            text-align: center;
        }
        header h1 {
            margin-bottom: 10px;
            font-size: 2.5em;
        }
        header p {
            font-size: 1.2em;
            color: #555;
        }
        .section {
            margin: 40px auto;
            text-align: center;
            padding: 20px;
        }
        .section h2 {
            font-size: 2em;
            margin-bottom: 10px;
        }
        .products {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            padding: 20px;
        }
        .product {
            border: 1px solid #ddd;
            border-radius: 8px;
            background: #fff;
            text-align: center;
            padding: 10px;
        }
        .product img {
            width: 100%;
            border-radius: 8px;
        }
        .product button {
            display: block;
            margin: 10px auto;
            padding: 10px 15px;
            background-color: #333;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .product button:hover {
            background-color: #555;
        }
        .cart {
            margin: 20px;
            text-align: center;
        }
        .cart-items {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        footer {
            background: #222;
            color: #fff;
            padding: 20px 0;
            text-align: center;
        }
        footer p {
            margin-bottom: 10px;
        }
        footer a {
            color: #1e90ff;
            text-decoration: none;
        }
        footer a:hover {
            text-decoration: underline;
        }
        .payment-form {
            margin: 20px auto;
            padding: 20px;
            max-width: 400px;
            background: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        .payment-form h2 {
            margin-bottom: 20px;
            text-align: center;
        }
        .payment-form label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }
        .payment-form input {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        .payment-form button {
            width: 100%;
            padding: 10px;
            background-color: #333;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .payment-form button:hover {
            background-color: #555;
        }
    </style>
    <script>
        const cart = [];

        function addToCart(product) {
            cart.push(product);
            alert(product + ' has been added to your cart!');
        }

        function viewCart() {
            let cartContent = '<h2>Your Cart</h2><ul>';
            cart.forEach(item => {
                cartContent += '<li>' + item + '</li>';
            });
            cartContent += '</ul>';
            cartContent += '<button onclick="showPaymentForm()">Proceed to Payment</button>';
            document.getElementById('cart').innerHTML = cartContent;
        }

        function showPaymentForm() {
            document.getElementById('payment-form').style.display = 'block';
            document.getElementById('cart').style.display = 'none';

            let cartSummary = '<h3>Order Summary</h3><ul>';
            cart.forEach(item => {
                cartSummary += '<li>' + item + '</li>';
            });
            cartSummary += '</ul>';
            document.getElementById('order-summary').innerHTML = cartSummary;
        }
    </script>
</head>
<body>

<header>
    <h1>Luxe Design</h1>
    <p>Quick and hassle-free shopping | An extension of your closet</p>
</header>

<section class="section">
    <h2>Clothes for Her</h2>
    <div class="products">
        <div class="product">
            <img src="C:\Users\Het\Desktop\website design\dress1.jpg" alt="Dress 1">
            <p>Elegant Red Dress</p>
            <button onclick="addToCart('Elegant Red Dress')">Add to Cart</button>
        </div>
        <div class="product">
            <img src="‪‪C:\Users\Het\Desktop\website design\dress2.jpg" alt="Dress 2">
            <p>Classic Black Dress</p>
            <button onclick="addToCart('Classic Black Dress')">Add to Cart</button>
        </div>
    </div>
</section>

<section class="section">
    <h2>Clothes for Him</h2>
    <div class="products">
        <div class="product">
            <img src="C:\Users\Het\Desktop\website design\mendress1.jpg" alt="Shirt 1">
            <p>Formal White Shirt</p>
            <button onclick="addToCart('Formal White Shirt')">Add to Cart</button>
        </div>
        <div class="product">
            <img src="C:\Users\Het\Desktop\website design\mendress2.jpg" alt="Jacket 1">
            <p>Leather Jacket</p>
            <button onclick="addToCart('Leather Jacket')">Add to Cart</button>
        </div>
    </div>
</section>

<section class="cart">
    <button onclick="viewCart()">View Cart</button>
    <div id="cart"></div>
</section>

<div id="payment-form" class="payment-form" style="display:none;">
    <h2>Payment Details</h2>
    <div id="order-summary"></div>
    <form>
        <label for="name">Name</label>
        <input type="text" id="name" name="name" required>

        <label for="surname">Surname</label>
        <input type="text" id="surname" name="surname" required>

        <label for="dob">Date of Birth</label>
        <input type="date" id="dob" name="dob" required>

        <label for="phone">Phone Number</label>
        <input type="tel" id="phone" name="phone" required>

        <label for="card">Card Details</label>
        <input type="text" id="card" name="card" placeholder="Card Number" required>

        <button type="submit">Pay Now</button>
    </form>
</div>

<footer>
    <p>Follow us: 
        <a href="#">Instagram</a> | 
        <a href="#">Facebook</a> | 
        <a href="#">Twitter</a>
    </p>
    <p>Contact us: (123) 456-7890 | Luxedesign2342@gmail.com</p>
    <p>Address: 246, Down Street, Near Starbucks, 4th Lane, UK</p>
</footer>

</body>
</html>
