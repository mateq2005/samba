# Samba

### 1. Installing Samba

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

### 2. Setting up Samba

**Specific User**
```
mkdir /home/username/sambashare/
chmod 777 /home/username/sambashare/
chowown username /home/username/sambashare/
```

```
sudo nano /etc/samba/smb.conf
```

```
[sambashare]
    comment = Samba on Ubuntu
    path = /home/username/sambashare
    writable = yes
    read only = no
    browsable = yes
```

```
sudo adduser username
sudo smbpasswd -a username
```

### 3. Resetting Samba

```
sudo service smbd restart
```

### 4. Connecting to Share

<img src="smb.png">