Virtual private cloud is a private network to deploy your resources. Its a regional resource not global.
Inside VPC you can create multiple subnets at AZ level, basically letting you partition your network.
You can create a public subnet to make it accessable via internet, private subnet is not accessable via internet. 
To define internet/network connectivity between subnets or subnet to access internet, you use route tables.

Internet gateway (IGW) is how public subnet communicate with the internet, route to it. Private subnet can access internet through NAT gateways (managed by internet) or NAT instances (self managed instances)
NACL(Network Access Control List) firewall which monitors traffic going in and out a subnet, rules based on IP address, based on subnet level. By default all traffic is allowed to go in and out through NACL
Security groups control traffic coming to an EC2 instance/Elastic network interface (ENI), can have only allow rules, can reference eithr IP address or other security group.
VPC flow logs are used to monitor internet and subnet and troubleshoot issues. It can also capture traffic from any AWS managed service.
VPC peering means connecting two VPC, privately using AWS network

VPC endpoint allow you to connect to AWS services privately, as by default these services are publicly available.  Enhanced security and lower latency. these are only for connecting to AWS services.

Typical 3 tier architecture