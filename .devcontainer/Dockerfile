# Loosely based on this blog post:
# https://www.modular.com/blog/how-to-setup-a-mojo-development-environment-with-docker-containers

FROM mcr.microsoft.com/devcontainers/base:ubuntu-22.04

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:deadsnakes/ppa && \
    apt-get update && \
    apt-get install -y \
        python3 python3-pip python3-venv python3.12 \
        llvm

ARG MODULAR_AUTH_TOKEN
ENV MODULAR_HOME="/home/vscode/.modular"
ENV PATH="$PATH:$MODULAR_HOME/pkg/packages.modular.com_mojo/bin"
RUN curl https://get.modular.com | sh - && \
    modular auth $MODULAR_AUTH_TOKEN && \
    modular install mojo
