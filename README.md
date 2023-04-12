# sonarqube-docker-compose
Port 9000 is opened in security firewall rule

#Login to instance where you will be installing SonarQube, perform the below command to configure virtual memory permanently for SonarQube to function:
sudo vi /etc/sysctl.conf

#Add the following lines to the bottom of that file:

vm.max_map_count=262144
fs.file-max=65536

To make sure changes are getting into effect:
sudo sysctl -p

#Perform System update
sudo apt-get update

#Install Docker and Docker-Compose from official documentation.

#Add current user to docker group
sudo usermod -aG docker $USER

clone or copy docker-compose.yml from this repo: 
sudo docker-compose up -d 

Make sure SonarQube is up and running by checking the logs
sudo docker-compose logs --follow
