# Make a war file with given SOAPUI project
# Deploy it into tomcat webapps folder
# Expose the port to jenkins

docker build -t soapuiimage .
docker run -it -d  [imageid]
docker exec -it [containerid] /bin/bash