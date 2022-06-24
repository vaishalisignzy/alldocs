# Configuration steps

The first step of the installation process is to configure the required parameters for **** the DB server, App server, and webserver.

We recommend running the configuration for all the layers - DB / App / Web - together since some of the config parameters might be common. For example - the setup requires the IPs of the DB servers and the same also needs to be put in the connection string in the app server configurations.

Once you are done providing the configuration values, the tool presents you a summary of all the config values that have been set. If you feel there is something wrong, please make sure you correct it by re-running the configuration step before proceeding with the installation step.

Inside the signzy-setup-tool directory, you’ll find certain scripts present. Ensure you are in the correct directory. As an example, you’ll see a file like `db_creds_setup.sh` .

**Signzy Signzy product uses docker to run the application. Ensure that you are running the mentioned commands using the root user or a user in which docker commands can execute. If your user does not have the relevant permissions, you’ll see the following error.**

`Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get http://%2Fvar%2Frun%2Fdocker.sock/v1.40/containers/aes/json: dial unix /var/run/docker.sock: connect: permission denied`

### Configuring Database Servers \[MongoDB] <a href="#h.4alvnurb7k0s" id="h.4alvnurb7k0s"></a>

Signzy’s products use MongoDB as the primary database and MongoDB can be set up in both standalone as well as cluster setup.

* Run the below command to initiate the setup of the database. This file enables you to set up and configure the credentials for your database environment.

```bash
$ bash db_creds_setup.sh
```

You’ll be asked the below questions which are explained in more detail.

* Please enter the DB Root Password !!
  * When prompted to provide the database’s administrator password, please provide one. Ensure that you provide a strong password and also remember it as it might be needed later on during maintenance activities. Admin passwords are meant only for administrative and maintenance purposes and are not used for running the application.
* Please enter a password for Read-Write User !!
  * Next is to provide a Read & Write password for your database. This password is different from the Admin password and is used by the applications to actually use the database. Ensure strength and remember for later configs as well.
* Please enter the number of Database Servers(1 or 3) !!
  * You are required to select whether you want to set up a standalone database server or a cluster setup. Cluster setup is recommended to have better fault tolerance
* Please enter the IP address for the DB Server !!
  * If you select Standalone setup (1 server), you will need to provide the IP of the DB server. In case of a cluster setup, you’ll be needed to provide three IPs for your DB servers. _\[One of the three should be selected as a primary server during installation & other two as secondary server]._
    * For the standalone setup, choose 1.
    * For cluster setup, you are only provided the option to set up 3 servers as of now. Post choosing cluster setup, you are required to provide the three IPs for the three servers.
  * Once you have provided all the values in the above steps your screen should look something like the below.

Example output in your terminal for a stand-alone database setup

```bash
----------- Hi. Let's start with the Database Setup!! -----------
----------- Please enter the DB Root Password!! -----------
ExampleStrongPasswordan34qi34
----------- Please enter a password for Read-Write User!! -----------
ExampleOfAnotherStrongPassword2342qv5m
----------- Please enter the number of Database Servers(1 or 3) !! -----------
1
----------- Please enter the IP address for the DB Server!! -----------
10.0.0.1
Unable to find image 'docker.signzy.tech/aes-encrypt:v1' locally
v1: Pulling from aes-encrypt
1c6172af85ee: Pull complete
b194b0e3c928: Pull complete
1f5ec00f35d5: Pull complete
93b1353672b6: Pull complete
3d7f38db3cca: Downloading [===============================================> ] 204.4MB/214.9MB
3d7f38db3cca: Pull complete
21e102f9fe89: Pull complete
1f9c0020f4f4: Pull complete
5ab83c758454: Pull complete
654868f0dc71: Pull complete
33b40725a3d9: Pull complete
Digest: sha256:b933e59931f66f965f85e0cb8a13f470e3c34052587a9428097dbb86db0d5fe8
Status: Downloaded newer image for docker.signzy.tech/aes-encrypt:v1
063d2ec63791ef379ad5e5b4d07065a723b9049b84ccab258a22c06a913523b6
aes
```

Example output in your terminal for a Cluster (3 nodes) database setup

```bash
----------- Hi. Let's start with the Database Setup!! -----------
----------- Please enter the DB Root Password!! -----------
ExampleStrongPasswordan34qi34
----------- Please enter a password for Read-Write User!! -----------
ExampleOfAnotherStrongPassword2342qv5m
----------- Please enter the number of Database Servers(1 or 3) !! -----------
3
------ Creating a replica set !!! -------
----------- Please enter the IP address for the first DB Server!! -----------
10.0.0.1
----------- Please enter the IP address for the Second DB Server!! -----------
10.0.0.2
----------- Please enter the IP address for the Third DB Server!! -----------
10.0.0.3
Unable to find image 'docker.signzy.tech/aes-encrypt:v1' locally
v1: Pulling from aes-encrypt
1c6172af85ee: Pull complete
b194b0e3c928: Pull complete
1f5ec00f35d5: Pull complete
93b1353672b6: Pull complete
3d7f38db3cca: Downloading [===============================================> ] 204.4MB/214.9MB
3d7f38db3cca: Pull complete
21e102f9fe89: Pull complete
1f9c0020f4f4: Pull complete
5ab83c758454: Pull complete
654868f0dc71: Pull complete
33b40725a3d9: Pull complete
Digest: sha256:b933e59931f66f965f85e0cb8a13f470e3c34052587a9428097dbb86db0d5fe8
Status: Downloaded newer image for docker.signzy.tech/aes-encrypt:v1
063d2ec63791ef379ad5e5b4d07065a723b9049b84ccab258a22c06a913523b6
aes
```

