# Daraja E-commerce Website

## Demo

-   Link to admin panel `VITE link` e.g.`localhost:3000/login`

```
# login credentials
Email: admin@example.com
Password: admin123
```

-   Link to Ecommerce site: `localhost:8000`

-   Link to mailhog: `locahost:8025`

## Installation

Make sure you have environment setup properly. You will need MySQL, PHP8.1, Node.js and composer.

### Install mailhog

-   Follow the steps on this website: `https://github.com/mailhog/MailHog`
-   If you choose to use docker

```bash
docker pull mailhog/mailhog

docker run --detach \
    --name=mailhog \
    --publish=127.0.0.1:8025:8025 \
    --publish=127.0.0.1:1025:1025 \
    --restart=unless-stopped \
    mailhog/mailhog
```

-   Go to `locahost:8025` to access the email client

### Payment processing

-   Create a Stripe account and take note of your `SECRET KEY`
-   Other method of payments can be implemented on this file `app/Http/controllers/CheckoutController.php`

#### NOTE: I'VE DELEIBERATELY COMMITED MY `.env` FILE FOR DEMO PURPOSES. DO NOT DO THAT ON A REAL PROJECT

### Install Laravel Website + API

1. Download the project (or clone using GIT)
2. Copy `.env.example` into `.env` and configure database credentials
3. Navigate to the project's root directory using terminal
4. Run `composer install`
5. Set the encryption key by executing `php artisan key:generate --ansi`
6. Run migrations `php artisan migrate --seed`
7. Start local server by executing `php artisan serve`
8. Open new terminal and navigate to the project root directory
9. Run `npm install`
10. Run `npm run dev` to start vite server for Laravel frontend

### Install Vue.js Admin Panel

1. Navigate to `backend` folder
2. Run `npm install`
3. Copy `backend/.env.example` into `backend/.env`
4. Make sure `VITE_API_BASE_URL` key in `backend/.env` is set to your Laravel API host (Default: http://localhost:8000)
5. Run `npm run dev`
6. Open Vue.js Admin Panel in browser and login with
    ```
    admin@example.com
    admin123
    ```
