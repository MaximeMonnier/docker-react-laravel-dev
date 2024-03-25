FROM webdevops/php-nginx:8.3-alpine

# Install necessary dependencies, including mysql-client
RUN apk add --no-cache oniguruma-dev libxml2-dev nodejs npm mysql-client

# Install PHP extensions
RUN docker-php-ext-install bcmath ctype fileinfo mbstring pdo_mysql xml

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Set the web document root directory for Nginx
ENV WEB_DOCUMENT_ROOT /app/public

# Set the working directory
WORKDIR /app

# Copy the application source code into the working directory
COPY . .

# Install Composer dependencies
# In development mode, you may want to include development dependencies
RUN composer install --no-interaction

# Copy .env.example to .env if .env does not exist
RUN if [ ! -f .env ]; then cp .env.example .env; fi

# Install npm dependencies and compile assets (if necessary)
RUN npm install

# Ensure files are owned by the 'application' user
RUN chown -R application:application .

# Expose port 80 to access Nginx
EXPOSE 80
