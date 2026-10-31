# Sprint 01 Testing & Verification Checklist

Team members must manually verify each feature after cloning the project from GitHub before signing off on user stories.

## 1. Account Registration & Login (ACC-1)
- [ ] New user can register with a unique email address and password.
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
- [ ] Out-of-stock items show an "Out of stock" label.

## 4. Manage Products & Stock (ADM-1)
- [ ] Product and category tables are correctly initialized with sample products.
- [ ] Admins can add, edit, and hide products in the catalog.
- [ ] Stock levels can be updated manually and changes appear immediately on customer pages.
- [ ] System prevents inventory quantities from going below zero.
- [ ] Products with past orders are hidden rather than deleted.
