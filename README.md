# Kodomosaitama

## Requirements

Before you begin, ensure you have met the following requirements:

- PHP 7.2 or higher
- Composer
- MySQL

## Installation

Follow these steps to install and set up your Laravel project on your local machine:

1. **Initialize Git and set up remote**

    Initialize a new Git repository in your project directory and set up the remote origin:

    ```bash
    git init
    git remote add origin https://generated_token@github.com/EBP-Japan/kodomoouen_saitama.git
    ```
2. **Navigate to the project directory**

    ```bash
    cd your-repo
    ```

3. **Check out the `developmmr` branch and pull latest code**

    Create and switch to the `main` branch, and then pull the latest code from the `developmmr` branch:

    ```bash
    git branch -M main
    git pull origin developmmr
    ```

4. **Comment out the line in the local environment**

    In your `App\Providers\AppServiceProvider` class file (`app/Providers/AppServiceProvider.php`), comment out the following line within the `boot` method:

    ```php
    if ($this->app->environment('production')) {
        //URL::forceScheme('https');
    }
    ```

5. **Install dependencies**

    Use Composer to install all the necessary dependencies:

    ```bash
    composer install
    ```

6. **Set up environment variables**

    Copy the `.env.example` file to create a new `.env` file:

    ```bash
    cp .env.example .env
    ```

    Edit the `.env` file to match your environment settings. Make sure to set the correct database connection details:

    ```dotenv
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=your_database_name
    DB_USERNAME=your_database_user
    DB_PASSWORD=your_database_password
    ```

7. **Generate application key**

    Generate a new application key:

    ```bash
    php artisan key:generate
    ```

8. **Import the database**

    If you have a database dump file, you can import it using the following command. Replace `path/to/dumpfile.sql` with the actual path to your SQL dump file:

    ```bash
    mysql -u your_database_user -p your_database_name < path/to/dumpfile.sql
    ```


## Running the Application

To run the application, use the following command:

```bash
php artisan serve
```