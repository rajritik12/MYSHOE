##### document.addEventListener('DOMContentLoaded', () => {

##### &nbsp;   const cartIcon = document.getElementById('cart-icon');

##### &nbsp;   const cartModal = document.getElementById('cart-modal');

##### &nbsp;   const cartItems = document.getElementById('cart-items');

##### &nbsp;   const cartTotal = document.getElementById('cart-total');

##### &nbsp;   const cartCount = document.getElementById('cart-count');

##### &nbsp;   const closeCart = document.getElementById('close-cart');

##### &nbsp;   const checkout = document.getElementById('checkout');

##### &nbsp;   const addToCartButtons = document.querySelectorAll('.add-to-cart');

##### 

##### &nbsp;   let cart = \[];

##### &nbsp;   let total = 0;

##### 

##### &nbsp;   // Add to cart

##### &nbsp;   addToCartButtons.forEach(button => {

##### &nbsp;       button.addEventListener('click', (e) => {

##### &nbsp;           const card = e.target.closest('.product-card');

##### &nbsp;           const name = card.querySelector('h3').textContent;

##### &nbsp;           const price = parseFloat(card.dataset.price);

##### &nbsp;           cart.push({ name, price });

##### &nbsp;           total += price;

##### &nbsp;           updateCart();

##### &nbsp;           // Animate button

##### &nbsp;           e.target.style.transform = 'scale(1.1)';

##### &nbsp;           setTimeout(() => e.target.style.transform = 'scale(1)', 200);

##### &nbsp;       });

##### &nbsp;   });

##### 

##### &nbsp;   // Update cart display

##### &nbsp;   function updateCart() {

##### &nbsp;       cartItems.innerHTML = '';

##### &nbsp;       cart.forEach(item => {

##### &nbsp;           const li = document.createElement('li');

##### &nbsp;           li.textContent = ${item.name} - $${item.price};

##### &nbsp;           cartItems.appendChild(li);

##### &nbsp;       });

##### &nbsp;       cartTotal.textContent = total.toFixed(2);

##### &nbsp;       cartCount.textContent = cart.length;

##### &nbsp;   }

##### 

##### &nbsp;   // Show/hide cart modal

##### &nbsp;   cartIcon.addEventListener('click', () => {

##### &nbsp;       cartModal.style.display = 'flex';

##### &nbsp;   });

##### 

##### &nbsp;   closeCart.addEventListener('click', () => {

##### &nbsp;       cartModal.style.display = 'none';

##### &nbsp;   });

##### 

##### &nbsp;   checkout.addEventListener('click', () => {

##### &nbsp;       alert('Checkout functionality not implemented yet!');

##### &nbsp;       cart = \[];

##### &nbsp;       total = 0;

##### &nbsp;       updateCart();

##### &nbsp;       cartModal.style.display = 'none';

##### &nbsp;   });

##### 

##### &nbsp;   // Smooth scroll for nav links

##### &nbsp;   document.querySelectorAll('nav a').forEach(anchor => {

##### &nbsp;       anchor.addEventListener('click', function(e) {

##### &nbsp;           e.preventDefault();

##### &nbsp;           const target = document.querySelector(this.getAttribute('href'));

##### &nbsp;           target.scrollIntoView({ behavior: 'smooth' });

##### &nbsp;       });

##### &nbsp;   });

##### });

