# Samba Setup (Ubuntu File Sharing)

## Install Samba

```
sudo apt install samba -y
```

## Create Shared Folder
```
mkdir -p /home/f12r/output
sudo chown -R f12r:f12r /home/f12r/output
sudo chmod -R 770 /home/f12r/output
```

## Add Samba User
```
sudo smbpasswd -a f12r
```
## Configure Share
```
sudo nano /etc/samba/smb.conf
```

Add at bottom:
```
[OutputShare]
   path = /home/f12r/output
   browseable = yes
   read only = no
   writable = yes
   valid users = f12r
   create mask = 0770
   directory mask = 0770
```
Restart:
```
sudo systemctl restart smbd
```

## Access Instructions

Windows:

```
\\192.168.100.179\OutputShare
```

Linux/macOS:
```
smb://192.168.100.179/OutputShare
```


## Common Errors
❌ zsh: no such file or directory

Do NOT run smb:// in terminal.
Use file manager.

❌ permission denied

Check:
```
ls -l /home/f12r/output
```
Fix:
```
sudo chmod -R 770 /home/f12r/output
```
