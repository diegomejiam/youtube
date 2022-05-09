Cómo configurar una ip estática y la zona horaria en Ubuntu server 20.04

-- INSTRUCCIONES --
Configurar una dirección ip estatica en ubuntu 20.04 a través de netplan:

sudo nano /etc/cloud/cloud.cfg.d/subiquity-disable-cloudinit-networking.cfg
network: {config: disabled}

sudo nano /etc/netplan/00-installer-config.yaml

network:
  version: 2
  ethernets:
    ens33:
      addresses: [192.168.20.160/24]
      gateway4: 192.168.20.2
      nameservers:
        addresses: [192.168.20.2, 8.8.8.8]
 
sudo netplan apply

Configurar nuestra nuestra hora, zona horaria y fecha
sudo dpkg-reconfigure tzdata
