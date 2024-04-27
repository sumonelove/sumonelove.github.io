---
title: Create  Own git server 
---

[I] Create user Name git

    useradd -m git -d /var/git -s (any shell bin path)

[II] Setup passwd of git user

     sudo passwd git

[III] Copy ssh pub key from already exist user or set your own
 
    cp -r .ssh /git user home dir path...

    (***)See the authorized_keys file Content

[IV] Make git user normal user to root user

     sudo usermod -aG sudo git

[V] Give Permissions and Change Ownership of .ssh dir

    sudo chmod 700 .ssh && sudo chmod 600 authorized_keys

    sudo chown git .ssh && sudo chown git .ssh/authorized_keys

[VI] Add user or group of in /usr/ssh/sshd_config file allowuser or allowgroups  *username

     sudo usermod -aG ssh-access *user_name 

     vim /etc/ssh/sshd_config 

[VI] rstart the sshd deamon

     service sshd restart

[VI] Create Bare Repo for Git server

     git init --bare /projects/*.git

[VII] push and ferch url

      git remote add (remote name) git@hostname:projects/*.git

      Now you can push and Fetch the repo using thie url

  URL:git@hostname:projects/*git


       
