# Use the official Ubuntu as the base image
FROM ubuntu:latest

# Update package sources and install necessary tools
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y wget gpg

# Download HashiCorp GPG key and add it to the keyring
RUN wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

# Add the HashiCorp repository to the sources list (replace `bionic` with the correct distribution codename)
RUN echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com bionic main" | tee /etc/apt/sources.list.d/hashicorp.list

# Update package sources and install Nomad
RUN apt-get update && apt-get install -y nomad

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Start a bash shell when the container runs
CMD ["/bin/bash"]
