# Common problems for on-premise solutions



### Problems identified during on-premise deployment & infrastructure

1. Internet is unavailable
   1. For installing corresponding dependencies and product pre-requisites
2. Port connectivity is bad & unstable
3. Releasing different components differently becomes a problem
4. Metering is difficult when connectivity to Signzy system isn’t present & we don’t have a common solution to the same.
5. Connectivity to the servers isn’t efficient and stable and varies.
   1. Which makes it difficult to get into the servers to execute something
6. Clients always have questions on the technologies we are using which are answered by our tech team and client is convinced.
   1. Example what database you are using and can you use a DB that let’s say bank provides.
   2. What language is getting used
   3. How does the DC/DR replication happening in each of the technologies.
7. The servers instances provided might not be of the specification we ask form
   1. For example, SSDs aren’t provided
   2. CPU GHz might be different than what has been asked for.
8. How to solve any issue faced by client which is actually in the code.
9. How to not show the third party dependencies.
10. Even when connectivity to the internet is present, How to insure client will not tweak into metering logic, because the code is available at his end.
11. System Dependencies used by some microservice, which client system may not have permission to install.
12. AI services infra usage is high and correspondingly needs to be provided by client which can create issue.
