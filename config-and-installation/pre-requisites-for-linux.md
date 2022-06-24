# Pre-requisites for linux

Signzy’s products can be set up in a Debian or CentOS based linux distribution that has a shell script runner installed by default. Follow the below instructions to install the software on the Linux environment.

### Installing docker <a href="#h.vye1nasl6drp" id="h.vye1nasl6drp"></a>

Docker provides very good documentation on how to install docker based on your Operating System. You can follow [the documentation here](https://www.google.com/url?q=https%3A%2F%2Fdocs.docker.com%2Fget-docker%2F\&sa=D\&sntz=1\&usg=AFQjCNGJd5XHuwmda77amUeBaKluPF\_aNA). The installation steps presented below have been directly taken from Docker Guide with no modification.

> Warning
>
> If you are not able to connect to the docker website, you will have to connect to your infrastructure team in order to avail access or request their support to install the docker runtime into your servers.

Docker runtime is required to run Signzy's product.

Follow the below instructions to install docker in your environment.

* Update the apt package index and install the below packages

```
sudo apt-get update


sudo apt-get install \

    apt-transport-https \

    ca-certificates \

    curl \

    gnupg-agent \

    software-properties-common
```

* Add Docker official GPG key

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

* Use the following commands to setup the stable repository

```
udo add-apt-repository \

  "deb [arch=amd64] https://download.docker.com/linux/ubuntu \

  $(lsb_release -cs) \

  stable"
```

* Finally install Docker Engine

```
sudo apt-get update && sudo apt-get install docker-ce docker-ce-cli containerd.io
```

* Test the Docker by running docker --version command on your console/terminal. You should get a output like the below.

```
docker --version

Docker version 19.03.13, build cd8016b6bc
```

### Signzy’s private docker repository <a href="#h.40mszuaoipbl" id="h.40mszuaoipbl"></a>

Signzy provides a private docker registry for its clients to use. You will be required to connect to Signzy's private docker registry in order to pull the images and run the containers. The product’s installation manuals contain further information about the same. The easiest way by far is to simply run the docker-compose command at your relevant docker-compose.yml file. Here’s an example:

```
$ COMPOSE_DOCKER_CLI_BUILD=1 docker-compose -f <your-product-docker-compose.yml> 
```

But first of all you need to connect with Signzy private repository using the instructions below.

Signzy hosts a private docker repository at [https://docker.signzy.tech](https://www.google.com/url?q=https%3A%2F%2Fdocker.signzy.tech\&sa=D\&sntz=1\&usg=AFQjCNGcaoJru2Aj31M8pBlN6wtFvZ6OSg) .

Clients require to get connectivity to the docker registry endpoint mentioned above on the port number 443. Kindly connect with your infrastructure teams in order to get the same or get implemented in your existing installation mechanism.

Signzy’s docker registry endpoint: [https://docker.signzy.tech](https://www.google.com/url?q=https%3A%2F%2Fdocker.signzy.tech\&sa=D\&sntz=1\&usg=AFQjCNGcaoJru2Aj31M8pBlN6wtFvZ6OSg)

#### Logging into the private repository <a href="#h.7vobs3dbaep5" id="h.7vobs3dbaep5"></a>

Signzy provides a unique username and password to the client for connecting to the Signzy’s docker registry.

Once you have the access, you can run the docker commands.

Run the below command to login into Signzy's private docker registry. This command needs to be run as a root user or a user that has access to docker’s CLI client.

```
$ docker login docker.signzy.tech
```

If the user doesn’t have permission to use docker CLI, you’ll receive an error similar to the below.

```
Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post http://%2Fvar%2Frun%2Fdocker.sock/v1.40/auth: dial unix /var/run/docker.sock: connect: permission denied
```

In such a case, please switch to your docker user or use sudo command. Please connect with your infrastructure / OS provisioning team for further support.

Here’s how to use docker with sudo.

```
$ sudo docker login docker.signzy.tech
```

Once you run the above command, you’ll be prompted to provide your username and password. Please enter the credentials you received from Signzy in order to login

#### Pulling images & running the containers <a href="#h.nt3wg778oqa7" id="h.nt3wg778oqa7"></a>

Refer your product’s documentation to understand the mechanism of pulling the images and creating + running the containers.

#### Other points to note <a href="#h.8g11xrz26ng" id="h.8g11xrz26ng"></a>

* _You also need to decide on any further specifications that your company recommends, for example, setting up the DR servers in active-active or active-passive mode._
* _Please ensure to go through the “Before installation” section before installation of the system, as errors in this may mean that you’ll have to restart the installation process._

### Download the Signzy’s self installation toolkit <a href="#h.tornmj7772b" id="h.tornmj7772b"></a>

The tool is available in the zip format at below location.

https://docker.signzy.tech/files/share/signzy-self-setup-tool-v0.0.1.zip

To download the tool to your machine through the terminal, follow below steps. Create the directory and move inside the directory.

* Create separate directory for the toolkit execution

```
mkdir signzy-setup
cd signzy-setup
```

* Download the toolkit & unzip. Once prompted for password, please provide your password. The authentication here is same as the authentication you use for docker login.

```
wget 
https://docker.signzy.tech/files/share/signzy-self-setup-tool-v0.0.1.zip
 --user <your-docker-username> --ask-password
unzip signzy-self-setup-tool.zip
```

* Move inside the directory.

```
cd signzy-self-setup-tool
```

* To start the setup of the database, Run through the commands mentioned in the next sections. Choose the relevant option and answer the further questions. **Please ensure to configure all parameters correctly, and provide the values of parameters in configurations of different layers.** For example, the same Read Write user password shall be used in both the application and the Database server configurations.

