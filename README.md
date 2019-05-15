# chef_automate
Chef Automate configuration steps on AWS Marketplace

#  Chef Automate configuration on AWS
- [Reconfigure Chef Starter Kit](#reconfigure-chef-starter-kit)
- [Generate an SSH key](#generate-an-ssh-key)
- [Set your Git identity](#set-your-git-identity)

Lab URL: https://learn.chef.io/modules/deploy-infrastructure/ubuntu/aws/set-up-your-workstation#/

## Reconfigure Chef Starter Kit
When you create instance - dynamic hostname used, so after assigning Elastic IP - chef automate and chef server require reconfiguration. Following commands required:

``` 
#Reconfigure and restart backend sevices.
chef-marketplace-ctl hostname 
chef-marketplace-ctl stop biscotti
chef-marketplace-ctl start biscotti
automate-ctl reconfigure
chef-server-ctl reconfigure
automate-ctl restart
chef-server-ctl restart
chef-server-ctl restart nginx
```

## Generate an SSH key
You need an SSH key to submit changes to Chef Automate from the command line. The private part of your key, ~/.ssh/id_rsa, stays with you. You associate the public part of your key, ~/.ssh/id_rsa.pub, with your Chef Automate user profile. The process is similar to how systems such as GitHub work.

If you don't have an SSH keypair that you want to use, generate one now. The syntax varies slightly between Windows and other operating systems. Here are a few examples. The email address is not significant for this module, but you can replace "jsmith@example.com" with yours if you prefer.

``` 
ssh-keygen -t rsa -b 4096 -C "jsmith@example.com" -f $HOME/.ssh/id_rsa -N ""
```

## Set your Git identity
Next, run git config to set your Git identity. Git includes this information as metadata when you commit changes. You can omit this step if you've already configured Git to work with other projects.

If you have an existing Git account, such as with GitHub, you can use the same information here (changes you make in this module won't be published as public activity on your GitHub account.) You can use fictitious values if you prefer.

Here's an example.


```
git config --global user.name "Jane Smith"
```

```
git config --global user.email jsmith@example.com
```

