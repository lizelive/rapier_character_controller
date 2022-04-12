# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.231.5/containers/rust/.devcontainer/base.Dockerfile

# [Choice] Debian OS version (use bullseye on local arm64/Apple Silicon): buster, bullseye
ARG VARIANT="bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/rust:0-${VARIANT}




# [Optional] Uncomment this section to install additional packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends x11-apps libasound2-dev libxrandr2 libxi-dev libx11-xcb1 freeglut3-dev \
#     libxau6 libxdmcp6 libxcb1 libxext6 libx11-6 \
#     libglvnd0 libgl1 libglx0 libegl1 libgles2 \
#     libglvnd-dev libgl1-mesa-dev libegl1-mesa-dev libgles2-mesa-dev \
#     libglx-dev libgl1-mesa-glx libgl1-mesa-dri mesa-utils \
#     vulkan-tools libvulkan1 mesa-vulkan-drivers \
#     libx11-xcb-dev libxkbcommon-dev libwayland-dev libxrandr-dev libegl1-mesa-dev \
#     pulseaudio
RUN rm -f /etc/apt/apt.conf.d/docker-clean

RUN --mount=type=cache,target=/var/cache/apt \
    apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    libx11-xcb-dev \
    libxkbcommon-dev \
    libwayland-dev \
    libxrandr-dev \
    libegl1-mesa-dev \
    vulkan-tools \
    && rm -rf /var/lib/apt/lists/*


ENV NVIDIA_DRIVER_CAPABILITIES graphics

# FROM nvidia/vulkan:1.2.170-470


# RUN TEMP_SCRIPT="$(mktemp --suffix=.deb)" \
#     && curl -O "$TEMP_SCRIPT" https://raw.githubusercontent.com/microsoft/vscode-dev-containers/main/script-library/common-debian.sh \
#     && chmod +x "$TEMP_SCRIPT" \
#     && $TEMP_SCRIPT \
#     && rm -f "$TEMP_SCRIPT"