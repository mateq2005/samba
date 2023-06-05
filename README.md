# Samba

### Installing Samba

```
sudo apt update
sudo apt install samba
```

```
sudo ufw allow samba
```

```
whereis samba
```

### Setting up Samba

**Specific User**
```
mkdir /home/username/sambashare/
chmod 777 /home/username/sambashare/
chowown nobody:nogroup /home/username/sambashare/
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

```
sudo service smbd restart
```



```
sudo adduser username
sudo smbpasswd -a username
```

### Connecting to Share

<img src="smb.png">