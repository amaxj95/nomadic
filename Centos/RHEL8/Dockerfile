# Use the official CentOS 8 as the base image
FROM centos:8

# Update the system and install necessary tools
RUN dnf -y update && \
    dnf -y install wget gnupg

# Download HashiCorp GPG key and add it to the keyring
RUN wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

# Add the HashiCorp repository to the sources list
RUN echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(rpm -E %rhel) main" | tee /etc/yum.repos.d/hashicorp.repo

# Install Nomad
RUN dnf -y install nomad

# Clean up
RUN dnf clean all && rm -rf /var/cache/dnf /tmp/* /var/tmp/*

# Start a bash shell when the container runs
CMD ["/bin/bash"]
