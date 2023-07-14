# hanat
A bash script named after myself for high-availability NAT in-between EC2 instances - modification of kteru's version


[Startup]

Setting sysctl variables to forwarding packet
Adding IP masquerade rule
Disabling the Source/Dest Check of my own instance
Configuring route table of subnets which have responsibility

![image](https://github.com/hanatsamatar/hanat/assets/72223941/37d5ac31-8b9f-40cb-b607-11eddb1aa2f8)

When you replace the route table 

[What's needed]

2 EC2 instances which have EIP or Public IP
No need to select "NAT instance"
IAM Policies

ec2:ModifyInstanceAttribute
ec2:DescribeRouteTables
ec2:ReplaceRouteTableAssociation
Commands
aws (aws-cli)
awk (gawk or mawk)
curl
sysctl
iptables



[Installation]

# git clone https://github.com/hanatsamatar/hanat.git /opt/hanat
# cp -a /opt/hanat/docs/init_hanat.sh /etc/init.d/hanat
# chkconfig --add hanat
# chkconfig hanat on
