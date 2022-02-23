# Docker_ssh_exercise

How to SSH into Docker containers using the docker run command and a Dockerfile.

Clone the Dockerfile and run the docker build command 

# Building the docker Image
sudo docker build -t name_on_the_image .

Run docker run to create and run the container from the image telling Docker to run the image in the background (-d)

# Running the container using the newly built image
docker run -d --name name_on_container -p 22:22 name_on_the_image


# Verify SSH connectivity between the Docker host and the container
sudo docker port test_sshd_container

Try ssh into your container by using your ip-adress on your computer, example ssh 192.168.100.1:22.

Windows-users
# If you want to connect from another machine in the same network you need to add a rule on Windows firewall. Enable docker-backend on port 22
