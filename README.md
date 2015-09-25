docker-wso2is
===================

Docker image to install and run WSO2 Identity Server. It uses the [dockerfile/java](https://index.docker.io/u/dockerfile/java/) as its base image.


The dockerfile will:

* Use `wget` to pull the Identity Server 5.0.0 ZIP and SP1 from WSO2 web server into the container `/opt` folder.
* Check the zips with sha256sum.
* Install `zip`.
* Unzip the ZIPs.
* Apply SP1 patch.
* Remove the ZIPs.
* Expose the container port `9443`.
* Set the Identity Servce `wso2server.sh` start-up script as the container start-up command.

### Usage
* To pull: `docker pull bastiaanb/wso2is`
* To build: `docker build --rm -t your_image_name github.com/bastiaanb/docker-wso2is`
* To run: `docker run --rm --name your_container_name -p 9443:9443 your_image_name`
* To access Identity Server web admin console, navigate to `https://localhost:9443`

