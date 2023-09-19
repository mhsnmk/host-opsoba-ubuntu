```shell
sudo apt update
sudo apt upgrade
```

```shell

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
source ~/.bashrc
nvm install v16.0.0
node -v
sudo apt-get install -y node-sqlite3

```
```shell
npm install yarn -g
git clone https://github.com/mhsnmk/opsobafrontend.git
git clone https://github.com/0xNeit/opsoba-sdk.git
git clone https://github.com/0xNeit/opsoba-uikit.git
cd opsoba-sdk
yarn
yarn build
cd ../
cd opsoba-uikit
yarn
yarn build
cd ../
cd opsobafrontend
yarn
npm install ../opsoba-sdk --force


```


```shell
npm i pm2 -g 
pm2 start yarn --name "my-react-app" -- start
sudo ufw allow 3000  #react application port
sudo ufw allow http
sudo ufw allow https
```


```shell
sudo apt install nginx
```
```shell
sudo nano /etc/nginx/sites-available/default
```

Add the following to the location part of the server block
```shell
    server_name bsclaunch.live www.bsclaunch.live;

    location / {
        proxy_pass http://localhost:3000; #whatever port your app runs on
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
```

after pasting it press ctrl+x and then press enter and you'll be back in the terminal

```shell
sudo nginx -t
sudo service nginx restart
```


```shell
snap install certbot --classic
sudo apt-get install python-certbot-nginx
sudo certbot --nginx -d bsclaunch.live -d www.bsclaunch.live --register-unsafely-without-email

# Only valid for 90 days, test the renewal process with
certbot renew --dry-run --
