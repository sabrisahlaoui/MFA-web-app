## Introduction

This web application implements multifactor authentication (MFA) using PHP and MySQL. It provides an additional layer of security by requiring users to authenticate using an OTP sent via email followed by a QR code scan using an authenticator app.

## Features

- **Email OTP Authentication:** Sends a one-time password (OTP) to the user's registered email address.
- **QR Code Authentication:** Requires users to scan a QR code with an authenticator app (such as Google Authenticator) for a second layer of security.
- **Secure Login:** Protects user accounts from unauthorized access through multifactor authentication.

## Requirements

- PHP 7.4 or higher
- MySQL 5.7 or higher
- Web server (e.g., Apache, Nginx)

## Installation

1. **Clone the Repository**
    
    ```bash
    git clone <https://github.com/your-username/your-repository.git>
    cd your-repository
    
    ```
    
2. **Install Dependencies**
Use Composer to install the necessary PHP dependencies.
    
    ```bash
    composer install
    
    ```
    
3. **Configure the Database**
Create a MySQL database and user. Import the provided SQL schema to set up the necessary tables.
    
    ```sql
    CREATE DATABASE mfa_app;
    CREATE USER 'mfa_user'@'localhost' IDENTIFIED BY 'password';
    GRANT ALL PRIVILEGES ON mfa_app.* TO 'mfa_user'@'localhost';
    FLUSH PRIVILEGES;
    
    ```
    
    Import the database schema:
    
    ```bash
    mysql -u mfa_user -p mfa_app < database/schema.sql
    
    ```
    
4. **Set Up Environment Variables**
Create a `.env` file in the project root directory and configure your database and email settings.
    
    ```
    DB_HOST=localhost
    DB_NAME=mfa_app
    DB_USER=mfa_user
    DB_PASS=password
    EMAIL_HOST=smtp.your-email-provider.com
    EMAIL_USER=your-email@example.com
    EMAIL_PASS=your-email-password
    
    ```
    
5. **Configure the Web Server**
Ensure your web server is configured to serve the application. For example, with Apache, you might add:
    
    ```
    <VirtualHost *:80>
        DocumentRoot "/path/to/your-repository/public"
        ServerName your-domain.com
    
        <Directory "/path/to/your-repository/public">
            AllowOverride All
            Require all granted
        </Directory>
    </VirtualHost>
    
    ```
    

## Usage

1. **Registration and Login**
    - Users must register with their email address.
    - Upon login, they will receive an OTP via email.
    - After entering the OTP, they will be prompted to scan a QR code with their authenticator app.
2. **OTP and QR Code Authentication**
    - The OTP is sent to the user's registered email address.
    - The QR code should be scanned using an authenticator app, which will generate a time-based token to be entered on the website.


## Contributing

Contributions are welcome! Please submit a pull request or open an issue to discuss your ideas.

## Contact

For questions or support, please open an issue or contact [sabri.sahlaoui@enis.tn](mailto:sabri.sahlaoui@enis.tn).
