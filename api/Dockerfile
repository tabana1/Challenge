# Use the official PHP image with Apache
FROM php:8.1-apache

# Install required PHP extensions
RUN docker-php-ext-install pdo pdo_mysql

# Set working directory and copy project files
WORKDIR /var/www/html
COPY . .

# Install Composer and Laravel dependencies
RUN apt-get update && \
    apt-get install -y zip unzip && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    composer install

# Set up Apache mod_rewrite
RUN a2enmod rewrite

# Expose port
EXPOSE 8000

# Start Apache server
CMD ["apache2-foreground"]

