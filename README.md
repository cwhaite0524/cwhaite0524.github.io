<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crust & Co</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #f4f4f4;
            padding: 1rem;
            text-align: center;
        }
        nav {
            background-color: #333;
            color: #fff;
            padding: 0.5rem;
        }
        nav ul {
            list-style-type: none;
            padding: 0;
        }
        nav ul li {
            display: inline;
            margin-right: 10px;
        }
        nav ul li a {
            color: #fff;
            text-decoration: none;
            cursor: pointer;
        }
        .container {
            width: 80%;
            margin: auto;
            overflow: hidden;
            padding: 20px;
        }
        .menu-item {
            border: 1px solid #ddd;
            padding: 15px;
            margin-bottom: 20px;
            border-radius: 8px;
            display: flex;
            gap: 20px;
            align-items: center;
        }
        .menu-item img {
            width: 200px;
            height: 150px;
            object-fit: cover;
            border-radius: 4px;
        }
        .menu-item-content {
            flex: 1;
        }
        .menu-item-content h4 {
            margin-top: 0;
            color: #333;
        }
        .menu-item button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .menu-item button:hover {
            background-color: #45a049;
        }
        form {
            background-color: #f4f4f4;
            padding: 20px;
            border-radius: 8px;
        }
        input[type="text"], input[type="email"], select {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        input[type="submit"] {
            background-color: #4CAF50;
            color: #fff;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .page {
            display: none;
        }
        .page.active {
            display: block;
        }
        #cart {
            background-color: #f9f9f9;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
        }
        #cart-items {
            list-style: none;
            padding: 0;
        }
        #cart-items li {
            padding: 10px;
            border-bottom: 1px solid #ddd;
        }
    </style>
</head>
<body>
    <header>
        <h1>Crust & Co</h1>
    </header>
    <nav>
        <ul>
            <li><a onclick="showPage('home')">Home</a></li>
            <li><a onclick="showPage('menu')">Menu</a></li>
            <li><a onclick="showPage('info')">Store Info</a></li>
        </ul>
    </nav>

    <div class="container">
        <div id="home" class="page active">
            <h2>Welcome to Crust & Co</h2>
            <p>Delicious pizzas available for pickup and delivery. Explore our menu and place your order today!</p>
            <img src="/api/placeholder/800/400" alt="Pizza restaurant interior" style="width: 100%; border-radius: 8px;">
        </div>

        <div id="menu" class="page">
            <h2>Our Menu</h2>
            <div id="pizza-menu">
                <h3>Pizzas</h3>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="Margherita Pizza">
                    <div class="menu-item-content">
                        <h4>Margherita</h4>
                        <p>Classic tomato sauce, mozzarella, and basil</p>
                        <button onclick="addToCart('Margherita', 12)">Add to Cart - $12</button>
                    </div>
                </div>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="Pepperoni Pizza">
                    <div class="menu-item-content">
                        <h4>Pepperoni</h4>
                        <p>Tomato sauce, mozzarella, and pepperoni</p>
                        <button onclick="addToCart('Pepperoni', 14)">Add to Cart - $14</button>
                    </div>
                </div>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="Vegetarian Pizza">
                    <div class="menu-item-content">
                        <h4>Vegetarian</h4>
                        <p>Tomato sauce, mozzarella, bell peppers, onions, and mushrooms</p>
                        <button onclick="addToCart('Vegetarian', 13)">Add to Cart - $13</button>
                    </div>
                </div>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="Hawaiian Pizza">
                    <div class="menu-item-content">
                        <h4>Hawaiian</h4>
                        <p>Tomato sauce, mozzarella, ham, and pineapple</p>
                        <button onclick="addToCart('Hawaiian', 15)">Add to Cart - $15</button>
                    </div>
                </div>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="BBQ Chicken Pizza">
                    <div class="menu-item-content">
                        <h4>BBQ Chicken</h4>
                        <p>BBQ sauce, mozzarella, grilled chicken, and red onions</p>
                        <button onclick="addToCart('BBQ Chicken', 16)">Add to Cart - $16</button>
                    </div>
                </div>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="Supreme Pizza">
                    <div class="menu-item-content">
                        <h4>Supreme</h4>
                        <p>Tomato sauce, mozzarella, pepperoni, sausage, bell peppers, onions, and olives</p>
                        <button onclick="addToCart('Supreme', 17)">Add to Cart - $17</button>
                    </div>
                </div>
            </div>
            
            <div id="drinks-menu">
                <h3>Soft Drinks</h3>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="Cola">
                    <div class="menu-item-content">
                        <h4>Cola</h4>
                        <button onclick="addToCart('Cola', 2)">Add to Cart - $2</button>
                    </div>
                </div>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="Lemon-Lime Soda">
                    <div class="menu-item-content">
                        <h4>Lemon-Lime Soda</h4>
                        <button onclick="addToCart('Lemon-Lime Soda', 2)">Add to Cart - $2</button>
                    </div>
                </div>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="Orange Soda">
                    <div class="menu-item-content">
                        <h4>Orange Soda</h4>
                        <button onclick="addToCart('Orange Soda', 2)">Add to Cart - $2</button>
                    </div>
                </div>
            </div>
            
            <div id="special-menu">
                <h3>Special</h3>
                <div class="menu-item">
                    <img src="/api/placeholder/200/150" alt="Family Meal Deal">
                    <div class="menu-item-content">
                        <h4>Family Meal Deal</h4>
                        <p>2 large pizzas, 4 soft drinks, and a dozen donuts</p>
                        <button onclick="addToCart('Family Meal Deal', 40)">Add to Cart - $40</button>
                    </div>
                </div>
            </div>
        </div>

        <div id="info" class="page">
            <h2>Store Information</h2>
            <p>Address: 123 Pizza Street, Pizzaville, PZ 12345</p>
            <p>Phone: (555) 123-4567</p>
            <p>Hours: Mon-Sun 11:00 AM - 10:00 PM</p>
            
            <h3>Checkout</h3>
            <div id="cart">
                <h4>Your Cart</h4>
                <ul id="cart-items"></ul>
                <p>Total: $<span id="cart-total">0</span></p>
            </div>
            
            <form id="order-form">
                <h4>Order Details</h4>
                <input type="text" id="name" placeholder="Your Name" required>
                <input type="email" id="email" placeholder="Your Email" required>
                <input type="text" id="phone" placeholder="Your Phone Number" required>
                <input type="text" id="address" placeholder="Delivery Address">
                <select id="order-type" required>
                    <option value="">Select Order Type</option>
                    <option value="delivery">Delivery</option>
                    <option value="pickup">Pickup</option>
                </select>
                <input type="submit" value="Place Order">
            </form>
        </div>
    </div>

    <script>
        let cart = [];
        
        function showPage(pageId) {
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            
            // Show the selected page
            document.getElementById(pageId).classList.add('active');
        }
        
        function addToCart(item, price) {
            cart.push({item, price});
            updateCart();
        }
        
        function updateCart() {
            const cartItems = document.getElementById('cart-items');
            const cartTotal = document.getElementById('cart-total');
            
            cartItems.innerHTML = '';
            let total = 0;
            
            cart.forEach(item => {
                const li = document.createElement('li');
                li.textContent = `${item.item} - $${item.price}`;
                cartItems.appendChild(li);
                total += item.price;
            });
            
            cartTotal.textContent = total;
        }
        
        document.getElementById('order-form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Order placed successfully!');
        });
    </script>
</body>
</html>
