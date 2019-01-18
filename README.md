# Docker Swarm

## Step By Step
- Clone Repo
  ```shell
  git clone https://github.com/vfarcic/docker-swarm.git
  cd docker-swarm
  vagrant up
  ```
- Fix ansible exexution permission (Windows User Only)

  If you run into issues with ansible complaining about executable permissions, try modifying the `Vagrantfile`'s `synced_folder` entry from this:
  ```ruby
  config.vm.synced_folder ".", "/vagrant"
  ```
  to this:
  ```ruby
  config.vm.synced_folder ".", "/vagrant", mount_options: [“dmode=700,fmode=600″]
  ```
- Connect to Master and Ansible
  ```shell
  vagrant ssh swarm-master
  ansible-playbook /vagrant/ansible/infra.yml -i /vagrant/ansible/hosts/prod
  ```

----
This repository contains code used in the **Scaling To Infinity with Docker Swarm, Docker Compose and Consul** article series:

* [A Taste of What Is To Come](http://technologyconversations.com/2015/07/02/scaling-to-infinity-with-docker-swarm-docker-compose-and-consul-part-14-a-taste-of-what-is-to-come/)
* [Manually Deploying Services](http://technologyconversations.com/2015/07/02/scaling-to-infinity-with-docker-swarm-docker-compose-and-consul-part-24-manually-deploying-services/)
* [Blue-Green Deployment, Automation and Self-Healing Procedure](http://technologyconversations.com/2015/07/02/scaling-to-infinity-with-docker-swarm-docker-compose-and-consul-part-34-blue-green-deployment-automation-and-self-healing-procedure/)
* [Scaling Individual Services](http://technologyconversations.com/2015/07/02/scaling-to-infinity-with-docker-swarm-docker-compose-and-consul-part-44-scaling-individual-services/)

