# Basic prerequisite information

Clients are required to ensure certain prerequisites for running the application are available or else the installation or the post installation product may fail. Below sections list the requirements.

#### Components provided out of the box <a href="#h.y510gflg739j" id="h.y510gflg739j"></a>

Signzy provides the below listed components as part of each product’s on-premise packages. Please ensure you have each of the below components handy with you before initiating the installation procedure for your product.

1. Link to **official docker website** for download and installation of docker daemon and docker CLI client.
   1. Clients are required to download the relevant image from the official link and install on each of the servers that are expected to host Signzy’s product and like web, app and DB servers.
   2. Official link to download docker images is : [https://www.docker.com/products/docker-desktop](https://www.google.com/url?q=https%3A%2F%2Fwww.docker.com%2Fproducts%2Fdocker-desktop\&sa=D\&sntz=1\&usg=AFQjCNEhaFBl99-ceI9Wt0LvHWRi-eVBmQ)
2. Links to **images on the Signzy’s private docker registry** (hosted at [https://docker.signzy.tech](https://www.google.com/url?q=https%3A%2F%2Fdocker.signzy.tech\&sa=D\&sntz=1\&usg=AFQjCNGcaoJru2Aj31M8pBlN6wtFvZ6OSg))
   1. Eg. docker.signzy.tech/generic-onboarding-tag-v1.2.2
3. Client specific **credentials to access Signzy’s docker registry**.
4. **Product documentations:**
   1. Product specific installation documentation
      1. Eg. docker installation documentation for Video KYC or generic onboarding products
   2. Block architecture diagram
   3. Network diagram
   4. Standard deployment diagram
   5. Product’s user manual
5. Relevant **configuration files and setup scripts**. Eg. docker-compose-vkyc-db.yml
   1. Refer the specific product’s documentation for exact details.

#### Security controls <a href="#h.pl5kq7bbzrzh" id="h.pl5kq7bbzrzh"></a>

All the docker images provided by Signzy are pre-hardened images of relevant software. For an instance, each image of the operating system used on the web, app or DB servers is hardened with Signzy’s internal security guidelines which is derived from global recommendations. The applications are compiled into the docker images for delivery to clients post Vulnerability Assessment of the environment and the Penetration Testing of the application are conducted.

Clients can request to avail the VAPT conducted by Signzy’s internal infosec team and empanelled 3rd party VAPT providers if required.

#### Port openings within infrastructure <a href="#h.qpduxu8ua6jt" id="h.qpduxu8ua6jt"></a>

The product follows a 3 tier architecture, and provides installables for web servers, app servers and the DB servers. Signzy provides the specified list of ports (source and destination servers along with destination ports) in the specific product instructions.

_Please ensure that the mentioned ports are opened according to specs provided in product’s document. Failure to do so will result in connectivity failure and the product will not work._

__

| **Source Server** | **Destination Server** | **Destination port** | Protocol    |
| ----------------- | ---------------------- | -------------------- | ----------- |
| **Web**           | **App**                | **53001-53020**      | **TCP**     |
| **App**           | **DB**                 | **51903**            | **TCP**     |
| **App**           | **DB**                 | **51904**            | **TCP**     |
| **App**           | **DB**                 | **51905**            | **TCP**     |
| **App**           | **DB**                 | **51906**            | **TCP**     |
| **App**           | **DB**                 | **51912**            | **TCP**     |
| **App**           | **Web**                | **80**               | **TCP**     |
| **App**           | **Web**                | **443**              | **TCP**     |
| **App**           | **RabbitMQ**           | **5672**             | **TCP**     |
| **0.0.0.0/0**     | **Media Streamer**     | **10021**            | **UDP**     |
| **0.0.0.0/0**     | **Media Streamer**     | **10022**            | **UDP**     |
| **0.0.0.0/0**     | **Video Manager**      | **3478**             | **TCP/UDP** |
| **0.0.0.0/0**     | **Web**                | **443**              | **TCP**     |
| **0.0.0.0/0**     | **Web**                | **80**               | **TCP**     |

#### Port openings outside the infrastructure <a href="#h.7frri9v1j273" id="h.7frri9v1j273"></a>

Signzy’s on premise product also needs to connect with the Signzy cloud hosted AI services for processes like extraction of documents, forgery detection etc. In order to do so, the on premise deployed product also shall connect with our APIs hosted at [https://signzy.tech](https://www.google.com/url?q=https%3A%2F%2Fsignzy.tech\&sa=D\&sntz=1\&usg=AFQjCNFEcniRwyJPVSqyKaaxXvlXVFXzMQ) for production and [https://preproduction.signzy.tech](https://www.google.com/url?q=https%3A%2F%2Fpreproduction.signzy.tech\&sa=D\&sntz=1\&usg=AFQjCNFKMqzCj9iimTMNTOnfB\_asG4T5dw) for the UAT (pre-production) environment.

#### SSL certificate <a href="#h.u808ag2k9s7t" id="h.u808ag2k9s7t"></a>

The web layer requires an SSL certificate for running. Signzy product supports only HTTPs on port 443. Hence clients are required to avail a valid SSL certificate from a reputed Root CA, however Signzy product can work with any provider’s certificate provided the key and the certificate chain are valid.

Following two files are required to be configured into web server setup:

1. Der encoded certificate file (.crt) containing the entire certificate chain. Below command is used to set the system up.
2. Key file (.key file)

```
$ cat your_domain.crt intermediate.crt root.crt >> ssl-bundle.crt
```

Refer to the product’s specific document to understand how to configure the SSL certificate into the YAML files.

Sometimes, the certificates are downloaded in the form of .pfx files. If you have a .pfx file, you’ll be needed to extract the certificate and key from the pfx file so it can be imported into the web server. This can ne done by using a tool like portecle, [http://portecle.sourceforge.net/](http://www.google.com/url?q=http%3A%2F%2Fportecle.sourceforge.net%2F\&sa=D\&sntz=1\&usg=AFQjCNFHYrwQIYSlylzGKaQYTMaXziKhFw) .

#### Operating system <a href="#h.7hzx828uqmgj" id="h.7hzx828uqmgj"></a>

Signzy product is based on docker images and hence can run on all the operating systems that support docker daemon and docker

#### VMs / Boxes for deployment <a href="#h.l6f4gqj3cbuy" id="h.l6f4gqj3cbuy"></a>

Signzy shall provide the box sizing for the mentioned volumes, basis which client is expected to procure the machines. The box sizing shall be provided in the below format.

Please note the below table contains the tentative numbers and is meant to be only for understanding. The actual numbers for your product may vary and you would receive the mentioned servers from your Signzy POC.

![](https://lh3.googleusercontent.com/IAAgVnTAZ2FIzrsz6aWdn8hZTUN5LzO0HPHSn1NLVjYkx9nAFtwpqh12RhonHQJ25ew6IMLRQlqX4vxcNWMNvBU97B5mqgJsGetdTHhpS\_0nPVGYvYQtTxGaTlqUL5PEEw=w1280)

**Description and disclaimer.**

* &#x20;The estimates of infrastructure is derived from the shared volumes
* The disk space on DB layer to store the files in distributed file system will vary if more documents than initially planned need to be stored
* DB layer disk space is recommended to be on an LVM, so that mounting to increase disk space could be efficiently executed. The number mentioned here is for storing files for up to 1 year.
* The numbers mentioned here are using standard mathematical predictions and might vary upon actual load testing.&#x20;
* Signzy assumes all disks are SSD drives and the operating system installed is Ubuntu 18.04.
