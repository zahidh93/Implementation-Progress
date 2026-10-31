# 4. Implementation Progress

During Sprint 01, our team developed the first working front-end prototype of the e-commerce system. The goal for this stage was to turn the initial wireframes and requirements into a usable customer shopping flow. The prototype now allows users to browse products from the four agreed product areas — **Electronics, Clothing, Home, Kitchen, and Books** — and interact with the main features of the store (UI-1, UI-2). Users can search for products, filter the catalog by category, sort products by price or name, open a product-details view, and add products to a shopping cart.

The shopping cart was one of the main features implemented during this sprint (CART-1). Users can add multiple products, increase or decrease quantities, remove products, and see the subtotal update automatically (CART-1). The cart is stored using the browser's `localStorage`, which means the cart contents remain available after the page is refreshed. This gave us a simple way to demonstrate persistence during Sprint 01 without requiring the full database implementation yet.

```javascript
function addToCart(id, quantity = 1) {
  const existing = state.cart.find(item => item.id === id);

  if (existing) {
    existing.qty += quantity;
  } else {
    state.cart.push({ id, qty: quantity });
  }

  localStorage.setItem("shopease-cart", JSON.stringify(state.cart));
  renderCart();
}
```

We also implemented a prototype login screen (ACC-1) and a demo checkout process (CART-2). The login page validates that the user has entered an email address and password, but it does not yet connect to a real account database (ACC-1). During checkout (CART-2), users can enter their name, shipping address, city, postal code, and a sample card number. The system performs basic client-side validation and then displays an order-confirmation screen with a generated order number. A simple order-tracking layout (ORD-1) is also included to show how the order could move through the stages of Ordered, Processing, Shipped, and Delivered.

The product catalog is currently stored in a JavaScript array. This made it possible to build and test the interface without waiting for the database layer. The same data is used by the search, category-filtering, product-details, cart, and checkout features, helping keep the prototype consistent across the different screens.

```javascript
const products = [
  { id: 1, name: "Wireless Headphones", category: "Electronics", price: 129.99 },
  { id: 4, name: "Classic T-Shirt", category: "Clothing", price: 24.99 },
  { id: 6, name: "Throw Pillow", category: "Home", price: 29.99 },
  { id: 7, name: "Algorithms Textbook", category: "Books", price: 89.99 },
  { id: 8, name: "Cookware Pot", category: "Kitchen", price: 44.99 }
];
```

### Testing Completed

The JavaScript source was checked for syntax errors using Node.js and passed successfully. We also performed a static integration check between the HTML and JavaScript files to confirm that every page element referenced by the JavaScript exists in the interface. The prototype includes a testing checklist in the repository so team members can manually verify category filtering (U-1), product search (U-1), cart updates (CART-1), cart persistence (CART-1), login validation (ACC-1), checkout (CART-2), and order confirmation (ORD-1) after cloning the project from GitHub.
### Technical Challenges and Resolutions

One challenge was deciding how to demonstrate a working cart before the full database and user-account system were available (CART-1). We solved this by using `localStorage` for temporary cart persistence. This keeps Sprint 01 simple while still allowing the cart to behave like a real feature during testing. Another challenge was keeping the product categories consistent across the requirements and interface. To solve this, the prototype uses the same four categories throughout the catalog: Electronics, Clothing, Home, Kitchen, and Books. 

The checkout (CART-2) and login features (ACC-1) also required a temporary solution because a real authentication service and payment gateway are outside the current prototype. We therefore implemented them as front-end demonstrations with form validation. No real passwords or payment information are transmitted or stored.

### Items Deferred to Future Sprints

The current prototype is mainly focused on demonstrating the customer-facing interface and shopping flow. Real user authentication (ACC-1, ACC-2), advanced catalog filtering such as price range and in-stock filters (UI-1), a server-side database, inventory management (ADM-1), secure payment processing (CART-2), persistent customer order history and cancellation (ORD-1, ORD-2), administrator functions (ADM-1, ADM-2), sales reporting (REP-1), and live order-status updates have been deferred to later sprints. These features can be connected to the existing interface as the project moves from the initial prototype toward a complete system.