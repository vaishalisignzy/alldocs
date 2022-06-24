# Installation

### Running the database MongoDB <a href="#h.40ltryazpxww" id="h.40ltryazpxww"></a>

Once you have complete the steps mentioned in the configuration of MongoDB section, your configurations values are successfully updated in the below two files:

1. Docker-compose \[`docker-compose-db.yml`]
2. DB setup \[`db_setup.sh`] - This file shall be ran only on the primary node in case of a cluster setup.

On the database server, create a directory called mongo-docker-files and place the above files from the configuration server to the newly-created directory.

* Create the mongo directory and move inside the directory.

```
$ mkdir mongo-docker-files
$ cd mongo-docker-files
```

The above step \[Creation of mongo-docker-files directory and movement of the two files] is required to be done on all the database servers. So for the cluster setup, you’ll need to execute this step in all three servers.

#### Running a standalone setup <a href="#h.46qwe5l1krxu" id="h.46qwe5l1krxu"></a>

If you have chosen to run a standalone setup during the configuration of the database, you are required to run the below command on your database server. Ensure you are inside the directory which contains the docker-compose-db.yml and db\_setup.sh files.

```
$ bash db_setup.sh
```

#### Running a cluster setup of MongoDB <a href="#h.wgvjqg3fjqwt" id="h.wgvjqg3fjqwt"></a>

As a first step, you are required to choose 2 servers to be kept as secondary and 1 to be kept as primary. Once the installation is complete this primary election is automated and doesn’t need to be set up again

* On the 2 secondary servers run the below commands.

```
$ docker-compose -f docker-compose-db.yml up -d
```

* On the primary server run the below command. **Ensure that the secondary is up before running this command.**

```
$ bash db_setup.sh
```

Example output in your terminal after running the database.

```
Creating network "mongo_default" with the default driver
Creating Mongo_GO ... done
Creating Redis ... done
MongoDB shell version v4.2.10
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("779db982-d357-418c-ab0a-92c7d84dcacf") }
MongoDB server version: 4.2.10
switched to db admin
Successfully added user: { "user" : "mongoadmin", "roles" : [ "root" ] }
bye
MongoDB shell version v4.2.10
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("84d0d5d5-ea9e-497b-b163-ceef2d7f2dd4") }
MongoDB server version: 4.2.10
switched to db admin
Successfully added user: {
 "user" : "global-onboarding",
 "roles" : [
 {
 "role" : "readWrite",
 "db" : "global-onboarding"
 }
 ]
}
Successfully added user: {
 "user" : "rmProduct",
 "roles" : [
 {
 "role" : "readWrite",
 "db" : "rmProduct"
 }
 ]
}
Successfully added user: {
 "user" : "apiBlender",
 "roles" : [
 {
 "role" : "readWrite",
 "db" : "apiBlender"
 }
 ]
}
Successfully added user: {
 "user" : "persist",
 "roles" : [
 {
 "role" : "readWrite",
 "db" : "persist"
 }
 ]
}
Successfully added user: {
 "user" : "VideoConf",
 "roles" : [
 {
 "role" : "readWrite",
 "db" : "VideoConf"
 }
 ]
}
Successfully added user: {
 "user" : "vcip",
 "roles" : [
 {
 "role" : "readWrite",
 "db" : "vcip"
 }
 ]
}
bye
```

### Running Rabbitmq <a href="#h.qfjnz5buq9bn" id="h.qfjnz5buq9bn"></a>

The setup for RabbitMQ is similar to the setup of MongoDB mentioned above. You’ll see three files:

1. `Docker-compose-mq1.yml` - Useful for standalone as well as cluster setup.
2. `Docker-compose-mq2.yml` - only for cluster setup
3. `Docker-compose-mq3.yml` - only for cluster setup

#### Running a stand-alone setup <a href="#h.3i4z2he5tdqo" id="h.3i4z2he5tdqo"></a>

* Create a directory called rabbit-mq-docker on the server and place the docker-compose-mq1.yml file in it.

```
$ mkdir rabbit-mq-docker
$ cd rabbit-mq-docker
```

* Place the docker-compose-mq1.yml file into this directory & run the below command.

```
$ docker-compose -f docker-compose-mq1.yml up -d
```

#### Running a cluster setup of RabbitMQ <a href="#h.rbq2ms301r4l" id="h.rbq2ms301r4l"></a>

```
$ mkdir rabbit-mq-docker
$ cd rabbit-mq-docker
```

On each of the three servers place the relevant files and run docker-compose commands as mentioned below.

**Server 1**

Place docker-compose-mq1.yml into the rabbit-mq-docker directory. Then run:

```
$ docker-compose -f docker-compose-mq1.yml up -d
```

**Server 2**

Place docker-compose-mq2.yml into the rabbit-mq-docker directory. Then run:

```
$ docker-compose -f docker-compose-mq2.yml up -d
```

**Server 3**

Place docker-compose-mq3.yml into the rabbit-mq-docker directory. Then run:

```
$ docker-compose -f docker-compose-mq3.yml up -d
```

### Global-onboarding backend setup <a href="#h.1rn9ar4pzulc" id="h.1rn9ar4pzulc"></a>

* Create a directory called generic-onboarding-back-setup on each of the application servers where you wish to install global onboarding. Ensure that you have at least 15 GB of space available on the disk where you are creating global-onboarding-back-setup directory.

```
$ mkdir global-onboarding-back-setup
$ cd global-onboarding-back-setup
```

* From the docker-files directory, copy docker-compose-app.yml file to the generic-onboarding-back-setup directory on each of the relevant application servers.
* Once files are copied, run the below command to make the service up and running.

```
$ docker-compose -f docker-compose-app.yml up -d
```

* You should see an output as demonstrated below.

```
Creating network "global-onboarding_default" with the default driver
Creating global-onboarding_persist-onpremise_1 ... done
Creating global-onboarding_rule-engine_1 ... done
Creating global-onboarding_global-onboarding-back_1 ... done
Creating global-onboarding_global-onboarding-integration-layer_1 ... done
Creating global-onboarding_rm-backend_1 ... done
Creating global-onboarding_api-blender_1 ... done
```

* Post completion of docker-compose, run `docker ps` command to check the health of the containers, and see if the container services are created properly and are healthy

### Video KYC Backend setup <a href="#h.drfxr5ubkbd3" id="h.drfxr5ubkbd3"></a>

* Create a directory called video-kyc-setup on each of the application servers where you wish to install global onboarding. Ensure that you have at least 15 GB of space available on the disk where you are creating video-kyc-setup directory.

```
$ mkdir video-kyc-setup
$ cd video-kyc-setup
```

* From the docker-files directory, copy docker-compose-vcip.yml file to the video-kyc-setup directory on each of the relevant application servers.
* Once files are copied, run the below command to make the service up and running.

```
docker-compose -f docker-compose-vcip.yml up -d
```

* You should see an output as demonstrated below.

```
Creating network "vcip_default" with the default driver
Creating vcip_video-worker_1 ... done
Creating vcip_scheduling-backend_1 ... done
Creating vcip_signzy-messaging-service_1 ... done
Creating vcip_signzy-video-conference-backend_1 ... done
```

Post completion of docker-compose, run `docker ps` command to check the health of the containers, and see if the container services are created properly and are healthy
