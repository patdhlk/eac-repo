# Use the same base image as the devcontainer
FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu24.04

# Install necessary packages using a single RUN command to optimize layers
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        default-jre \
        graphviz \
        cmake \
    && rm -rf /var/lib/apt/lists/*


# Install Rye and set up the environment
# The `--yes` option is included to mirror the script's behavior
RUN curl -sSf https://rye-up.com/get | RYE_INSTALL_OPTION="--yes" bash
#RUN mv /root/.rye /home/vscode/.rye

#RUN echo 'source "/home/vscode/.rye/env"' >> /home/vscode/.bashrc
#ENV PATH="$PATH:/home/vscode/.rye/env"
# Set the default working directory and user
WORKDIR /workspace
USER vscode



