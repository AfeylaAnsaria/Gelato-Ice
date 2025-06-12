# Gelato Ice - Manage Your Sweet Treats

---

Welcome to **Gelato Ice**, your ultimate gelato shop management system! Gelato Ice helps you organize, plan, and manage your gelato business operations. Whether you're planning seasonal flavors, managing inventory, or tracking customer preferences, this app has got you covered. Built using modern web technologies and a clean, intuitive design, Gelato Ice is here to make gelato business management sweet and stress-free!

---

## 🍨 Features

• **Flavor Management**: Organize your gelato flavors and plan seasonal menus for any occasion.

• **Inventory Tracking**: Sync your ingredient stock with production schedules to keep track of your supplies.

• **Customer Preferences**: Categorize customer orders and preferences for personalized service—classic, premium, seasonal, and specialty flavors.

• **Sales Analytics**: Create detailed reports with sales data, popular flavors, and customer insights.

• **Interactive Dashboard**: A sleek and interactive interface that makes it easy to manage all aspects of your gelato business.

---

## 🔥 Technologies Used

### Frontend:
◦ **HTML**: Structure of the web pages.
◦ **CSS**: Styling to make the app look modern and appealing.
◦ **JavaScript**: Bringing dynamic functionality to the app, including interactive flavor selections.

### Backend:
◦ **PHP**: Server-side logic for handling business operations and database interactions.
◦ **MySQL**: Database management for storing flavor recipes, inventory, and customer data.

### Additional Tools:
◦ **Bootstrap**: Responsive design framework for mobile-friendly interface.
◦ **Chart.js**: Data visualization for sales analytics and reporting.

---

## 🚀 Installation Steps

### Prerequisites
- Web server (Apache/Nginx)
- PHP 7.4 or higher
- MySQL 5.7 or higher
- Composer (for dependency management)

### Step-by-Step Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/gelato-ice.git
   cd gelato-ice
   ```

2. **Install Dependencies**
   ```bash
   composer install
   npm install
   ```

3. **Database Setup**
   ```sql
   CREATE DATABASE gelato_ice;
   USE gelato_ice;
   ```
   
   Import the database schema:
   ```bash
   mysql -u username -p gelato_ice < database/schema.sql
   ```

4. **Configuration**
   - Copy `.env.example` to `.env`
   - Update database credentials in `.env` file:
   ```
   DB_HOST=localhost
   DB_NAME=gelato_ice
   DB_USER=your_username
   DB_PASS=your_password
   ```

5. **Set Permissions**
   ```bash
   chmod 755 storage/
   chmod 755 uploads/
   ```

6. **Start the Application**
   ```bash
   php -S localhost:8000
   ```

---

## 📱 Usage Guide

### Getting Started

1. **Admin Login**
   - Navigate to `/admin` 
   - Use default credentials: `admin@gelato.com` / `password123`
   - Change password after first login

2. **Adding Flavors**
   - Go to "Flavor Management" section
   - Click "Add New Flavor"
   - Fill in flavor details: name, ingredients, cost, seasonal availability
   - Upload flavor image

3. **Inventory Management**
   - Navigate to "Inventory" tab
   - Add ingredients with quantities and suppliers
   - Set low-stock alerts
   - Track ingredient usage per flavor

4. **Customer Orders**
   - Use "Orders" section to process customer requests
   - Select flavors, portions, and add-ons
   - Generate receipts and track order history

5. **Analytics Dashboard**
   - View sales reports by day/week/month
   - Monitor popular flavors and peak hours
   - Export data for external analysis

---

## 🛠️ Configuration Options

### Flavor Categories
```php
// config/flavors.php
return [
    'categories' => [
        'classic' => ['Vanilla', 'Chocolate', 'Strawberry'],
        'premium' => ['Pistachio', 'Tiramisu', 'Salted Caramel'],
        'seasonal' => ['Pumpkin Spice', 'Eggnog', 'Summer Berry'],
        'vegan' => ['Coconut', 'Almond', 'Oat Milk Chocolate']
    ]
];
```

### Business Settings
```php
// config/business.php
return [
    'shop_name' => 'Your Gelato Shop',
    'operating_hours' => '09:00-22:00',
    'currency' => 'IDR',
    'tax_rate' => 0.11,
    'portions' => ['Small', 'Medium', 'Large', 'Family']
];
```

---

## 🔧 API Endpoints

### Flavors
- `GET /api/flavors` - Get all flavors
- `POST /api/flavors` - Add new flavor
- `PUT /api/flavors/{id}` - Update flavor
- `DELETE /api/flavors/{id}` - Remove flavor

### Orders
- `GET /api/orders` - Get order history
- `POST /api/orders` - Create new order
- `GET /api/orders/{id}` - Get order details

### Analytics
- `GET /api/analytics/sales` - Sales data
- `GET /api/analytics/flavors` - Flavor popularity
- `GET /api/analytics/customers` - Customer insights

---

## 🎨 Customization

### Themes
The application supports multiple themes:
- Light Mode (default)
- Dark Mode
- Gelato Theme (colorful)

### Language Support
Currently supported languages:
- English (default)
- Indonesian
- Italian

---

## 📊 Database Schema

### Main Tables
```sql
-- Flavors table
CREATE TABLE flavors (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    description TEXT,
    ingredients JSON,
    price DECIMAL(10,2),
    category VARCHAR(50),
    is_available BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Orders table
CREATE TABLE orders (
    id INT PRIMARY KEY AUTO_INCREMENT,
    customer_name VARCHAR(100),
    flavors JSON,
    total_amount DECIMAL(10,2),
    order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    status ENUM('pending', 'completed', 'cancelled')
);
```

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---


## 🙏 Acknowledgments

- Thanks to all contributors who helped build this project
- Special thanks to gelato masters who provided flavor expertise
- Bootstrap team for the amazing UI framework
- Chart.js team for beautiful data visualizations

---

**Made with ❤️ for gelato lovers everywhere**
