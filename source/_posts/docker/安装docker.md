---
title: 安装docker
---

 489  yum install -y yum-utils   device-mapper-persistent-data \
  490  yum install -y yum-utils  device-mapper-persistent-data lvm2
  491  yum-config-manager   --add-repo  https://download.docker.com/linux/centos/docker-ce.repo
  492  yum-config-manager --enable docker-ce-nightly
  493  yum-config-manager --enable docker-ce-test
  494  yum install docker-ce docker-ce-cli containerd.io
  495  yum list docker-ce --showduplicates | sort -r
  496  yum install -y docker-ce-18.03.0.ce-1.el7.centos containerd.io
  497  yum install -y docker-ce-18.06.1.ce docker-ce-cli-18.06.1.ce containerd.io
  498  systemctl start docker