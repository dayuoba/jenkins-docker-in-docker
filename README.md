# A docker-in-docker jenkins Dockerfile

this is a Dockerfile wraps the jenkins, as the offical image does not deal with the solution of docker-in-docker pipeline, if you just run official image you will not be able to run docker jobs in pipeline

## Usage

clone this repo anywhere you'd like, run 

```Dockerfile
docker run -d --name jenkins \
	-p 8080:8080 -p 50000:50000 \ 
	-v /var/run/docker.sock:/var/run/docker.sock \
	-v jenkins_home:/var/lib/jenkins_home
	your_builded_image
```

## PS

* you should have docker installed on your host

* you should create a volume for this image like the `jenkins_home` above, whichhas be mentioned on the official doc

* if your host's docker version isn't compatible with the one in jenkins container you should change this Dockerfile to let it install the compatible docker version

## links
* [official doc](https://github.com/jenkinsci/docker/blob/master/README.md)

* [solution i searched](https://medium.com/@manav503/how-to-build-docker-images-inside-a-jenkins-container-d59944102f30)

