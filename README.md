# ValACEPasss

ValACEPass is a secure QR-based patron management system designed for library access and integration with the Koha Integrated Library System and other System of Valenzuela City Library. It provides a modern approach for authenticating patrons, generating encrypted QR codes, and managing access with support for staff roles and OTP verification.

## 🔧 Features

- 🔐 Secure login with Cardnumber and Date of Birth
- 📧 OTP email verification using Gmail SMTP (PHPMailer)
- 🧾 QR Code generation with embedded logo and name (using Endroid QR Code v4)
- 🔐 AES-256-CBC encryption inside QR codes
- 📂 Base64 QR storage in MySQL database
- 👤 Staff login with role management (Admin, Library Staff, IT Staff)
- 🔗 Integration with Koha REST API (Basic Auth)
- 📊 Admin dashboard with reports and filters
- 🛡️ SMTP failure logging and OTP rate limiting
- OCR integrated for self registration of library users
- Approval Verification of staffs of pending registrations
- Email Notification with QR Code Attachment
## 📁 Project Structure

```
valacepass/
├── public/
│   ├── login.php
│   ├── dashboard.php
│   ├── generate_qr.php
│   └── verify_otp.php
├── includes/
│   ├── db.php
│   ├── crypto.php
│   ├── auth.php
│   └── send_otp.php
├── assets/
│   ├── css/
│   ├── js/
│   └── images/
├── .env
└── composer.json
```

## ⚙️ Installation

1. Clone the repository:

```
git clone https://github.com/yourusername/valacepass.git
```

2. Configure environment variables in `.env`:

```
KOHA_BASE_URL=
KOHA_API_USER=
KOHA_API_PASS=
GMAIL_USER=
GMAIL_PASS=
ADMIN_USER=admin
ADMIN_PASS=admin
```

3. Install PHP dependencies via Composer:

```
composer install
```

4. Import the SQL schema into MySQL database.

5. Launch using Apache (XAMPP or Ubuntu LAMP).

## 🛡️ Security

- Passwords are hashed using PHP `password_hash()`.
- QR data is encrypted using AES-256-CBC.
- OTP requests are logged with status, SMTP error message, and resend restriction.
- Only verified users may access QR generation and dashboard.

## 📌 License

This project is intended for educational and government use under Valenzuela City Library IT policy.
