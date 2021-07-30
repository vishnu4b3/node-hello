# Creating Jenkins CI/CD pipeline for to buid and push the docker image to dockerHub.

# Prerequisites:

* Jenkins server with an agent or without an agent.
* Should have to install the Docker on where the  Jenkins build running.
* Install the required plungins related to pipeline, git and docker.
* should have to save git and DockerHub credentials in Jenkins manage credentials.
* Should have to maintain the Dockerfile and Jenkinsfile in the root directory of the repository.



# How to create Docker Image and run the docker container.

* Fork the repository and clone the git repository to your localmachine using the following command.


         git clone https://github.com/vishnu4b3/node-hello.git

* How to create docker image.

         docker build -t pvishnu/node-hello:tagname

         
* How to push the docker image to Docker registry.

         docker login
         docker push pvishnu/node-hello:tagname
         
* how to run the Docker container in your local machine.

         docker run -it --name nodehello -p 8000:3000 pvishnu/nodehello:tagname
         
* You can access the node-hello app from the browser using the following URL.

         https://localhost:8000
 
 
 
 # To create the docker container using ansible pleaybook.
 
  # Prerequisites:
*   Have to install the Ansible on you machine.
*   Docker also have to install on your machine. 
*   above mentined playbook wil create the docker container on local machine only. 

# How to create the Docker container using Ansible playbook.

* pleas download this repository to you manchine using git Clone command.


         git clone https://github.com/vishnu4b3/node-hello.git


*   Change from your current directoy to node-hello directory and to spin up the container run the following command.

         ansible-playbook dockerplaybook.yaml  
         
**Note:** Above mentined playbook will create the docker container on local machine only.






