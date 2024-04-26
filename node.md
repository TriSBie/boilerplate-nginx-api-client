# Multi container set up flow 
1. Push code to github
2. Travis automatically pushs repo
3. ______ builds a test image, tests code
4. ______ builds prod images
5. ______ pushes built prod images to Docker Hub
6. Travis pushes project to AWS EB
7. EB pulls image from Docker Hub, deploys
# AWS Docker json configuration
1. name is the container name.
2. image is the Dockerhub image name to run in this container.
3. hostname is the url to use to access this image.
4. essential: true means shutdown all containers if this container fails. At least one container must be set to true.
5. portMappings, hostPort is the port on the machine that is hosting all of the containers.
6. portMappings, containerPort map to this port in this container.
7. links is a list of containers that depend on this container. Use the container name, not the hostname.