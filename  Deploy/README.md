## Deploy Site off Droplet VIA Nginx

### create droplet

### ssh root@xxx.xxx.xxx

### apt install/update/upgrade

### apt install nginx

## create new user

        adduser ${username}  -- answer prompts (pw,room,group,other, etc)
        sudo adduser ${username}  -- assign sudo priviledge(must be root while doing)

## disable/lock root passwd/ability to login

         sudo passwd -d root  (disables)        -|
                                                 |-------- double_check!!
         sudo passwd -l root (locks)            -|

## create App folder in /var/www/html

## unlink default config and link your config

             sudo nano etc/nginx/sites-available/137.184.180.59
                    server{
                        listen 80;
                        listen [::]:80;
                        root /var/www/137.184.180.59;
                        index index.html;
                        }

             sudo unlink /etc/nginx/sites-enabled/default       ---unlinks

             sudo ln -s /etc/nginx/sites-available/137.184.180.59 /etc/nginx/sites-enabled/      -- links

             sudo nginx -t       --tests
             sudo systemctl restart nginx     --restart server

## back to host/your side

             create .sh script in app

echo "Switching to branch master"
git checkout master

echo "Building ap..."
npm run build

echo "Deploying files to server..."
scp -r build/\* brat@137.184.180.59:/var/www/html/137.184.180.59

echo "App has been deployed"
