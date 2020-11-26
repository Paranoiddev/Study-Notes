RDS is used for Relational Database. You can host these DB on RDS:

MySQL.
SQL SERVER.
PostgreSQL.
AURORA.
ORACLE.
MariaDB.

Elasticache is a great way to cache frequently accessed data, in memory cache to improve database performance.
Redis and memcache. 
For security you can set a VPC security group and put the DB behind it and also by default it is not accessible publicly.

You are never given a public IPv4 for the RDS, you are assigned a DNS and AWS manages the DNS to IP mapping.
Always make sure that your RDS security group and EC2 instance, communication is allowed, check inbound and outbound rules and allow port 3306 and the EC2 instance security group.

Backups, multi AZ and read replicas are an important aspect of RDS