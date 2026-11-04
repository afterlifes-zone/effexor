FROM fedora:latest

RUN dnf install -y --setopt=install_weak_deps=False \
    openssh-server sudo passwd git curl wget which fastfetch nano \
    && dnf clean all \
    && ssh-keygen -A \
    && useradd -m -s /bin/bash codespace \
    && echo "codespace ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

RUN mkdir -p /var/run/sshd
EXPOSE 22

ENTRYPOINT ["/usr/sbin/sshd", "-D"]
