FROM quay.io/costoolkit/examples:rpi-554a9b96

RUN zypper ref
RUN zypper in -y wireless-tools \
                 wpa_supplicant \
                 NetworkManager \
                 iw \
                 iproute2 \
                 iputils \
                 xf86-input-evdev \
                 kmod \
                 hostapd \
                 libudev1 \
                 vim-small \
		         docker-compose \
                 tmux \
                 zsh && \
    zypper cc

COPY ./config /etc/cos/config
COPY ./99-calibration.conf-35-90 /etc/X11/xorg.conf.d/99-calibration.conf
COPY ./99-fbturbo.conf /usr/share/X11/xorg.conf.d/99-fbturbo.conf
COPY ./tft35a-overlay.dtb /opt/tft35a-overlay.dtb
COPY ./setup.yaml /system/oem/tft.yaml
RUN systemctl disable wicked
RUN systemctl enable NetworkManager

RUN mkinitrd
