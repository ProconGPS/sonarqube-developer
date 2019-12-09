# sonarqube-developer

## Image Description 

Sonarqube Image for Developer Edition

This image is a duplicate image of community edition with Developer binaries.

The image contains two files:

  * Dockerfile: Docker image with Developer binaries
  * run.sh: Shell script to run sonarqube (same as community edition)

## Image tagging

DockerHub automatically build and push the Docker Image by Tag. 
To create another Image from a new Tag version.

  * Verify change run.sh and DockerFile from community edition 
  * Update run.sh and DockerFile accordinlgy
  * Test 
  * Push change with new tag version

```
git tag -a "7.9.1" -m "Version 7.9.1"
git push origin 7.9.1
```

## Sonarqube Details

### Management of Server ID

The server ID of the server is based on your JDBC URL that sonarqube connects.
It means that if you specify a specific JDBC URL the server ID will not change and your Developer Licence will remain the same.

By example, by hosting Sonarqube on Kubernetes, the JDBC URL will be your postgresql service and port. In this case, after a restart or upgrade of your sonarqube or postgresql version it will not change the Server ID.


### Upgrade 


As mentionned in the documentation, perform first a backup of your database and then change the Image version of your container.
Then connect to the Sonarqube: https://sonarqube.test.com/setup, and perform the database migration as requested in the web page.


