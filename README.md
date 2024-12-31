Project Architecture Diagram
![HTML Architecture Diagram](https://github.com/user-attachments/assets/49e05364-c201-43a7-a8cf-1db96e7954af)



Steps to Deploy an HTML Template with Docker and Push to Docker Hub
Step 1: Launch an Ubuntu-based Instance
1.	Open the AWS EC2 service.
2.	Launch an instance with the name Docker.
3.	Configure the security group to allow: 
o	HTTP at port 80
o	Custom TCP at port 8080
o	SSH at port 22
4.	Connect to the instance using SSH.

Step 2: Create a Docker Hub Account
1.	Search for Docker Hub on Google or visit: Docker Hub.
2.	Sign up using a Google or GitHub account.
3.	Remember your username and password for later use.

Step 3: Create a Repository in Docker Hub
1.	After signing in, click on Repositories.
2.	Click on Create repository.
3.	Fill in the repository name, short description, and set visibility (public or private).
4.	Click Create to finalize the repository.

Step 4: Install Docker on Ubuntu
1.	Search for install Docker on Ubuntu and follow the documentation at: Install Docker.
2.	Download the installation script: 
sudo su -
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
service docker start
3.	Switch to the root user using sudo su.

Step 5: Login to Docker
1.	Run the command: 
docker login
2.	Enter your Docker Hub username and password.

Step 6: Create and Run a Tomcat-based Container
1.	Run the Tomcat container: 
docker run -itd -p 8080:8080 tomcat
docker ps

Step 7: Download and Deploy an HTML Template
Step 7.1: Download the HTML Template
1.	Visit Tooplate to choose an HTML template.
2.	Download the template but pause the download to copy the link address.

Step 7.2: Deploy the HTML Template
1.	Create a directory and navigate into it: 
mkdir mydir
cd mydir
2.	Install unzip: 
apt-get update
apt-get install unzip
docker commit <container_id> mykool
3.	Download the template using wget: 
wget <template_link>
4.	Change directory to Tomcat's webapps folder: 

cd /var/lib/docker/overlay2/<container_id>/merged/usr/local/tomcat/webapps
mkdir ROOT
5.	Unzip the downloaded template: 
unzip -o <downloaded_template.zip>
cp -rf * /var/lib/docker/overlay2/<container_id>/merged/usr/local/tomcat/webapps/ROOTStep 8: Check if it Works
1.	Open the AWS EC2 instance page.
2.	Copy the public IP address of the Docker instance.
3.	Access the application via your browser at: 
http://<public_ip>:8080

Step 9: Push the Image to Docker Hub
1.	Tag the image: 
Docker  tag  <your_dockerhub_username>/dockerrepo
2.	Push the image: 
docker push <your_dockerhub_username>/dockerrepo

Step 10: Check in Docker Hub Repo
1.	Open Docker Hub and navigate to your repositories.
2.	Click on Tags to verify the uploaded image.Step 11: Terminate the Instance
exit
1.	Go to the EC2 instances page.
2.	Select the Docker instance and click on Instance State > Terminate.
_____________________<img width="960" alt="2024-12-31 (9)" src="https://github.com/user-attachments/assets/4598e5eb-1cd6-412a-a086-8a89ffbd327d" />
___________________
<img width="960" alt="2024-12-31 (10)" src="https://github.com/user-attachments/assets/0604927b-dbfa-498e-a9d0-76961f5e01a6" />

<img width="960" alt="2024-12-31 (15)" src="https://github.com/user-attachments/assets/8485a3d6-57ca-44a3-846f-c6f6a67fbfe7" />

By following these steps, you will successfully deploy an HTML template using Docker and push it to your Docker Hub account.

<img width="960" alt="2024-12-31 (14)" src="https://github.com/user-attachments/assets/dc0385f3-12cb-4ac2-b5fd-1d9e1adebbc9" />
