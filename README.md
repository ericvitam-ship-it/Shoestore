# Stride Shoes: Shoe E-Commerce Platform
Stack: PHP 8, MySQL (XAMPP), HTML/CSS/JavaScript, Bootstrap 5.

## Features
Customer: homepage with filters, product page with colour and size selector, cart, wishlist, checkout (M-Pesa code or cash on delivery),
order tracking, return or exchange requests, reviews, order messages, registration and login with lockout.
Staff: dashboard, inventory, orders, shipping, returns, customers.
Administrator (also all staff pages): products and variants with images, categories, brands, delivery zones, reviews,
reports and CSV export, users and roles, audit log.

## Setup (XAMPP on Windows)
1. Copy this folder to C:\xampp\htdocs\shoe-store (overwrite existing files).
2. Start Apache and MySQL in the XAMPP Control Panel.
3. First time only: open http://localhost/phpmyadmin > SQL tab and run, in order, database/schema.sql, database/seed.sql, database/seed_products.sql.
4. If you already had the database from an earlier version: open http://localhost/shoe-store/tests/upgrade_database.php (safe to run more than once).
5. Demo data (optional, for testing): open tests/create_demo_users.php, then tests/create_demo_orders.php (each once).
6. Check product images: tests/check_images.php

## Addresses
- Shop: http://localhost/shoe-store/public/index.php
- Login: http://localhost/shoe-store/public/login.php
- Admin: http://localhost/shoe-store/admin/dashboard.php (staff and admin accounts only)

## Demo accounts (password Pass1234)
customer@shoestore.test, staff@shoestore.test, admin@shoestore.test, plus amina@, brian@ and cynthia@shoestore.test (customers with demo orders).

## Folder guide
config/ settings and database connection | includes/ shared PHP code (auth, helpers, header and footer) | public/ customer pages |
admin/ staff and admin pages | assets/ CSS and product images | database/ SQL files | tests/ setup and check helpers

## Security notes
Prepared statements everywhere, CSRF tokens on every form, escaped output, password hashing, login lockout, idle timeout,
role checks on the server, validated image uploads. Before going live: use a MySQL user with limited rights (not root),
turn off display_errors, serve over HTTPS, and delete the tests/ folder.
