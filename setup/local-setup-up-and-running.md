# Local setup - up and running

{% content-ref url="local-setup-up-and-running.md" %}
[local-setup-up-and-running.md](local-setup-up-and-running.md)
{% endcontent-ref %}

#### Technology Stack of Nebula

* Frontend - Vue.js
* Backend - Django
* Database - MongoDB



### Cloning repository

```bash
git clone <copy_link_from_bitbucket> 

# It is git@bitbucket.org:signzycode/sigmoid-web-layer.git

git checkout master (or release)
```

Front-end Setup

* You can install **NodeJS** using this [article](https://www.google.com/url?q=https%3A%2F%2Fwww.digitalocean.com%2Fcommunity%2Ftutorials%2Fhow-to-install-node-js-on-ubuntu-18-04\&sa=D\&sntz=1\&usg=AFQjCNGTyXoLkxQIwtiR-kMLAP2CgcvXrQ), if you do not have already. (Prefer using NVM)
* Change current directory to **/static** (sigmoid-web-layer/app/static)
* Run **npm install**

Back-end Setup (without Docker)

* Install Python 3.6.9 and pip 9.0.1
* Check **Dockerfile.base** in the app.
* Run **sudo apt-get update**
* Run **apt-get install -y libgtk2.0-dev**
* Run **apt install -y cmake**
* Change directory to sigmoid-web-layer.
* Run **pip install -r requirements.txt**

### Nginx setup

```bash

server {
    listen 80;
    server_name nebula.prv;

   location /static {
     root <your_path>/sigmoid-web-layer/app;
   }
​
    location / {
       # include /etc/nginx/sites-enabled/cors.conf;
       #        proxy_set_header Host $host;
       #         proxy_set_header Connection '';
       #         proxy_http_version 1.1;
       #         chunked_transfer_encoding off;
       #         proxy_buffering off;
       #         proxy_cache off;
       #         proxy_set_header X-Real-IP $remote_addr;
        # proxy_pass http://nebula;
                proxy_pass http://api.prv:52133;
        proxy_read_timeout 900s;
    }

    location /ping {
     return 200 'gangnam style!';
    # because default content-type is application/octet-stream,
    # browser will offer to "save the file"...
    # if you want to see reply in browser, uncomment next line
         add_header Content-Type text/plain;

       }

   location = /robots.txt { return 200 "User-agent: *\nDisallow: /\n"; }


}
```

{% swagger baseUrl="" path="/v2/patrons/login" method="post" summary="Login request" %}
{% swagger-description %}
Logs you in
{% endswagger-description %}

{% swagger-parameter in="body" name="username" type="string" %}
username provided to you
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}