### Configuring Database Servers \[Rabbit MQ] <a href="#h.g87votrew49r" id="h.g87votrew49r"></a>

Along with the database servers, you shall also be required to set up the RabbitMQ which is used as a message queue for multiple applications.

* To start the configuration of the Rabbit MQ servers, run the below command.

```bash
$ bash db_creds_setup.sh
```

* Please enter the number of Rq Servers(1 or 3) !!
  * Here you have to enter whether you’re setting up a RabbitMQ cluster or a standalone RabbitMQ service. If you are going for one server enter **1** and if you’re going for a 3-node RabbitMQ cluster, enter **3.**
* Please enter the IP address for the Rq Server !!
  * Here you have to enter the IP address of your RabbitMQ server. Make sure the port whitelisting is done from the app server to the MQ server. Refer to the requirement doc for port whitelisting information.

Example output in your terminal for a stand-alone RabbitMQ setup.

```bash
----------- Hi. Let's start with the RabbitMq Setup!! -----------
----------- Please enter the number of Rq Servers(1 or 3) !! -----------
1
----------- Please enter the IP address for the Rq Server!! -----------
10.0.0.1
Example output in your terminal for a Cluster (3 node) RabbitMQ setup
----------- Hi. Let's start with the RabbitMq Setup!! -----------
----------- Please enter the number of Rq Servers(1 or 3) !! -----------
3
------ Creating a RabbitmQ Cluster !!! -------
----------- Please enter the IP address for the first RMQ Server!! -----------
10.0.0.1
----------- Please enter the IP address for the Second RMQ Server!! -----------
10.0.0.2
----------- Please enter the IP address for the Third RMQ Server!! -----------
10.0.0.3
```

### Configuring the Application Servers <a href="#h.ngok7yvv0wa0" id="h.ngok7yvv0wa0"></a>

The above commands that you have run while configuring the database servers, have also configured for your application servers. For example, the passwords set for database servers also lead to the setting of DB connection strings in the docker-compose files of both application and the database servers.

You don’t need to execute any additional configurations for application servers now.

### Configuring the Webserver <a href="#h.3cqhenrb9tk4" id="h.3cqhenrb9tk4"></a>

Once the configuration of the application layer is completed, we are ready to configure the webserver.

* To configure the webserver, go to the docker-files directory and then go to the webserver directory.

```bash
$ cd docker-files
$ cd webserver
```

Replace the bundled certificate and the key you have obtained from your Certification Authority (CA). The certificate should be replaced into the file ssl-bundle.crt and the key should be replaced to the file ssl.key. To understand more about the certificates, refer to [Basic pre-requisite information](https://sites.google.com/signzy.com/dev-docs/on-prem/basic-prerequisite-information?authuser=0). Please ensure that the certificate is a valid Nginx certificate, as per

* Once the certificate is placed correctly. run the below command to start the configuration of the Nginx server.

```bash
$ bash nginxsetup.sh <your-top-level-domain>
```

The top-level domain is used to create subdomains as well. For example, if you enter signzy.com as the TLD, the subdomains like vkyc.signzy.com and go-admin-dashboard.signzy.com will automatically get setup.

The script would ask for IPs of application servers and configure them in web server configuration files.

* Please enter the No. of GO app servers!!
  * This value is essentially the number of application server nodes that you are planning to set up. For UAT this value would be 1 unless you are planning for fault tolerance setup. However, for production, you are recommended to set up at least 2 application servers.
* Please enter the No. of VCIP app servers!!
  * Same as above question
* Please enter the No. of Video Manager servers!!
  * Same as above question
* The Ip addresses of the GO app servers to be given one by one according to the no. of servers answered in question 1.
* The Ip addresses of the VCIP app servers to be given one by one according to the no. of servers answered in question 2.
* The Ip addresses of the Video Manager servers to be given one by one according to the no. of servers answered in question 3.

**Example of a single application server setup**

```bash
----------- Hi. Let's start with the Nginx Setup!! -----------
----------- Please enter the No. of GO app servers!! -----------
1
----------- Please enter the No. of VCIP app servers!! -----------
1
----------- Please enter the No. of Video Manager servers!! -----------
1
---------- Please enter the IP address for the GO App1 Server!! -----------
10.0.0.1
---------- Please enter the IP address for the VCIP App1 Server!! -----------
10.0.0.2
---------- Please enter the IP address for the Video Manager App1 Server!! -----------
10.0.0.3
```

**Example of a multiple server setup**

```bash
----------- Hi. Let's start with the Nginx Setup!! -----------
----------- Please enter the No. of GO app servers!! -----------
1
----------- Please enter the No. of VCIP app servers!! -----------
2
----------- Please enter the No. of Video Manager servers!! -----------
3
---------- Please enter the IP address for the GO App1 Server!! -----------
10.0.0.1
---------- Please enter the IP address for the VCIP App1 Server!! -----------
10.0.0.1
---------- Please enter the IP address for the VCIP App2 Server!! -----------
10.0.0.2
---------- Please enter the IP address for the Video Manager App1 Server!! -----------
10.0.0.1
---------- Please enter the IP address for the Video Manager App2 Server!! -----------
10.0.0.2
---------- Please enter the IP address for the Video Manager App3 Server!! -----------
10.0.0.3
```

* Once the script finishes, copy the whole webserver directory to each of your web layer servers.
* On each of the web servers, you are required to run the below command

```bash
$ docker-compose up -d
```

Please ensure you are inside the webserver directory when running this command.
