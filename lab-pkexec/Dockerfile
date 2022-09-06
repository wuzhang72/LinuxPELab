FROM ubuntu:20.04

# install openssh server
RUN apt update && apt install-y openssh-server

# install vulnerable PwnKit
RUN apt install -y libpolkit-gobject-1-0=0.105-26ubuntu1 libpolkit-agent-1-0=0.105-26ubuntu1 policykit-1=0.105-26ubuntu1

# install gcc
RUN apt install -y gcc

# add "test" user
RUN useradd -ms /bin/bash test

# set password for "test" user
RUN echo 'test:test' | chpasswd

# start SSH service
RUN service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]
