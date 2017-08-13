# Make a war file with given SOAPUI project
# Deploy it into tomcat webapps folder
# Expose the port to jenkins

docker build -t soapuiimage .  
docker run -it -d  [imageid]  
docker exec -it [containerid] /bin/bash
  
# Port forward(forward container port to host machine)
docker run -p 127.0.0.1:8585:8080 --name [containerid] -t [imageid]

# Stop docker container
docker stop [containerid]
docker kill [containerid]
doker ps