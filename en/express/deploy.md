## Deploy app on server

In this section, you will get to know how to deploy your Node.js application on Amazon Web Service.

There're two ways to install Node.js on Ubuntu and other Linux distributions:

1. Compile and install from the source of Node.js
2. Using package management tool (like apt-get and yum) of the Operating System: [instruction on Github]((https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager#debian-and-ubuntu-based-linux-distributions)), and I chose this approach:

```sh
curl -sL https://deb.nodesource.com/setup | sudo bash -
sudo apt-get install nodejs
```

Then you could use VIM to edit a simple JavaScript file to have a test on your server:

```
console.log('Hello Node.js and AWS.');
```

## Deploy

Firstly, I should clone the repository on Github:

```
git clone https://github.com/SFantasy/Riki.git
```

Then install the dependencies:

```
npm install
```

For we run the App using supervisor during the developing period, it's better to choose PM2 to run it on EC2.

Install PM2: `sudo npm install -g pm2`

Edit the "scripts" field on package.json

```
pm2 start ./bin/www
```

Now we are able to start our application using `npm start` command.

## Nginx

It's very simple to install Nginx on Ubuntu:

```
sudo apt-get install nginx
```

Nginx has been started when the installation completed. If we visit the public IP of EC2, the below is what we can see:

![aws-nginx](http://fantasyshao-blog.qiniudn.com/aws-nginx.png)

And now, we have to modify the config file of Nginx to make the proxy work.

> The default config file is at `/etc/nginx/nginx.conf`

```
upstream riki {
    server 127.0.0.1:3000;
}

server {
    listen 80;
    server_name localhost;

    location / {
        proxy_pass http://riki;
    }
}
```

And now we can visit Riki via IP without `:3000`:

![aws-riki](http://fantasyshao-blog.qiniudn.com/aws-riki-2.png)
