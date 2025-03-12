# Use a lightweight base image with the necessary tools
FROM ubuntu:20.04

# Install dependencies
RUN apt-get update && apt-get install -y \
    wget \
    && rm -rf /var/lib/apt/lists/*

# Download nbminer
RUN wget https://github.com/NebuTech/NBMiner/releases/download/v40.1/nbminer_40.1_Linux.tgz && \
    tar -xvf nbminer_40.1_Linux.tgz && \
    mv nbminer_40.1_Linux /nbminer

# Set the working directory
WORKDIR /nbminer

# Set the command to run nbminer with the provided arguments
CMD ["./nbminer", "-a", "kawpow", "-o", "stratum+ssl://kp.unmineable.com:4444", "-u", "TRX:TGE79xhsj924ZdyULZKM4FTPagNEpn8n6f.unmineable_worker_esnpnb", "-log", "start"]
