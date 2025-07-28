# License satrio (c) 2025
# By using fish-bucket, you must agree to our Privacy and terms for using our software. 


FROM debian:bullseye-slim

LABEL version="1.0.0"

# INSTALL DEPS
RUN apt update && apt upgrade && apt install -y \
  wget curl unzip bash git ca-certificates && \
  useradd -m obscat && \
  mkdir -p /home/obscat && \
  chown -R obscat:obscat /home/obscat && \
  apt clean

# Change Workdir
WORKDIR /home/obscat

# Copy and chmod entrypoint
COPY entrypoint.sh /entrypint.sh
RUN chmod +x /entrypoint.sh

# login user
USER obscat

# Exposed port
EXPOSE 25565
#entrypoint
ENTRYPOINT ["/entrypoint.sh"]
