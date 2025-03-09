# Start from a Node.js base image
FROM node:23-slim AS dev_container_base

# Install Hugo and other dependencies
RUN apt-get update && apt-get install -y \
    hugo \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Download the standalone Tailwind CSS CLI (for Linux x64)
#RUN curl -sLO https://github.com/tailwindlabs/tailwindcss/releases/latest/download/tailwindcss-linux-x64 \
#    && chmod +x tailwindcss-linux-x64 \
#    && mv tailwindcss-linux-x64 /usr/local/bin/tailwindcss

# Install tailwindcss with cli globally
RUN npm install -g tailwindcss @tailwindcss/cli

# Set the working directory
WORKDIR /workspace/hugo-start

# Create vscode user with a home directory
RUN useradd -m vscode

# Switch to the vscode user
USER vscode

# Set the default command to run when the container starts
CMD ["bash"]
