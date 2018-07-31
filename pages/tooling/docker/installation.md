# Docker Installation


## Installation

Install Docker on your system:

[Mac OS](https://docs.docker.com/docker-for-mac/install/): https://docs.docker.com/docker-for-mac/install/

[Windows](https://docs.docker.com/docker-for-windows/install/): https://docs.docker.com/docker-for-windows/install/

[Linux](https://docs.docker.com/install): https://docs.docker.com/install

If you are on windows and do not have Git bash installed you will need to additionally install that:
https://gitforwindows.org/

The underlying operation of docker depends on the platform/version that you are using, the most crucial difference is between using the docker machine and running natively. 
The main way that this will effect your usage will be in the IP that the environments will be presented upon. For the docker machine it will be presented on an IP, with a native 
docker implementation the environments will be presented on localhost.

This means that the IP that will need to be put into /etc/hosts will differ based on your machine, but will likely be one of either:

 	- 192.168.99.100
 	- 127.0.0.1


If you are using a docker-machine then during the boot stage of the machine should print out the IP, if not it can be found via `docker-machine ip`. If you are not using the docker-machine :sunglasses: then the IP will be localhost: 127.0.0.1