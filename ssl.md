1. `sudo snap install core; sudo snap refresh core`
2. `sudo snap install --classic certbot`
3. `sudo ln -s /snap/bin/certbot /usr/bin/certbot`
4. `sudo certbot --nginx`
5. `sudo crontab -e`
6. add inside `0 */12 * * * sudo certbot renew`


`https://certbot.eff.org/lets-encrypt/ubuntubionic-nginx.html`
