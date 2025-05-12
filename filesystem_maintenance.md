# Filesystem Maintenance

## mount

```bash
# DrvFs is the native way for mounting in WSL
sudo mount -t drvfs //abc.local/public /mnt/public
```

``` bash
# auto mounting in /etc/fstab
# no-fail prevents WSL from failing should the share not be available
# optionally no-auto can be added to prevent auto mounting
//abc.local/public /mnt/public drvfs nofail 0 0
```

```bash
# mounts a Windows (SMB/CIFS) network share located at //abc.local/public to the local directory /mnt/public using the credentials for user john.doe in the ABC domain. It uses SMB protocol version 3.02, sets file and directory permissions to be fully open (read/write/execute for all users), and ensures file names are encoded in UTF-8.
sudo mount -v //abc.local/public /mnt/public -o user=john.doe,domain=ABC,vers=3.02,iocharset=utf8,file_mode=0777,dir_mode=0777
```
### kinit, klist

Kerberos authentication.

```bash
# authenticate
kinit john.doe@ABC

# list tickets
klist
```
