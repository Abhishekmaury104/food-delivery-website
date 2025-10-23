# Food Delivery Software

Simple PHP/MySQL food-ordering system with shop registration, customer sign-up/login, menu, cart, order placement and admin dashboard.

## Important Files
- User-facing entry: [index.php](index.php)  
- Admin dashboard: [admin/index.php](admin/index.php)  
- Database dump: [dbms_project.sql](dbms_project.sql)  
- DB connection: [floating-login-signup/partials/_dbconnect.php](floating-login-signup/partials/_dbconnect.php)  
- Signup & email verification (uses PHPMailer): [`sendMail`](floating-login-signup/partials/signUp.php) in [floating-login-signup/partials/signUp.php](floating-login-signup/partials/signUp.php)  
- PHPMailer copies included: [phpmailer1/PHPMailer.php](phpmailer1/PHPMailer.php) and [floating-login-signup/partials/PHPMailer/PHPMailer/src/PHPMailer.php](floating-login-signup/partials/PHPMailer/PHPMailer/src/PHPMailer.php)  
- Payment upload handling: [file/index1.php](file/index1.php) and [file/index.php](file/index.php)  
- Shop listing: [shops_list/index.php](shops_list/index.php)  
- Restaurant view & cart: [restuarent/index1.php](restuarent/index1.php) and [restuarent/add_to_cart.php](restuarent/add_to_cart.php)  
- Admin orders: [admin/orders.php](admin/orders.php)

## Features
- User signup/login with email verification.
- Shop registration and listing.
- Menu management (admin).
- Cart stored in DB / client-side JS with AJAX sync ([restuarent/add_to_cart.php](restuarent/add_to_cart.php)).
- Order placement with payment screenshot upload ([file/index1.php](file/index1.php)).
- Admin UI to view/confirm orders ([admin/orders.php](admin/orders.php)).

## Requirements
- PHP 7.4+ / 8.x (project contains PHPMailer compatible with PHP 5.5+)
- MySQL 
- Apache (XAMPP recommended for local setup)

## Setup 
1. clone the repository into your web root.
```bash
https://github.com/Abhishekmaury104/food-delivery-website.git
```
1. Extract and Put project folder under htdocs (e.g. C:\xampp\htdocs\Food-delivery-software-main).
2. Start Apache and MySQL (e.g. via XAMPP).
3. Import the database:
   - Import [dbms_project.sql](dbms_project.sql) into MySQL (phpMyAdmin or mysql CLI).
4. Update DB connection:
   - Edit [floating-login-signup/partials/_dbconnect.php](floating-login-signup/partials/_dbconnect.php) with your DB credentials.
5. Configure SMTP (for email verification):
   - Update SMTP credentials in [floating-login-signup/partials/signUp.php](floating-login-signup/partials/signUp.php). It currently uses included PHPMailer files ([phpmailer1/PHPMailer.php](phpmailer1/PHPMailer.php)).
   - Remove hard-coded passwords and use environment variables or secure config before production.
6. Open the site:
   - User: http://localhost/<your-folder>/index.php  
   - Admin: http://localhost/<your-folder>/admin/index.php
