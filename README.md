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

**Anonymous Directory**
mkdir /home/resources/
chmod 777 /home/resources/
chowown nobody:group /home/resources/

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
    comment = Samba for username 
    path = /home/username/sambashare
    writable = yes
    read only = no
    browsable = yes
    valid users = username
    quest ok = no
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