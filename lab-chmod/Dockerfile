FROM ubuntu:latest

# install openssh server
RUN apt update && apt install openssh-server -y

# install packages
RUN apt install sudo -y

# add "test" user
RUN useradd -ms /bin/bash test

# set password for "test" user
RUN echo 'test:test' | chpasswd

RUN mkdir -p /backup/data

RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/chmod" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/chmod a+w /backup/data/*" >> /etc/sudoers

# start SSH service
RUN service ssh start

EXPOSE 22

ENTRYPOINT /usr/sbin/sshd -D
