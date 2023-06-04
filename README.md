# Samba

### Installing Samba

```
sudo apt update
sudo apt install samba
```

```
whereis samba
```

### Setting up Samba

```
mkdir /home/username/sambashare/
```

```
sudo nano /etc/samba/smb.conf
```

```
[sambashare]
    comment = Samba on Ubuntu
    path = /home/username/sambashare
    read only = no
    browsable = yes
```