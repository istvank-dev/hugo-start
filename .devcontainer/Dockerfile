# Start from a Node.js base image
FROM node:16-buster AS dev_container_base

# Install Hugo and other dependencies
RUN apt-get update && apt-get install -y \
    hugo \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Install TailwindCSS globally
RUN npm install -g tailwindcss

# Create vscode user with a home directory
RUN useradd -m vscode

# Set the working directory
WORKDIR /workspace

# Switch to the vscode user
USER vscode

# Set the default command to run when the container starts
CMD ["bash"]
