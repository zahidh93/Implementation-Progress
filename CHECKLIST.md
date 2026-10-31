# Sprint 01 Testing & Verification Checklist

Team members must manually verify each feature after cloning the project from GitHub before signing off on user stories.

## 1. Account Registration & Login (ACC-1)
- [ ] New user can register with a unique email address and hashed password.
- [ ] Duplicate email registration shows a clear error message.
- [ ] Invalid passwords trigger an error and prevent login.
- [ ] Successful login redirects the user to the dashboard/store view.

## 2. Product Search & Filter (UI-1)
- [ ] Keyword search correctly matches product names and descriptions.
- [ ] Category filter correctly displays items across Electronics, Clothing, Home, Kitchen, and Books.
- [ ] Filters and search queries work both individually and combined.
- [ ] Searching for non-existent items displays a clear "no products found" message.

## 3. Product Page (UI-2)
- [ ] Clicking any catalog product opens its dedicated details page.
- [ ] Product page displays correct name, description, price, and stock status.
- [ ] Missing images fall back to placeholders with proper accessibility alt text.
- [ ] Out-of-stock items show an "Out of stock" label and disable the add-to-cart action.

## 4. Shopping Cart & Persistence (CART-1)
- [ ] Users can add products, update quantities, and remove items.
- [ ] Cart subtotal updates instantly upon quantity changes.
- [ ] Cart contents persist across page refreshes using browser `localStorage`.

## 5. Checkout & Order Simulation (CART-2 & ORD-1)
- [ ] Checkout form accepts shipping address, city, postal code, and sample card details.
- [ ] Client-side validation catches missing or invalid input fields.
- [ ] Successful simulated payment generates a unique order confirmation number and order summary.
- [ ] Order-tracking view displays the initial processing state correctly.
