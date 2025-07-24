
# 🛠️ Jenkins on Ubuntu using Vagrant, VirtualBox and Ansible

This project provisions a Jenkins server on Ubuntu 20.04 LTS (`ubuntu/focal64`) using Vagrant, VirtualBox, and Ansible.

---

## ✅ Prerequisites

- **VirtualBox**: version **7.0.20**
- **Vagrant**: version **2.4.1**

Make sure both are installed on your host machine.

---

## 📦 Project overview

- Uses the public Vagrant box: `ubuntu/focal64` (Ubuntu 20.04 LTS)
- Sets a **fixed private IP** for Jenkins: `192.168.56.10`
- Installs **Ansible** directly on the guest VM
- Ansible runs a playbook that:
  - Installs **Docker**
  - Pulls and starts the official **Jenkins Docker container**
- Exposes Jenkins on: [http://192.168.56.10:8080](http://192.168.56.10:8080)

---

## 🚀 How to run


    git clone https://github.com/val7304/vagrant-jenkins.git
    $ cd vagrant-jenkins
    $ vagrant up

    $ vagrant ssh
    # retrieve token:
    $ sudo docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword

Go to 192.168.56.10:8080 to launch Jenkins, paste the token  to access on it