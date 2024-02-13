##install the docker

sudo snap install docker

cd Netflix-clone-Project

##Build the Docker File

docker build -t net .

## Run the Docker File

docker run -itd -p 8080:80 net

##Install

sudo apt install nginx -y




##Enter into nano Editor


sudo nano /etc/nginx/sites-available/aduri.mooo.com

##Paste the following code for Nginx Virtual Host Block

server {
   
    listen 80;


    server_name aduri.mooo.com;
    location / {
    proxy_pass http://localhost:8080;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header X-Forwarded-Proto $scheme;
   }
}

## Save and Close the File
Ctrl + X and Ctrl + O


## Execute the following for linking of files

sudo ln -s /etc/nginx/sites-available/aduri.mooo.com /etc/nginx/sites-enabled
 
## Check the linkage is succesful or not
sudo nginx -t

## Restart nginx Web Server
sudo systemctl restart nginx

## Check after Restarting if nginx is working or not  
sudo systemctl status nginx
   
   
---------------------------------------------------


to install dns use free dns tool


afraid.org dns free

and use temp email to register it for free


remove nginx completely and if you are getting nginx error

sudo apt remove --purge nginx*
sudo apt autoremove
sudo apt update
sudo apt install nginx
