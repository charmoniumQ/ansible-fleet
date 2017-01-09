# Provision AWS server

- Install Debian Jessie on a t2.nano
- Open port 80, 22, and 443 to the world
- Give an 8GB EBS root volume store
- Assign elastic IP

# Post initial

- Configure local ~/.ssh/config to connect by default with user sam (but -l admin)

# Debops

    debops bootstrap --limit main --user admin --become
    debops common --limit main --become
    debops samgrayson --limit main --become

# Post install
- Give a 10GB EBS store mounted on /var/www/nextcloud

pki-authority: Error: failed to run ca -batch -notext -in /home/sam/box/dev/ansible-fleet/ansible/secret/pki/requests/domain/main.samgrayson.me/samgrayson.me/request.pem -out /home/sam/box/dev/ansible-fleet/ansible/secret/pki/realms/by-host/main.samgrayson.me/samgrayson.me/internal/cert.pem.tmp -config config/openssl-sign.conf (Exitcode: 1)

Details:
Using configuration from config/openssl-sign.conf
/home/sam/box/dev/ansible-fleet/ansible/secret/pki/realms/by-host/main.samgrayson.me/samgrayson.me/internal/cert.pem.tmp: No such file or directory
139706500957848:error:02001002:system library:fopen:No such file or directory:bio/bss_file.c:255:fopen('/home/sam/box/dev/ansible-fleet/ansible/secret/pki/realms/by-host/main.samgrayson.me/samgrayson.me/internal/cert.pem.tmp', 'w')
139706500957848:error:20074002:BIO routines:FILE_CTRL:system lib:bio/bss_file.c:257:
