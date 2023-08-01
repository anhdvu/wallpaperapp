# Wallpaper App
## 1. Quickstart
- Step 1: Clone this repository to the designated deployment location.
  
        git clone https://github.com/anhdvu/wallpaperapp.git

- Step 2: Use Docker Compose to quickly deploy the app.

        cd wallpaperapp
        docker compose up -d

- Step 3: Perform database migration, choose yes if asked.

        docker exec -it wallpaperapp-service-1 php artisan migrate

- Step 4: Change ownership of `storage` directory.

        docker exec -it wallpaperapp-service-1 chown -R www-data:www-data storage/

## 2. Environment Variables

>This section serves as a reference if you wish to use your own environment variables.

The docker images and docker compose file were built testing purpose. If you are looking to deploy the app to production, refer to the `.env.example` file for settings that can be changed.

### Steps to use your own `.env` file

- Step 1: Make a copy of `.env.example` and name it `.env`.

        cp .env.example .env

- Step 2: Modify the `.env` file and uncomment the following line in `docker-compose.yml` file.

        #- ./.env:/var/www/html/.env
