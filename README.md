# Samba

Installing Samba

```
sudo apt-get update
sudo apt-get install samba -y
```

```
systemctl start smbd 
systemctl enable smbd
systemctl status smbd 
```

### Setting up Samba

**Anonymous Directory**
```
mkdir /home/resources/
chmod -R 777 /home/resources/
chowown -R nobody:nogroup /home/resources/
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
    guest ok = yes
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
    guest ok = no
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
    guest ok = no
    valid users = @group
```

### Resetting Samba

```
sudo systemctl restart smbd
```

*tested*
