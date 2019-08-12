# lightsail-webgoat
WebGoat, a deliberately insecure Web Application hosted on AWS Lightsail

## Create instance
Create AWS Lightsail instance via [AWS Lightsail CLI](https://docs.aws.amazon.com/cli/latest/reference/lightsail/index.html "AWS Lightsail CLI")
```
aws lightsail create-instances --instance-names "webgoat-vm" --availability-zone eu-west-2a --blueprint-id centos_7_1901_01 --bundle-id large_2_0 --user-data file://user-data.txt
```
You can find the script in `/var/lib/cloud/instance/user-data.txt` on the instance

## Configure instance
### Open ports
```
aws lightsail open-instance-public-ports --port-info fromPort=8080,toPort=8080,protocol=TCP --instance-name webgoat-vm
aws lightsail open-instance-public-ports --port-info fromPort=9001,toPort=9001,protocol=TCP --instance-name webgoat-vm
aws lightsail open-instance-public-ports --port-info fromPort=9090,toPort=9090,protocol=TCP --instance-name webgoat-vm
```
