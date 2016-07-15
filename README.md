# run external docker registry in vagrant (with x509/Basic Authentication)

* required
```
	- install vagrant 4.3
	https://www.virtualbox.org/wiki/Download_Old_Builds_4_3
	http://download.virtualbox.org/virtualbox/4.3.34/VirtualBox-4.3.34-104062-OSX.dmg
	cf. vagrant box add ubuntu/trusty64
		vagrant box add precise64 http://files.vagrantup.com/precise64.box
```

* run		
```
	bash build.sh
```	
	
* workflow
```
	1. make cert before making vagrant VMs (x509/Basic Authentication for docker registry)
	2. make docker registry VM (registry.sh)
		update certs
		install docker
		make test docker image
		install nginx
		make docker-registry / domain-registry
		push test image to external server with https
	3. make client registry VM (client.sh)
		update certs
		install docker
		pull test image from external server with https
```

* check out docker client
```
	http://192.168.82.171:8080/
	Username: admin Password: shipyard
```

* Running Docker Trusted Registry in AWS
```
	https://www.youtube.com/watch?v=t7yQPbfvYvs
```