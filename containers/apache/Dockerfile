FROM httpd:latest

RUN apt-get update -y

RUN apt install openssh-server vim -y

COPY sshd_config /etc/ssh/sshd_config

RUN groupadd sftp_users

RUN useradd sftp

RUN usermod -G sftp_users sftp

RUN echo "sftp:sftp" |  chpasswd

RUN mkdir /SFTP

RUN mkdir /SFTP/sftp

RUN chown sftp:sftp_users /SFTP/sftp

RUN service ssh start

EXPOSE 22