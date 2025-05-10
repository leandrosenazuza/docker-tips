# docker-tips
I created this repository to help me to remember how to deal with docker

## How to use a docker image to create a oracle database container

First off, you have to go to Oracle github, and clone the oficial repository: https://github.com/oracle/docker-images

Your docker service have to be initiated.

After that, you have to look for the folder "..\oracle\docker-images\OracleDatabase\SingleInstance\dockerfiles", and look for the file "buildContainerImage.sh". This is all specification to create the oracle database image. Open your git bash, look for this .sh file, and execute it. Wait until build is completed. 

If you run the command "docker images", you should see something like that: "oracle/database          18.4.0-xe   4d9c07d48a87   About an hour ago   5.9GB". It means that you created an oracle database image. 

Let's create the container. Execute: "docker run --name containerOracle -e ORACLE_PWD=admin123 -p 1521:1521 -d oracle/database:18.4.0-xe". ORACLE_PWD is the password of the database, and the standard user is system.
