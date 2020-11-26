there's two types of backups for AWS.
There's the automated backups
and there's database snapshots.
Now automated backups will allow you to recover
your database to any point in time,
within a retention period.
And the retention period can be between one and 35 days.
Automated backups will basically take a full daily snapshot
and will also store transaction logs throughout the day.
And then when you recover, AWS will first
choose the most recent daily backup,
so it will choose the snapshot that is most recent,
and then apply those transaction logs
that are relevant to that day,
they're enabled by default.
The backup data is stored on S3
and you're going to get free storage space
equal to the size of your database.
During the backup window, storage IO may be suspended
while your data is being backed up
and you may experience some elevated latency.
Whenever you restore either an Automatic Backup
or a manual Snapshot,
the restored version of the database will be
a new RDS instance with a new DNS endpoint.


snapshots.
They're basically a snapshot of the database,like a VM snapshot
when you do a database snapshot
it's going to take a snapshot of the database.
It's always done manually, so they're always user initiated,
and they will always be stored
even after you delete the original RDS instance.
If you delete the original RDS instance,
your automated backups will also be deleted
with it as well.
Whereas DB Snapshots are basically set as a standalone file
and you can delete the RDS instance without having to worry
about those snapshots being deleted as well.


Encryption at rest is supported for MySQL, Oracle,
SQL Server, PostgreSQL, MariaDB and Aurora.
It's done using the AWS KMS, or Key Management Service.
once your RDS instance is encrypted,
the data stored at rest in the underlying storage
is encrypted, as are all of its automated backups,
read replicas, and snapshots. once you encrypt a database, anything you do with
that database in terms of making a copy
of that data is going to be encrypted as well.

To use RDS encryption for an existing database,
you must first create a snapshot
and then make a copy of that snapshot
and encrypt the copy,

Multi-AZ?
if you lose your
primary database amazon will detect that
and it will update the DNS address to point to the
IP address of your multi-AZ copy of your database.
you never deal with IP addresses when dealing with RDS,
you always just use this DNS endpoint and this DNS endpoint will fail over automatically
to your secondary multi-AZ database.
So multi-AZ allows you to have an exact copy
of your production database in another Availability Zone.
And AWS handles the replication for you,
multi-AZ databases are available for
SQL Server, Oracle, MySQL Server, PostgreSQL, MariaDB.
Aurora by default
is spread across multiple availability zones.
So you don't need to turn on multi-AZ for Aurora,


If you want performance improvement,
you're going to need read replicas,

This is a way of scaling out your database,
so that you take the load off the primary database
and you spread that load across one or more read replicas.
You can also have read replicas of read replicas.
You will get some replication latency if you do do that,
but you could have a read replica in another
availability zone or you could have a read replica
in another availability zone, or you could have a
read replica in a completely different region,

So read replicas allow you to have a
read-only copy of your production database.
This is a achieved using Asynchronous replication for the
primary RDS instance to the read replica,
and you use read replicas primarily for very
read-heavy database workloads.
So read replica databases are currently available for
MySQL Server, PostgreSQL, MariaDB and Aurora.
So it's available for four.
They are currently not available for SQLServer or for Oracle.

they used for scaling not for disaster recovery.
