# ansible_vuls

![new-9781788394512_copy](https://user-images.githubusercontent.com/5633085/38768975-62c9b3ce-4036-11e8-9584-1210228b4207.png)

https://github.com/RVIRUS0817/security-automation-with-ansible-2  

It is a repository that automates the construction of Vuls server, scan and report with ansible while looking at security-automation-with-ansible-2!


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

