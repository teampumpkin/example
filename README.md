# Steps to setup the BrainGym project

 # *Pre-requisite*
- Node Js
- Docker
- MySQL
- Nginx
- Redis 

# *Domain and Cloud Provider*
Cloud provider on which website is hosted and Domain name.
- Amazon Web Server.
- braingymjr.com (GoDaddy).

  Added credentials in file and upload files that to this folder https://drive.google.com/drive/folders/1SjZrdc5F2hh5R0vF4KXn5jy3vX2JIuFM
    
# *Server specifications*
Server specifications such as OS, Number of vCpu, memory, storage, region(country) and price.
 - Os: Linux
 - Vcpu: 4Vcpu
 - Memory: 16GiB
 - Storage: 65 GB
 - Region: Ohio( USA )
 - Instance Price - 45$ monthly and RDS Price - 13$ monthly

# *Branches*
- Staging branch name: staging
- Production branch name: master

# *Confidential files*
Confidential files which can’t be added to GitHub repo added in this drive and the path on project file is braingymjr/client/.env (same path for production and master branch)
.env files contains credentials of databases and secret variables/keys.(stored .env.staging for staging .env.production for production)

# *Installation*
Node Js: 
Use Node Version manager to manage node installation, In this project set node js version to 16.16.0 and install dependent packages yarn and pm2.

Docker:
We are using docker to setup the Ghost(CMS) container. 

MySQL:
In this project we have used MySQL database service of Aws that is Relational Database Service rather than installing MySQL on server. 

Nginx:
To route the request to the requested port number we are using nginx, Added nginx.conf to project repo.

Redis: 
We have install Redis for cache storage on server.

# *Deployment Steps*

__Setting up for first time:__

Make sure that the you have clone the GitHub project repo, places important file from Drive folder to exact path, all dependencies and packages are installed and docker, Redis, MySQL and Nginx are up and running.

MySQL:
Create a databases with name and password as present in drive file and the user which is created should have all privileges to the databases. host, username and password need to be added to  file upload to the project folder on this drive https://drive.google.com/drive/folders/1zI3xidnVcuXZ745pZDGympMlapvL3xsT

Docker:
Create a Ghost(CMS) container with this command:
docker run -d --name ghost -e database__client=mysql -e database__connection__host=databasebraingym.amazonaws.com -e database__connection__user=braingymjr -e database__connection__password= {password} -e database__connection__database= ghost_db -e NODE_ENV=production -e url=https://www.braingymjr.com/blog -p 127.0.0.1:4242:2368 -v /root/ghostDockerVolume:/var/lib/ghost/content ghost:alpine

Nginx:
After placed nginx.conf from project to /etc/nginx/conf.d/nginx.conf, create ssl certificate using certbot and reload the nginx.

Commands to start application:
Get into project dir “cd braingymjr/api” , install packages “yarn”  and start api process with pm2 “pm2 start ecosystem.config.js –env=production”
Get into project dir “cd braingymjr/client” , install packages “yarn && yarn build”  and start api process with pm2 “pm2 start ecosystem.config.js –env=production”

__Deployment Of New Changes After Project Is Set upped:__

Integrate new changes:
Get into the project home directory and do git pull to fetch latest code.

Commands to start application:
Run Database migration to update database changes. npx knex migrate:latest –env=production
Get into project dir “cd braingymjr/api” , install packages “yarn”  and restart api process with pm2 “pm2 restart api”
Get into project dir “cd braingymjr/client” , install packages “yarn && yarn build” or "yarn stage"(for staging)  and restart the client process with pm2 “pm2 restart client”
pm2 process name or id can be used to restart pm2 process.
