ARG VARIANT=20-bullseye
FROM mcr.microsoft.com/devcontainers/typescript-node:1-${VARIANT}
ENV DEBIAN_FRONTEND=noninteractive \
    DOTNET_CLI_TELEMETRY_OPTOUT=1

# Install dotnet 8.0
RUN apt-get update \
    # Install prerequisites
    && apt-get install -y --no-install-recommends \
    wget \
    ca-certificates \
    \
    # Install Microsoft package feed
    && wget -q https://packages.microsoft.com/config/debian/12/packages-microsoft-prod.deb -O packages-microsoft-prod.deb \
    && dpkg -i packages-microsoft-prod.deb \
    && rm packages-microsoft-prod.deb \
    \
    # Install .NET
    && apt-get update \
    && apt-get install -y --no-install-recommends \
    # dotnet-runtime-8.0 \
    dotnet-sdk-8.0
USER node