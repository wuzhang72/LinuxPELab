FROM ubuntu:latest

# install openssh server
RUN apt update && apt install openssh-server -y

# install packages
RUN apt install sudo -y

# add "test" user
RUN useradd -ms /bin/bash test

# set password for "test" user
RUN echo 'test:test' | chpasswd

RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/tar" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/tar cvvf backup.tar *" >> /etc/sudoers

# start SSH service
RUN service ssh start

EXPOSE 22

ENTRYPOINT /usr/sbin/sshd -D
