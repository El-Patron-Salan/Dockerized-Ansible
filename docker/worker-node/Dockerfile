FROM alpine:latest

RUN apk add --update --no-cache \
        openrc \
        openssh \
        iputils \
        && echo 'root:hello' | chpasswd \
        && ssh-keygen -A \
        && sed -i 's/#PermitRootLogin.*/PermitRootLogin yes/' /etc/ssh/sshd_config \
        && mkdir -p /run/openrc \
        && touch /run/openrc/softlevel

EXPOSE 22

ENTRYPOINT ["sh", "-c", "rc-status; rc-service sshd restart"]
