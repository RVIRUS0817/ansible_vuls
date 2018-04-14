# ansible_vuls

https://github.com/RVIRUS0817/security-automation-with-ansible-2  

![download-security-automation-with-ansible-2-leverage-ansible-2-to-automate-complex-security-tasks-like-application-security-network-security-and-malware-analysis-ebooks-textbooks-1-638](https://user-images.githubusercontent.com/5633085/38729162-07f179b2-3f4d-11e8-9752-fc3c489f6cb0.jpg)

Validating!!! coming soon!

## Environment

・Docker for Mac 18.04.0-ce-mac62 (23965)/edge  
・ansible -v2.5.0  
・ubuntu-vuls(vuls docker)  

## 1.setting Docker for Mac Daemon

![2018-04-14 22 32 33](https://user-images.githubusercontent.com/5633085/38768794-dea64082-4033-11e8-9b91-f9da82d8e893.jpg)


## 2.docker pull 

https://hub.docker.com/r/tvirus17/ansible-vuls_ubuntu16/

```
$ docker pull tvirus17/ansible-vuls_ubuntu16
```

## 3.docker run

```
$ docker run -p 22:22 -h "ubuntu-vuls" -e TZ=Asia/Tokyo --privileged -d --name ubuntu-vuls tvirus17/ansible-vuls_ubuntu16 /sbin/init
```

## 4.setting ssh

```
root@ubuntu:~# mkdir .ssh
root@ubuntu:~# chmod 700 .ssh/
root@ubuntu:~# cd .ssh/
root@ubuntu:~/.ssh# vim authorized_keys
root@ubuntu:~/.ssh# chmod 600 authorized_keys

```

## 5.ansible run

```
$ ansible-playbook -i inventory main.yml
```

