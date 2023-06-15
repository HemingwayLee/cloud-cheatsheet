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
* `AWS account access keys`: If you forget your account access keys, you can create new access keys without disabling the existing access keys. If you are not using the existing keys, you can delete those

