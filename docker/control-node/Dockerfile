FROM alpine:latest

LABEL name="Ansible control node"

COPY remote-hosts.txt /tmp/

USER root
RUN apk add --update --no-cache \
        ansible \
        bash \
        openssh \
        openssh-client-common \
        iputils \
        && mkdir -p ~/.ssh \
        && ssh-keyscan -f /tmp/remote-hosts.txt >> ~/.ssh/known_hosts

EXPOSE 22
