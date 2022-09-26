FROM ubuntu:latest

# install openssh server
RUN apt update && apt install openssh-server -y

# add "test" user
RUN useradd -ms /bin/bash test

# set password for "test" user
RUN echo 'test:test' | chpasswd

RUN chmod a+w /etc/passwd

# start SSH service
RUN service ssh start

EXPOSE 22

ENTRYPOINT /usr/sbin/sshd -D
