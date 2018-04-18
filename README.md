# Ubuntu cloud-init-data image for GNS3 virtual appliance

Generated using the following commands:
```
echo -e "#cloud-config\npassword: ubuntu\nchpasswd: { expire: False }\nssh_pwauth: True" > user-data
echo -e "instance-id: ubuntu\nlocal-hostname: ubuntu" > meta-data
mkisofs -output "ubuntu-cloud-init-data.iso" -volid cidata -joliet -rock {user-data,meta-data}
```
