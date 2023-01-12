#### first create a vpc by search for vpc in aws search bar
---
![](pictures/Screenshot%20(42).png) 


select vpc only and give it any of your choice, i named mine my-vpc
![](pictures/Screenshot%20(43).png)

specify a cidr block for your network and click create vpc
![](pictures/Screenshot%20(44).png)

now its time to create our private and public subnet inside our newly created vpc 

![](pictures/Screenshot%20(45).png)

click on create subnet and create 
![](pictures/Screenshot%20(46).png)

make sure to select the vpc we create,specify a cidr block(it must fall within the subnet of the vpc) and click on click,;chose an availabity zone repaet this process four times to create four sbunet
![](pictures/Screenshot%20(47).png)

select a region and assign a cidr block and create the subnet
![](pictures/Screenshot%20(49).png)

now its time to create a public and private route table
![](pictures/Screenshot%20(51).png)

give it any name of your choice and make sure to create it inside the vpc we created, repeat the step to create two route a private and public
![](pictures/Screenshot%20(52).png)

create an internet gaway 
![](pictures/Screenshot%20(53).png)

attach it to our vpc
![](pictures/Screenshot%20(55).png)

create a nat-gateway that will us access to the internet from our private subnet(create it inide the public subnet of our vpc)
![](pictures/Screenshot%20(56).png)

go back to our route table select the public subnet and click on associated route, selete  the two public subnet, repeate the process for the private the priivate route table but select the two private subnet instead

![](pictures/Screenshot%20(56).png)

now the public route table click on edit route and allow connect from the internet-gate-way we created
![](pictures/Screenshot%20(59).png)


it time to create our ec2 instance ,we are createing three instances, two in the private subnet(without public ipv4) and 1 in the public subnent (with public ipv4) 

![](pictures/Screenshot%20(62).png)

---
# after the instances are properly launched ssh into the public intance , then from there sh into the private intance and install nginx

now time to create a load balancer for the two server
![](pictures/Screenshot%20(65).png

selet application loadbalancer
![](pictures/Screenshot%20(66).png)

select you vpc and chose the public subnet
![](pictures/Screenshot%20(66).png)

create a security gruop or choose a defualt one
![](pictures/Screenshot%20(69).png)

chose the two private server a your target group
![](pictures/Screenshot%20(70).png)

now you see you public instance  with an ipv4 address and your two private instances without ipv4 address
![](pictures/Screenshot%20(71).png)

sample of server 1
![](pictures/Screenshot%20(73).png)
sample of server 2
![](pictures/Screenshot%20(72).png)