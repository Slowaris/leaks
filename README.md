Configuration and Setup Instructions:

This section provides step-by-step instructions for configuring and setting up the necessary components for the application. Ensure you have the following prerequisites installed on your server: Nginx/Apache, PHP 8.1, and MariaDB 10.4.
Database Configuration

    Open the file global/config/initdatabase.php.
    Update the database configuration settings:
        username: Set the database username.
        password: Set the database password.
        dbname: Set the name of the database.

Sellix Integration

    Open the file inc.php.
    Update the Sellix API key:
        sellix_key: Enter your Sellix API key here.

Webhook Setup

    Navigate to the Sellix dashboard and create a new webhook.
    Specify the webhook URL, pointing to the .../ipn path on your server.
    Open the file global/ipn
    Update the secret key for the webhook:
        webhook_secret: Enter the secret key provided by Sellix.

Server Requirements

Ensure your server meets the following requirements:

    Web Server: Nginx or Apache
    PHP Version: 8.1 (important)
    Database: MariaDB 10.4


Remove .php extension:

//Nginx

    location / {
        try_files $uri $uri/ @extensionless-php;
    }

    location @extensionless-php {
        rewrite ^(.*)$ $1.php last;
    }
