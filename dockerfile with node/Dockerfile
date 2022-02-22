
FROM ubuntu:latest
RUN apt-get update && apt-get install openssh-server sudo -y 
RUN mkdir /var/run/sshd
RUN echo 'root:mypassword' | chpasswd
RUN sed -Ei 's/#(PermitRootLogin).+/\1 yes/' /etc/ssh/sshd_config
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd
RUN service ssh start
RUN sudo apt install nodejs
RUN mkdir node && cd node
RUN npm install express
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]   