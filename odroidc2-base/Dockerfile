FROM quay.io/costoolkit/examples:odroid-c2-latest

RUN zypper in -y wireless-tools \
                 wpa_supplicant \
                 NetworkManager \
                 iw \
                 iproute2 \
                 aaa_base-extras \
                 iputils \
                 kmod \
                 libudev1 \
                 vim-small \
                 tmux \
                 zsh \
                 kernel-firmware-all && \
    zypper cc

RUN systemctl disable wicked
RUN systemctl enable NetworkManager

RUN mkinitrd
