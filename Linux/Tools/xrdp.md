## Optimize

- Turning Animations off in Ubuntu: gsettings set org.gnome.desktop.interface enable-animations false
- Turn Off UI Animations in Ubuntu: 
- Reduce the number of colors that XRDP has to transmit: sudo sed -i 's/max_bpp=32/max_bpp=16/g' /etc/xrdp/xrdp.ini && sudo reboot
- Disables encryption, which can improve performance by reducing the CPU usage on the server: set `crypt_level` to `none`

## Reference
- https://devicetests.com/speeding-up-xrdp-ubuntu-20-04-xorg-tips-tricks#disabling-compositing
- https://www.youtube.com/watch?v=gPsOcE1yw5I