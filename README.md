# Docker Container for Laravel and React

### A small setup to dockerize your development environment with Laravel and React TypeScript.

## How to install 🛠️

(Using Docker Desktop)

- Clone the repositories.
- Configure the '.env' file.
- Check the docker-compose fil

### Frontend 📱

- Install the frontend part with 'npm install'.
- Test the server with 'npm run dev'.
- Configure the 'vite.config.ts' file. See the file for details.
- Create the Dockerfile and configure it. See the file for details.

### Backend 🗄️

- Install the backend part with 'composer install'.
- Test the server with 'php artisan serve'.
- Configure the environment variables to connect to your database.
- Create the Dockerfile and configure it. See the file for details.

### Docker 🐋

- Execute the docker-compose file, build the container with its images using 'docker-compose build'.
- Execute the docker-compose file with 'docker-compose up' or 'docker-compose up -d'.
- Follow the different links to connect to the different services such as 'phpMyAdmin'.

### other 🚀

To execute Laravel commands inside the container, find the container of your application using 'docker ps', then use 'docker exec -it container_name your_laravel_command'.
