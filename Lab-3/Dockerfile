FROM ubuntu:latest

# install openssh server
RUN apt update && apt install openssh-server -y

# install packages
RUN apt install sudo vim nmap zip -y

# add "test" user
RUN useradd -ms /bin/bash test

# set password for "test" user
RUN echo 'test:test' | chpasswd


RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/bash" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/su" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/vim" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/apt-get" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/chmod" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/cp" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/python3" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/ssh" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/nmap" >> /etc/sudoers
RUN echo "test ALL=(ALL) NOPASSWD: /usr/bin/zip" >> /etc/sudoers

# start SSH service
RUN service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]
