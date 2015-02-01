---
layout: post
title:  "Setup a server for your rails app."
date:   2014-12-24 19:40:00
categories: rails
tags: featured
image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.jpg
---

## Does it have to be so painful ?

You just got a brand new server with a classic linux distro on it, but what should you do next to get it ready for a rails app deploiment ?

In this article, I will cover the installation of differents neddeed softwares and users, and I'll cover the deploiement of a rails app in another article.

You can install most softwares with the `root` user, like this :

```
apt-get install mongodb redis-server postgresql imagemagick git
```

But it's probably a bad idea to use the system ruby version. I use rbenv as a version manager, on both my desktop and server.

I use the same user to deploy and run tha applications. As a convention the user name is so `deploy`.

Logged as `root` on your server, do :

```
useradd -m -g staff -s /bin/bash deploy
mkdir /home/deploy/.ssh
chown -R deploy:nogroup /home/deploy/.ssh
```

Deploy's home will host our rails projects in the future.

At this point, you probable want to copy your ssh key in the `.ssh` folder, so as to be able to connect with ssh.

Do you have a ssh key setup on your desktop ?

```
cat ~/.ssh/id_rsa.pub
```

if the command doesn't output something, you probably don't.

# TODO generate key

# TODO copy paste key in deploy ssh folder

# TODO connect with deploy via ssh

# TODO install rbenv