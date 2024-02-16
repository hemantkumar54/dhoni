 <html>
<html>
<head>
<title>Shopping Cart</title>
<style>
        /* Add your CSS styles here */
    </style>
</head>
<body>
    <h1>My Shopping Cart</h1>
    <div id="cart">
        <!-- Cart items will be displayed here -->
    </div>
    <button onclick="addToCart('Product A', 2000)">Add Product A (Rs. 2000)</button>
    <button onclick="addToCart('Product B', 3500)">Add Product B (Rs. 3500)</button>
    <button onclick="calculateTotal()">Calculate Total</button>
    <p id="totalPrice"></p>

    <script>
        const cart = [];
        let total = 0;

        function addToCart(productName, price) {
            cart.push({ name: productName, price: price });
        }

        function calculateTotal() {
            total = cart.reduce((acc, item) => acc + item.price, 0);
            if (total > 5000) {
                const discountedTotal = total * 0.9;
                document.getElementById('totalPrice').textContent = `Total Price (with 10% discount): Rs. ${discountedTotal.toFixed(2)}`;
            } else {
                document.getElementById('totalPrice').textContent = `Original Total Price: Rs. ${total.toFixed(2)}`;
            }
        }
    </script>
</body>
</html>
