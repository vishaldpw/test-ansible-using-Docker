FROM ubuntu:20.04

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies
RUN apt-get update && \
    apt-get install -y openssh-server sudo && \
    apt-get clean

# Create a user
RUN useradd -m target && \
    echo "target:target" | chpasswd && \
    echo "target ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

# Enable SSH
RUN mkdir /var/run/sshd
EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
