FROM quay.io/costoolkit/examples:odroid-c2-latest

RUN zypper ar -G https://download.opensuse.org/repositories/devel:/ARM:/Factory:/Contrib:/OdroidC2/standard/devel:ARM:Factory:Contrib:OdroidC2.repo
RUN zypper ref
RUN zypper in -y wireless-tools \
                 wpa_supplicant \
                 NetworkManager \
                 iw \
                 iproute2 \
                 dtb-amlogic \
                 aaa_base-extras \
                 odroidc2-firmware \
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