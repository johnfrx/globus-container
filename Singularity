Bootstrap: docker
From: centos:latest

%runscript
    exec echo "Centos7 image for use with globus"


%post
    #echo "The post section is where you can install, and configure your container."
    #
    yum -y update && yum -y install epel-release openssl openssl-dev
    yum -y install git wget bzip2 aria2
    yum -y install tmux atop dstat
    yum -y install yum-utils
    #
    # Install the globus repo
    mkdir -p /etc/pki/rpm-gpg
    mkdir -p /data 
    wget https://downloads.globus.org/toolkit/gt6/stable/repo/rpm/RPM-GPG-KEY-Globus -O /etc/pki/rpm-gpg/RPM-GPG-KEY-Globus
    yum-config-manager --add-repo https://downloads.globus.org/toolkit/gt6/stable/repo/rpm/globus-toolkit-6-stable-el7.repo
    yum-config-manager --enable Globus-Toolkit-6-el7
    yum install -y globus-gridftp
    yum install -y vim
