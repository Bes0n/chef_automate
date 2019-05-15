# chef_automate
Chef Automate configuration steps on AWS Marketplace

#  Chef Automate configuration on AWS
- [Reconfigure Chef Starter Kit](#reconfigure-chef-starter-kit)


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