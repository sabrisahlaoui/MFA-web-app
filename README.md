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
