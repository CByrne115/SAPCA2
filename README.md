## Setup

To use this project, you will need to create a Docker network and run a MySQL database and phpMyAdmin container. Follow the instructions below to get started.

### Create a Docker network

To create a new Docker network, run the following command:

	```sql
	docker network create my-network
	```


Replace `my-network` with the name you want to give your network.

### Run a MySQL database container 

To run a MySQL database container with the name `db` and a root password of `my-secret-password`, run the following command:

	```sql
	docker run -d --name db --network my-network -e MYSQL_ROOT_PASSWORD=my-secret-password mysql:latest
	```


Replace `my-network` with the name of the network you created in the previous step.

### Run phpMyAdmin container

To run the phpMyAdmin container on the Docker network you created, run the following command:

	```sql
	docker run -d --name phpmyadmin --network my-network -p 8080:80 phpmyadmin/phpmyadmin
	```


Replace `my-network` with the name of the network you created in the first step. This command will map port `8080` on your host machine to port `80` on the container. You can choose any port number you want to use.```





