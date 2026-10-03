# DevOps Journey

A small static website with my DevOps learning path and Coursera/IBM certificates, hosted on my own Linux server with Nginx.

## Run locally
Open `index.html` in a browser

## Deploy with Nginx (Ubuntu/Debian)
```bash
sudo apt update && sudo apt install nginx -y

# copy the site
sudo mkdir -p /var/www/devops-journey
sudo cp -r index.html assets /var/www/devops-journey/

# add the config
sudo cp nginx-site.conf /etc/nginx/sites-available/devops-journey
sudo ln -s /etc/nginx/sites-available/devops-journey /etc/nginx/sites-enabled/
sudo rm /etc/nginx/sites-enabled/default

# test and reload
sudo nginx -t
sudo systemctl reload nginx
```
Open `http://SERVER-IP` in a browser.

## Troubleshooting
- `sudo nginx -t` shows config errors
- `sudo tail -f /var/log/nginx/devops-journey.error.log`
- 403 error: `sudo chmod -R 755 /var/www/devops-journey`

## Next steps
- [ ] Add HTTPS with Certbot
- [ ] Containerize with Docker
- [ ] Auto-deploy with GitHub Actions
