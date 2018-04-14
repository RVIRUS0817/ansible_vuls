# ansible_vuls

https://github.com/RVIRUS0817/security-automation-with-ansible-2  

![download-security-automation-with-ansible-2-leverage-ansible-2-to-automate-complex-security-tasks-like-application-security-network-security-and-malware-analysis-ebooks-textbooks-1-638](https://user-images.githubusercontent.com/5633085/38729162-07f179b2-3f4d-11e8-9752-fc3c489f6cb0.jpg)

Validating!!! coming soon!

## 1.docker pull 

https://hub.docker.com/r/tvirus17/ansible-vuls_ubuntu16/

```
$ docker pull tvirus17/ansible-vuls_ubuntu16
```

## 2.docker run

```
$ docker run -p 22:22 -h "ubuntu-vuls" -e TZ=Asia/Tokyo --privileged -d --name ubuntu-vuls tvirus17/ansible-vuls_ubuntu16 /sbin/init
```

## 3.setting ssh

```
root@ubuntu:~# mkdir .ssh
root@ubuntu:~# chmod 700 .ssh/
root@ubuntu:~# cd .ssh/
root@ubuntu:~/.ssh# vim authorized_keys
root@ubuntu:~/.ssh# chmod 600 authorized_keys

```

## 4.Docker for Mac setting

