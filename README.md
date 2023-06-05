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
```
mkdir /home/resources/
chmod 777 /home/resources/
chowown nobody:nogroup /home/resources/
```

```
sudo nano /etc/samba/smb.conf
```

```
[resources]
    comment = Samba for everyone 
    path = /home/resources/
    writable = yes
    browsable = yes
    quest ok = yes
```

**Specific User**
```
mkdir /home/username/
chmod 777 /home/username/
chowown username /home/username/
```

```
sudo nano /etc/samba/smb.conf
```

```
[username]
    comment = Samba for username 
    path = /home/username/
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

**Specific Group**
```
mkdir /home/group/
chmod 777 /home/group/
chowown nobody:group /home/group/
```

```
sudo nano /etc/samba/smb.conf
```

```
[group]
    comment = Samba for group 
    path = /home/group/
    writable = yes
    browsable = yes
    quest ok = no
    valid users = @group
```

### 3. Resetting Samba

```
sudo service smbd restart
```