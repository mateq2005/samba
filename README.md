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

```
mkdir /home/username/sambashare/
chmod 777 /home/username/sambashare/
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

### Setting up User Accounts and Connecting to Share

```
sudo adduser username
sudo smbpasswd -a username
```

<img src="smb.png">