FROM ubuntu:latest

# install openssh server
RUN apt update && apt install openssh-server -y

# install packages
RUN apt install cron -y

# add "test" user
RUN useradd -ms /bin/bash test

# set password for "test" user
RUN echo 'test:test' | chpasswd

# set up cron jobs

RUN echo "*  *  *  *  * root /home/test/backup.sh" >> /etc/crontab
RUN echo "#" >> /etc/crontab

RUN crontab /etc/crontab

# start SSH service
RUN service ssh start

EXPOSE 22

ENTRYPOINT cron start && /usr/sbin/sshd -D

