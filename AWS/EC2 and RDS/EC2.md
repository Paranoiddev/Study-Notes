https://www.stackchief.com/blog/Amazon%20EC2%20Tutorial

Scalable VM which use pay as use model, no wasted capacity. No hardware expense. 
Its pricing models are 
on demand (pay for an hour or second)
reserved (You reserve for one or three years, upto 72% discount)
Spot (Purchase unsed capacity at upto 90% discount, price can differ)
Dedicated (The most expensive, a physical ec2 server, great for compliance and licensing)
Also Savings plans, use pricing calculator to get estimate and check ec2, you can estimate other services too.
In a type name, the number indicates the generation number of the AMI.
FPGA is for parallel processing use cases. Imagine a Go app on this lol, use case can be finanicial computing  data analystics
Compute optimized is for batch processing or high processing apps use cases
GPU is for graphics, 3D or image rendering. Its type can name also start with p
ML machine start with inf1 type. 
Storage optimized use case is for nosql database.
All EC2 instances are monitored by cloudwatch by default  and collects data every 5 mins but detailed monitoring costs extra on cloud watch.
User data is script you run on your EC2 instances when it boots up, for example update the OS or install an app.
For storage you can add volume, more EBS volume can be added, you can also encrypt your storage using KMS.
Security Groups is similar to virtual firewall, you can add ports and protocol, src and dest, along with traffic type such as ssh and https and so on. 


Elastic load balancers are application load balancers (http and https traffic, layer 7 and application aware), network load balancers(layer 4, tcp traffic, low latency and extreme performance but most expensive), classic load balancers (being phased out, layer 7 or layer 4), errors on ELB can be 504 which means its app or db. 
X-forwarded-For Header is for IP mapping traffic to your end user. 

Route 53 is managed DNS server for amazon which you can map to EC2, load balancer or S3 buckets, after a domain registeration, create a hosted zoned, create a record set, A record, CNAME, MX and AAAA record, you already know these.

CLI
You can use by generating an access id and use it using AWS configure. Don't put it in code, use KMS. 
You can use CLI on you PC. 

https://docs.aws.amazon.com/cli/latest/index.html

https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html

You can assign roles instead of using user keys, you can change, remove or assign IAM roles without starting or stopping the EC2 instance, this way your keys are secure and not accidentally leaked on github or other platforms.