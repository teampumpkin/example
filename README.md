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

# *Confidential file*
Confidential file which can’t be added to GitHub repo added in this drive and the path on project file is braingymjr/client/.env (both for production and master branch)
.env files contains credentials of databases and secret variables/keys.(stored .env.staging for staging .env.production for production)
