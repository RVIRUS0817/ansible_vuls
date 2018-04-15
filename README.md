# ansible_vuls

![2018-04-14 22 52 32](https://user-images.githubusercontent.com/5633085/38768987-911d2756-4036-11e8-8765-c3ae0afde3e1.jpg)

https://github.com/RVIRUS0817/security-automation-with-ansible-2  

It is a repository that automates the construction of Vuls server, scan and report with ansible while looking at security-automation-with-ansible-2!

## Install with Ansible(Vuls document)  

https://vuls.io/docs/en/install-with-ansible.html

## Environment

・Docker for Mac 18.04.0-ce-mac62 (23965)/edge  
・ansible -v2.5.0  

---

# vuls-server_build/  

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
$ docker exec -it xxxx /bin/bash
root@ubuntu-vuls:~# mkdir .ssh
root@ubuntu-vuls:~# chmod 700 .ssh/
root@ubuntu-vuls:~# cd .ssh/
root@ubuntu-vuls:~/.ssh# vim authorized_keys
root@ubuntu-vuls:~/.ssh# chmod 600 authorized_keys

$ ssh ubuntu-vuls
The authenticity of host 'localhost (127.0.0.1)' can't be established.
ECDSA key fingerprint is SHA256:vSxT14VBokw/dQUI9o0yudU4Jc2DNBF5395tG+JRR3Q.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'localhost' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 16.04.4 LTS (GNU/Linux 4.9.87-linuxkit-aufs x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

root@ubuntu-vuls:~# 

```

## 5.ansible run

```
$ ansible-playbook -i inventory main.yml
```
![2018-04-15 11 26 47](https://user-images.githubusercontent.com/5633085/38774273-efca4216-409f-11e8-997b-c446f0ee45e6.jpg)

```
root@ubuntu-vuls:~# docker images
REPOSITORY               TAG                 IMAGE ID            CREATED             SIZE
vuls/goval-dictionary    latest              256d630fc765        5 days ago          953MB
vuls/vuls                latest              9bc590ea71cf        5 days ago          1.49GB
vuls/go-cve-dictionary   latest              26be99fe513a        5 days ago          1.04GB

root@ubuntu-vuls:~# cd /vuls_data/
root@ubuntu-vuls:/vuls_data# ll
total 210592
drwxr-xr-x  4 root root      4096 Apr 15 09:54 ./
drwxr-xr-x 53 root root      4096 Apr 15 09:01 ../
-rw-r--r--  1 root root 162717696 Apr 15 09:37 cve.sqlite3
drwxr-xr-x  2 root root      4096 Apr 15 09:01 go-cve-dictionary-log/
drwxr-xr-x  2 root root      4096 Apr 15 09:38 goval-dictionary-log/
-rw-r--r--  1 root root  52903936 Apr 15 09:54 oval.sqlite3

```

-----

# vuls-scanning/  

coming soon...

