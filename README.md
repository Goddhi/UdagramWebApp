<h2>Project Name : Udagram Web APP</h2>

<p> This a Udagram Web app  built with AWS cloudformation script </p>

<p>The UdagramNetwork file contains script used to build a network stack for the web server.</p>

<p>The UdagramServer file contains script used to build the web server.</p>

<p> The UdagramNetwork file includes two availability zones and it also contains:  </p>

- VPC: It host all resources both the Public Subnet and Private Subnet including NAT gateways, routable etc.

Private Subnet: The Web Server is hosted on the private subnet due to security reasons. To let end users  access the web app a loadbalancer is created to route traffic to the web server in the private subnet.

- Public Subnet: The loadbalncer of the application is hosted on the Public server.

- NAT gateway: This is hosted in the public subnet to allow the the private IP address have access to the internet. it does this by changing the Private IP address of the Private subnet for both Inbound and Outbounnd traffic.

- Route Table: it is a set rules that decides how traffic are being routed in the VPC

 
<p> The UdagramServer file contains:</p>

- WebServerGroup: It is a rule that decides how traffic are being routed into the web servr both for inbound and outbound traffic.

- LoabalancerServergroup: It is also a rule for the loadbalancer


-UdagaramLaunchConfiguration: This contains the web app code, what type of server it runs on etc

- AutoScallingGroup: scales the web server based on end user traffic to the webApp.

-ProfileWithRolesForUdagramApp: Provides Instances running in the webserver only read access to the S3 bucket 
