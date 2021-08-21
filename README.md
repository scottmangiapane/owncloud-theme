## Owncloud Theme

1. Assuming you're running owncloud with docker and docker-compose, connect to your container:
   - `docker ps`
   - `docker exec -it <container id> bash`
2. Install the app:
   - `cd /var/www/owncloud/custom`
   - `git clone <repo url> theme-custom`
   - `chown -R www-data:root theme-custom`
3. Exit the container, and add the following to your .env file:
   ```
   OWNCLOUD_INTEGRITY_IGNORE_MISSING_APP_SIGNATURE=theme-custom
   ```
4. Restart the container:
   - `docker-compose down`
   - `docker-compose up -d`
