docker ps -a #check all running containers; process status = ps

docker stop $(docker ps -aq) #stop containers; $() replaced by output; a = running + stopped containers

docker rm $(docker ps -aq) #remove containers, will list containers

truncate -s 0 /var/lib/docker/containers/*/*-json.log #clear docker logs

#removing will stop container but vice versa isn't valid

#running online
To run a Docker container online, you can use a cloud-based container service such as Amazon Elastic Container Service (ECS)1 or Google Kubernetes Engine (GKE)2. You can also use a container registry such as GitHub Container Registry3 or Google Container Registry1 to store your Docker images and then deploy them to a cloud-based container service.


