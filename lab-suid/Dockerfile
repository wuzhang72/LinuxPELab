FROM ubuntu:latest

# install openssh server
RUN apt update && apt install openssh-server -y

# install packages
RUN apt install csh cpulimit dash hping3 time zsh -y

# add "test" user
RUN useradd -ms /bin/bash test

# set password for "test" user
RUN echo 'test:test' | chpasswd

RUN chmod u+s /usr/bin/bash
RUN chmod u+s /usr/bin/chmod
RUN chmod u+s /usr/bin/cpulimit
RUN chmod u+s /usr/bin/csh
RUN chmod u+s /usr/bin/dash
RUN chmod u+s /usr/bin/find
RUN chmod u+s /usr/bin/python3
RUN chmod u+s /usr/bin/time
RUN chmod u+s /usr/bin/zsh
RUN chmod u+s /usr/sbin/hping3

# start SSH service
RUN service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]
