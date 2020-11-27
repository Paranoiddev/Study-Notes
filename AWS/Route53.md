It is managed DNS, it is not a free service, it can use public domain, it can use private domain as well which can only be resolved to your VPC. You pay 0.50$ per hosted zone.
It is a global service, doesn't require region selection.
After registered domain, you go to hosted zones to see your domain and there you can add a new record as seen below, you can add A, AAAA, CNAME and ALIAS records.

You can also add TTL for how long DNS can be stored/cached on the user's browser, when creating an A record you can also create a TTL for it
Alias work for root and non root domain, CNAME can't be used for root domain, ALIAS is also free of charge. Use Alias as you can point a hostname to aws resource directly. For example you can set up a load balancer for an EC2 instance, set up an ALIAS record and point root domain directly to the Alias.
Simple routing policy is when you can assign an A record multiple IP and it performs client side load balancing.
Weighted routing policy can divide traffic based on percentage, in record set when assigning IP address to A record, you can set weighted policy and enter value, you have to create multiple weighted policy for different IP and assign percentage.
Latency routing policy redirects to server with least latency close to user, it evaluated in terms of user and AWS region.
Route53 health checks are based, If it passes 3, then its healthy, if it fails 3 then unhealthy (value can be changed), default is 30seconds, can be 10s but costs, 15 health checkers will check endpoints , http, tcp and https based, can be integrated with cloud watch, can be linked with DNS queries.
Failover can be used when health check fails to route traffic to secondary.
Geolocation policy routes based on user location.
Multi value route policy is used to point to multiple resources. 