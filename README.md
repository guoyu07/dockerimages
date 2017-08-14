# This docker image does the below steps
# Make a war file with given SOAPUI project
# Deploy it into tomcat webapps folder
# Expose the port to jenkins

# build image, run and execute containers
docker build -t soapuiimage .  
docker run -it -d  [ImageId]  
docker exec -it [ContainerId] /bin/bash
  
# Port forward(forward container port to host machine)
docker run -p 127.0.0.1:8585:8080 --name [ContainerId] -t [imageid]

# Stop  and remove docker container
docker stop $(docker ps -a -q)  
docker rm $(docker ps -a -q)  
docker ps  

# Delete all images and release memory
docker rmi $(docker images -q)

# Show Image  dependencies
docker images -viz | dot -Tpng -o docker.png  
