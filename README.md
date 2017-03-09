# Jenkins_Docker

## What is Jenkins?

* Jenkins is a software that allows continuous integration.

* Jenkins will be installed on a server where the central build will take place.

* Along with Jenkins, sometimes, one might also see the association of Hudson.

* Hudson is a very popular open-source Java-based continuous integration tool developed by Sun Microsystems which was later acquired by Oracle.

* After the acquisition of Sun by Oracle, a fork was created from the Hudson source code, which brought about the introduction of Jenkins.

## What is Continuous Integration?

* Continuous Integration is a development practice that requires developers to integrate code into a shared repository at regular intervals. 

* This concept was meant to remove the problem of finding later occurrence of issues in the build lifecycle.

## What id Docker?

* Docker is an open platform for developing, shipping, and running applications.

* Docker enables you to separate your applications from your infrastructure so you can deliver software quickly.

* With Docker, you can manage your infrastructure in the same ways you manage your applications.

* By taking advantage of Docker’s methodologies for shipping, testing, and deploying code quickly, you can significantly reduce the delay between writing code and running it in production.

## What can I use Docker for?

* Fast, consistent delivery of your applications.

* Responsive deployment and scaling.

* Running more workloads on the same hardware.

## Integration of Docker and Jenkins :

* First we need to set up Docker by installing docker on Jenkin's server.

* To avoid running Docker in sudo mode, you must add the "jenkins" user in the "docker" group.

```
sudo groupadd docker
```

```
sudo gpasswd -a Jenkins docker 
```

```
sudo service docker restart
```

* If You want to give the root access to your jenkins user, you need to change the permission in sudoers file in unix. 

* Path for sudoers file (/etc/sudoers).

* Build the docker image

```
docker build -t imagename:${BUILD_NUMBER} .
```

* Run the Script using Docker image

```
docker run --rm -e BROWSER=browser -v $(pwd)/local/test:/container/test -v $(pwd)local_/scripts:/container/scripts -v $(pwd)/local_path_results:/container_path_results imagename:${BUILD_NUMBER}
```

## References for Integration of Docker and Jenkins:

[Jenkins and Docker Integration](http://www.therightcode.net/use-docker-jenkins-to-run-github-tests/)