# AWS CLI
## install
[official website](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

### Check if installed
```
which aws
aws --version
```

## Config
* The credentials and config file are updated when you run the command `aws configure`
  * The config file is located at `~/.aws/config`
  * The credentials file is located at `~/.aws/credentials`

### Switch AWS CLI to another AWS account
* Change the `AWS account access keys` in `~/.aws/credentials` files

## Keys
* `AWS account access keys`: If you forget your account access keys, you can [create new access keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) without disabling the existing access keys. If you are not using the existing keys, you can delete those

### Lost old .pem key
* Create a new .pem key file
  * `chmod 400 <new_pem_key.pem>`
  * Get the public key part of the new .pem key
```
ssh-keygen -f <new_pem_key.pem> -y | pbcopy
```

  * Or, save to a .pem.pub file
```
ssh-keygen -f private.pem -y > public.pub
```

* Connect to EC2 from AWS console
* modify `~/.ssh/authorized_keys`
* paste the public key part of the new .pem key
* `ssh -i ~/.ssh/<new_pem_key.pem> <user>@<ip>`

