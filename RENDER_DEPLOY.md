# Render Deployment Guide

This project can be deployed on Render as a PHP Web Service using the included `render.yaml` blueprint.

## 1. Push your latest code to GitHub
Make sure your repository contains the new deployment file:
- `render.yaml`

## 2. Create the service on Render
1. Go to Render dashboard.
2. Click **New +** -> **Blueprint**.
3. Connect/select your GitHub repository.
4. Render will detect `render.yaml` and create the `krycialys-project` service.

## 3. Wait for first build
Render will run:
- Build: `composer install --no-dev --optimize-autoloader --no-interaction`
- Start: `php -S 0.0.0.0:$PORT -t .`

## 4. Open your app
After deploy is successful, open your Render URL.

## Notes
- This app uses Supabase from frontend JS, so no server-side DB migration is required on Render.
- API endpoints under `api/*.php` will run under the PHP built-in server.
- If email sending is needed, ensure SMTP credentials in `config/email_config.php` are valid for production.
