# Travel Form - PHP Project

A simple PHP-based travel registration form that collects user information and stores it in a MySQL database. This project allows users to register for a trip by submitting their personal details through a web form.

## 📋 Features

- User-friendly travel registration form
- Collects participant information (name, age, gender, email, phone, additional details)
- Stores form submissions in MySQL database
- Success message confirmation after submission
- Responsive design with modern styling
- Background image support

## 🛠️ Requirements

- **PHP** 7.0 or higher
- **MySQL** 5.7 or higher (or MariaDB 10.2+)
- **Apache** web server (or any PHP-compatible web server)
- **php-mysqli** extension enabled

## 📁 Project Structure

```
php/
├── index.php           # Main PHP file with form and database logic
├── trip_database.sql   # Database schema file for import
├── bg.webp            # Background image for the form
└── README.md          # Project documentation
```

## 🚀 Installation & Setup

### Step 1: Clone or Download the Project

Place the project files in your web server directory:
- **XAMPP**: `C:\xampp\htdocs\php\` (Windows) or `/opt/lampp/htdocs/php/` (Linux/Mac)
- **WAMP**: `C:\wamp64\www\php\`
- **MAMP**: `/Applications/MAMP/htdocs/php/`
- **Custom server**: Your web root directory

### Step 2: Database Setup

1. **Import the database:**
   
   **Using MySQL command line:**
   ```bash
   mysql -u root -p < trip_database.sql
   ```
   
   **Using phpMyAdmin:**
   - Open phpMyAdmin in your browser
   - Click on "Import" tab
   - Choose the `trip_database.sql` file
   - Click "Go" to import

   **Using MySQL Workbench:**
   - Open MySQL Workbench
   - Connect to your MySQL server
   - Go to File → Open SQL Script
   - Select `trip_database.sql`
   - Execute the script

2. **Verify database creation:**
   - Database name: `trip`
   - Table name: `trip`
   - The table should have columns: `id`, `name`, `age`, `gender`, `email`, `phone`, `other`, `dt`

### Step 3: Configure Database Connection

Edit `index.php` and update the database connection settings (lines 5-7):

```php
$server = "localhost";    // Your MySQL server address
$username = "root";       // Your MySQL username
$password = "";           // Your MySQL password
```

**Note:** For production, consider using environment variables or a separate configuration file for security.

### Step 4: Set Up Background Image

Ensure the `bg.webp` file is in the same directory as `index.php`. If you're using a different image:

1. Place your image file in the project directory
2. Update line 122 in `index.php`:
   ```php
   <img class="bg" src="your-image.jpg" alt="AKGEC">
   ```

### Step 5: Start Your Web Server

- **XAMPP**: Start Apache and MySQL from the XAMPP Control Panel
- **WAMP**: Start all services from the WAMP menu
- **MAMP**: Start servers from MAMP application
- **Built-in PHP server** (for development):
  ```bash
  php -S localhost:8000
  ```

### Step 6: Access the Application

Open your web browser and navigate to:
- `http://localhost/php/index.php` (if using XAMPP/WAMP/MAMP)
- `http://localhost:8000/index.php` (if using PHP built-in server)

## 📝 Usage

1. Fill out the travel registration form with the following details:
   - **Name**: Participant's full name
   - **Age**: Participant's age
   - **Gender**: Participant's gender
   - **Email**: Valid email address
   - **Phone**: Contact phone number
   - **Additional Information**: Any other relevant details (optional)

2. Click the "Submit" button

3. Upon successful submission, a green success message will appear confirming the registration

4. The form data will be stored in the `trip` database table with a timestamp

## 🗄️ Database Schema

The `trip` table structure:

| Column | Type | Description |
|--------|------|-------------|
| `id` | INT(11) | Primary key, auto-increment |
| `name` | VARCHAR(100) | Participant's name |
| `age` | INT(3) | Participant's age |
| `gender` | VARCHAR(20) | Participant's gender |
| `email` | VARCHAR(100) | Participant's email |
| `phone` | VARCHAR(20) | Participant's phone number |
| `other` | TEXT | Additional information |
| `dt` | TIMESTAMP | Submission timestamp (auto-generated) |

## 🔧 Configuration

### Customizing the Form

- **Title**: Edit line 124 in `index.php` to change the form title
- **Success Message**: Edit line 128 to customize the success message
- **Styling**: Modify the CSS in the `<style>` section (lines 51-115)

### Database Settings

For production environments, it's recommended to:
1. Create a separate `config.php` file for database credentials
2. Use environment variables
3. Implement proper error handling and logging

## ⚠️ Security Notes

**Important:** This is a basic implementation for learning purposes. For production use, consider:

- ✅ Using prepared statements to prevent SQL injection
- ✅ Implementing input validation and sanitization
- ✅ Adding CSRF protection
- ✅ Moving database credentials to environment variables
- ✅ Implementing proper error handling (log errors, don't display to users)
- ✅ Adding rate limiting to prevent abuse

## 🐛 Troubleshooting

### Database Connection Error
- Verify MySQL is running
- Check database credentials in `index.php`
- Ensure the `trip` database exists (import `trip_database.sql`)

### Form Not Submitting
- Check PHP error logs
- Verify `php-mysqli` extension is enabled
- Ensure form action points to correct file

### Background Image Not Showing
- Verify `bg.webp` exists in the same directory
- Check file permissions
- Update the image path in `index.php` if needed



## 📄 License

This project is open source and available for educational purposes.

## 👤 Author

Created for AKGEC US Trip registration.

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements.

---

**Note:** This project is intended for educational purposes. Always follow security best practices when deploying to production environments.
