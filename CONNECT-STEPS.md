# Steps to connect to your EC2 instance

## 1. ✅ Key file added to project!
- Key file: ansibletestkey.pem
- Location: /mnt/windows-data/VScode/ansible/

## 2. Set permissions:
chmod 400 ansibletestkey.pem

## 3. Test connection:
ansible-playbook connect-test.yml

## Your EC2 Details:
- Instance: ec2-100-27-28-140.compute-1.amazonaws.com
- User: ec2-user
- Key: ansibletestkey.pem
