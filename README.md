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
Confidential files which can’t be added to GitHub repo added in this drive and the path on project file is braingymjr/client/.env (both for production and master branch)
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

