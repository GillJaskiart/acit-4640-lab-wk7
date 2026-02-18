# Lab week 7

## 1. Create SSH Key Pair

Generate a new SSH key named `aws`:

```bash
ssh-keygen -t ed25519 -f ~/.ssh/aws -C "lab week 7"
```

`-t ed25519` → key type

`-f ~/.ssh/aws` → file name

This creates:

`~/.ssh/aws` (private key)

`~/.ssh/aws.pub` (public key)


## 2. Import SSH Key into AWS

Make the scripts executable:

```
chmod +x scripts/import_lab_key
chmod +x scripts/delete_lab_key
```


Run the script to upload the public key to AWS:

```
./scripts/import_lab_key ~/.ssh/aws.pub
```
This command runs the `import_lab_key` script


To remove the key from AWS:

```
./scripts/delete_lab_key
```
This command runs the `delete_lab_key` script



## 3. Terraform commands


Initialize Terraform:
```
terraform init
```

Format configuration files:
```
terraform fmt
```

Validate configuration:
```
terraform validate
```

Preview infrastructure changes:
```
terraform plan
```

Create infrastructure (2 EC2 instances):
```
terraform apply
```

Destroy infrastructure when finished with the lab:
```
terraform destroy
```


## 4. Ansible Commands


Perform syntax check on playbook:
```
ansible-playbook playbook.yml --syntax-check
```


Run the playbook:
```
ansible-playbook playbook.yml
```


## Screenshots

VM 1:
![](screenshot1.png)

VM 2:
![](screenshot2.png)