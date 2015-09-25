# vagrant-mesos-ansible

Mesos cluster provisioned by Ansible which runs on Vagrant (Virtualbox).

Basically, it is a result config after walking through [Recreating the Cluster Using Ansible](https://open.mesosphere.com/advanced-course/deploying-a-web-app-using-docker/) guide.

Differences from the guide:

* Mesos-DNS service starts automatically on master node
* `resolv.conf` is not overwritten after node restart
* Event subscription is enabled in Marathon.
* Vagrant VM box version is fixed to 2.2.1
* `oyter` is not included

`apps` folder contains configuration files for Marathon apps. I run them using REST API, e.g.
```http POST http://192.168.33.10:8080/v2/apps < apps/mongo_webapp.json```
