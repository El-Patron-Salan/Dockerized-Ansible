FROM alpine:latest

LABEL name="Ansible control node"


COPY remote-hosts.txt /tmp/
RUN apk add --update --no-cache \
        ansible \
        bash \
        openssh \
        iputils \
        && mkdir -p .ssh \
        && ssh-keyscan -f /tmp/remote-hosts.txt >> .ssh/known_hosts

EXPOSE 22
