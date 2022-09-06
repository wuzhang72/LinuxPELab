FROM ubuntu:latest

# install openssh server
RUN apt update && apt install openssh-server -y

# install packages
RUN apt install sudo zip -y

# add "test" user
RUN useradd -ms /bin/bash test

# set password for "test" user
RUN echo 'test:test' | chpasswd

RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/zip /tmp/backup.zip /opt/data/*" >> /etc/sudoers

RUN mkdir /opt/data

# start SSH service
RUN service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]
