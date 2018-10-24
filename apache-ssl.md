# Apache SSL

Install OpenSSL

```bash
sudo apt-get install openssl
```

Generate Self Signed SSL Certificate

```bash
> sudo openssl req -x509 -nodes -days 1095 -newkey rsa:2048 -out /etc/ssl/certs/server.crt -keyout /etc/ssl/private/server.key
```

Enable SSL for Apache

```bash
> sudo a2enmod ssl
```

Place default-ssl site available creating a symbolic link

```bash
> sudo ln -s /etc/apache2/sites-available/default-ssl.conf /etc/apache2/sites-enabled/000-default-ssl.conf
```

Edit the file default-ssl.conf

```bash
> sudo nano /etc/apache2/sites-enabled/000-default-ssl.conf
```

Change the following lines to point to the certs

```bash
> SSLCertificateFile    /etc/ssl/certs/server.crt
> SSLCertificateKeyFile /etc/ssl/private/server.key
```

Restart Apache

```bash
> sudo /etc/init.d/apache2 restart
```













