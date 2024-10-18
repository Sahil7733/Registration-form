# Registration Page

This repository contains a simple registration web page built with HTML, CSS, JavaScript, and PHP. It stores the user’s data (first name, last name, email, and password) in an SQL database. It also includes a "Sign In" link for existing users.

## Features
- **User Registration**: Collects first name, last name, email, and password.
- **Client-Side Validation**: JavaScript is used for basic form validation.
- **Password Encryption**: The password is securely hashed before storing in the database.
- **Database Storage**: User data is stored in an SQL database using PHP.

## Prerequisites
Before you can use this project, ensure that the following are installed on your system:
- [XAMPP](https://www.apachefriends.org/index.html) or any server environment with PHP and MySQL support.
- A web browser.
- A code editor (e.g., VSCode, Sublime, etc.)

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Sahil7733/registration-form.git
## Set Up the Database

1. Open phpMyAdmin (usually available at [http://localhost/phpmyadmin](http://localhost/phpmyadmin)).
2. Create a new database (e.g., `user_registration`).
3. Inside the `SQL` tab, run the following query to create a `users` table:

    ```sql
    CREATE TABLE users (
      id INT(10) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
      first_name VARCHAR(30) NOT NULL,
      last_name VARCHAR(30) NOT NULL,
      email VARCHAR(50) NOT NULL UNIQUE,
      password VARCHAR(255) NOT NULL,
      reg_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
    );
    ```

## Configure the Database Connection

1. Open the `config.php` file in the root of the project.
2. Edit the database connection details to match your environment:

    ```php
    <?php
    $servername = "localhost";
    $username = "root";
    $password = "";
    $dbname = "registration";
    $conn = new mysqli($servername, $username, $password, $dbname);

    if ($conn->connect_error) {
        die("Connection failed: " . $conn->connect_error);
    }
    ?>
    ```

## Run the Application

1. Move the project folder into the `htdocs` directory of your XAMPP installation (or the equivalent for your server setup).
2. Start Apache and MySQL from the XAMPP control panel.
3. Visit [http://localhost/registration-page](http://localhost/registration-form) in your browser.

## index.php

This file contains the HTML form for user registration. It includes the following fields:
- First Name
- Last Name
- Email
- Password
- A "Sign In" link for existing users

## register.php

This script processes the registration form submission, validates the input data, hashes the password, and stores the user’s information in the SQL database.

## script.js

Contains JavaScript code for client-side validation, such as:
- Ensuring the email format is valid
- Checking password strength
- Ensuring all required fields are filled

## style.css

Defines the styles for the registration form to make it:
- User-friendly
- Responsive across devices

## Usage

- **Registration**: Fill out the registration form with the required details (first name, last name, email, and password) and click the "Register" button.
- **Sign In**: A link to the sign-in page is provided for users who already have an account.

This is my live link for showcasing the project:

[http://registrationpage.infinityfreeapp.com/](http://registrationpage.infinityfreeapp.com/)
