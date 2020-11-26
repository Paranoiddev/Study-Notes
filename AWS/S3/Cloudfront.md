It is a CDN service by AWS
Improves read performance, cache content at the edge.
DDOS protection and integrates with Shield and WAF, it can also expose an external https by loading a certificate and you can use https internally as well.
You can use it with S3 or an S3 website but you must first declare the bucket as a static S3 website, ec2, lamda, application load balancer or any service that utilizes HTTP protocol.

Cloudfront is referred as edge and origin can be any AWS service it queries.

For S3, the edge location needs OAI (origin access identity and S3 bucket poilcy) to access the S3 bucket. this can be used for all edgelocations regardless of origin


For instance such as EC2, the security group must allow edge location's public IP, couple this with ALB, this way you can make the ALB public but the EC2 can be private.
You can create whitelist and blacklist using GEO-IP database.

Good for static content, S3 cross region replication for dynamic content though.

