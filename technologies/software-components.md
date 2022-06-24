# Software components

Signzy on premise products are deployed as containerised applications. Docker containers are compiled, tested and security hardened to form deployable docker images. All infrastructure is horizontally scaled through pods and extension of new infrastructure happends through addition of new pods.

Each pod is a final comiled images with all relevant dependencies and prerequisites preinstalled. Running an application through a pod is essentially three steps.

1. Procure the latest container image of the application from Signzy distribution hub
2. Start the containers through scripts
3. Execute monitoring scripts provided with installation instructions.

Following are the major components of software that come installed in your docker containers filtered by particular software's requirements.

| Item                                       | Type                 | Source      | Application          | Licence 1                                                                                                                                          |
| ------------------------------------------ | -------------------- | ----------- | -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ubuntu Server (ubuntu 16.04/18.04)         | Operating system     | Open source | OS                   | [GPL](http://www.gnu.org/copyleft/gpl.html)                                                                                                        |
| Python                                     | Programming language | Open source | Processor unit, API  | [http://opencv.org/license.html](http://opencv.org/license.html)                                                                                   |
| NodeJS                                     | Programming language | Open source | API                  | [https://github.com/nodejs/node/blob/master/LICENSE](https://github.com/nodejs/node/blob/master/LICENSE)                                           |
| PHP                                        | Programming language | Open source | Queue consumer       | [http://php.net/license/index.php](http://php.net/license/index.php)                                                                               |
| Elastic search/logstash/Kibana (ELK stack) | Database             | Open source | Data store           | [https://www.elastic.co/guide/en/shield/current/license-management.html](https://www.elastic.co/guide/en/shield/current/license-management.html)   |
| Kafka                                      | Framework            | Open source | Upload queue         | [https://github.com/kafka-dev/kafka/blob/master/LICENSE](https://github.com/kafka-dev/kafka/blob/master/LICENSE)                                   |
| Python Computer vision (openCV)            | Framework            | Open source | Processor unit       | [http://opencv.org/license.html](http://opencv.org/license.html)                                                                                   |
| Nagios                                     | Library              | Opensource  | Server monitoring    | [https://www.nagios.com/legal/licenses/](https://www.nagios.com/legal/licenses/)                                                                   |
| Telegraf                                   | Tool                 | Opensource  | Server monitoring    | [https://github.com/influxdata/telegraf/blob/master/LICENSE](https://github.com/influxdata/telegraf/blob/master/LICENSE)                           |
| Nginx                                      | Software             | Opensource  | Web server           | [https://github.com/nginx/nginx/blob/master/docs/text/LICENSE](https://github.com/nginx/nginx/blob/master/docs/text/LICENSE)                       |
| Loopback                                   | Framework            | Opensource  | File upload          | [https://github.com/strongloop/loopback/blob/master/LICENSE](https://github.com/strongloop/loopback/blob/master/LICENSE)                           |
| Tensorflow                                 | Tool                 | Opensource  | Modelling & training | [https://github.com/tensorflow/tensorflow/blob/master/LICENSE](https://github.com/tensorflow/tensorflow/blob/master/LICENSE)                       |
| Theano                                     | Tool                 | Opensource  | Modelling & training | [http://deeplearning.net/software/theano/LICENSE.html](http://deeplearning.net/software/theano/LICENSE.html)                                       |
| Java                                       | Tool                 | Opensource  | Programming language | [http://deeplearning.net/software/theano/LICENSE.html](http://deeplearning.net/software/theano/LICENSE.html)                                       |
| Jmeter                                     | Tool                 | Opensource  | Performance testing  | [http://svn.apache.org/repos/asf/jmeter/tags/v2\_4/docs/license.html](http://svn.apache.org/repos/asf/jmeter/tags/v2\_4/docs/license.html)         |
| Git                                        | Tool                 | Opensource  | Version control      |                                                                                                                                                    |
| Docker                                     | Tool                 | Opensource  | Image deployment     | [https://www.docker.com/legal/docker-software-end-user-license-agreement](https://www.docker.com/legal/docker-software-end-user-license-agreement) |
| MySQL                                      | Database             | Opensource  | Clustered database   | [https://www.mysql.com/about/legal/](https://www.mysql.com/about/legal/)                                                                           |
| MongoDB                                    | Database             | Opensource  | Clustered database   | [https://www.mongodb.com/community/licensing](https://www.mongodb.com/community/licensing)                                                         |



