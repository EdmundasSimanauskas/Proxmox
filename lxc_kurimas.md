Konteinerio kurimas Proxmox
Atsiusti sablona:
pveam download local debian12-standart_12.0-1_amd64.tar.gz


Sukurti konteineri:
pct create 100 local:vztmpl/debian-12-standart_12.0-1_amd64.tar.gz \
--hostname mycontainer \
--cores 2 \
--memory 2048 \
-- swap 512 \
--net0 name=eth0, bridge=v,br0, ip=dhcp \
--onboot 1 \
--unprivileged 1 \
--rootfs local-lvm:8 \

Paleist konteineri:
pct start 100
ptc enter 100
