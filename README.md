# MikroTik Billing System

A comprehensive billing and payment system for MikroTik ISP services built with PHP and MySQLi.

## Features

- **Customer Management**: Registration, authentication, and profile management
- **Subscription Plans**: Multiple plans with different speeds and billing periods
- **Invoice Generation**: Automatic invoice creation for subscriptions
- **Payment Integration**: Stripe, PayPal, and bank transfer support
- **MikroTik API Integration**: Automatic user creation/deletion on MikroTik
- **Dashboard**: Customer dashboard to manage subscriptions and payments
- **Admin Panel**: Manage customers, plans, and view billing reports

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/zackmusa/mikrotik-billing-system.git
   ```

2. **Install dependencies**
   ```bash
   composer install
   ```

3. **Create database**
   ```bash
   mysql -u root < database.sql
   ```

4. **Configure settings**
   - Update `config.php` with your database credentials
   - Add MikroTik connection details
   - Add payment gateway API keys

5. **Set file permissions**
   ```bash
   chmod 755 uploads/
   chmod 644 config.php
   ```

## Configuration

Update `config.php` with:
- Database credentials
- MikroTik connection details
- Stripe API keys
- PayPal credentials

## Usage

### Customer Registration
```bash
POST /api/register.php
{
  "username": "customer1",
  "email": "customer@example.com",
  "password": "password123",
  "full_name": "John Doe"
}
```

### Subscribe to Plan
```bash
POST /api/subscribe.php
{
  "plan_id": 1
}
```

### Process Payment
```bash
POST /api/payment.php
{
  "action": "process_stripe",
  "payment_id": 1,
  "token": "stripe_token_here"
}
```

## Security

- Passwords hashed with bcrypt
- CSRF protection on forms
- Input validation and sanitization
- Prepared statements to prevent SQL injection
- HTTPS recommended for production

## Support

For issues and questions, please create an issue on GitHub.

## License

MIT License - see LICENSE file for details