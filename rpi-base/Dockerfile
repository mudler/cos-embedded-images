FROM quay.io/costoolkit/examples:rpi-554a9b96

RUN zypper ref
RUN zypper in -y wireless-tools \
                 wpa_supplicant \
                 NetworkManager \
                 iw \
                 iproute2 \
                 iputils \
                 kmod \
                 libudev1 \
                 vim-small \
		 docker-compose \
                 tmux \
                 zsh && \
    zypper cc

RUN systemctl disable wicked
RUN systemctl enable NetworkManager

RUN mkinitrd
