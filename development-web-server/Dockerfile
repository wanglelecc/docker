FROM debian:stretch-slim

MAINTAINER wanglelecc <wanglelecc@gmail.com>

LABEL Description="This image is the base os images."  Version="1.0"

ENV NOTVISIBLE "in users profile"

RUN apt-get update \
&& apt-get install -y wget \
    curl \
    vim \
    openssh-server \
    pwgen \
    --no-install-recommends \
&& mkdir /var/run/sshd \
&& echo 'root:123456' | chpasswd \
&& sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config \
&& sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd \
&& sed -i "s/UsePAM yes/#UsePAM yes/g" /etc/ssh/sshd_config \
&& echo "export VISIBLE=now" >> /etc/profile \
&& apt-get autoremove -y \
&& rm -rf /var/lib/apt/lists/* \
&& mkdir /home/src \
&& cd /home/src

EXPOSE 80 443 21 22 3306 6379 11211

CMD ["/usr/sbin/sshd", "-D"]