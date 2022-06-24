# Web layer

## Nginx service monitoring & configuration changes

The nginx is hosted on the production web layer servers. And is located at /usr/local/nginx/sites-enabled/\*.

#### Check status

To check status of nginx service running.

sudo service nginx status

#### Start a stopped nginx service

To start the nginx service after the configuration changes, run the below command.

sudo service nginx start

#### Restart

To restart the nginx service after the configuration changes, run the below command.

sudo service nginx restart

### Nginx configuration on web server

Nginx configuration is used on the web server. **api.prv** points to the app server location (IP).

```
server {
    listen 80;
    server_name _;

    location /utilities {
        proxy_pass http://api.prv:52301/api;
        proxy_read_timeout 180s;
    }

    location /api/files {
        proxy_pass http://api.prv:51691/api/files;
    }
}

```

## Web application location and starting

To be filled.
