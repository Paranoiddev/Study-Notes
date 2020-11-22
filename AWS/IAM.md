Identity access management is where you manage your AWS users and the level of access associated to their account and services they can use. 

IAM is Users, groups, IAM policies and Roles, roles is for AWS services to communicate to eachother or user on another aws account/ federated login from coorperate directory or other services such as OpenID or aws cognito. 

Explicit deny in AWS means If a user is denied access in any policy, it will override any allow in any policy.

Never use root user, think principle of least privilege and Zero Trust. 

Your authentication and authorization is handled by IAM. 

Before creating user accounts, enable MFA for your root user for example with google authenticator, Delete root access keys.

For adminstrative tasks create an IAM user with 'AdministratorAccess' policy assigned to it.


After, creating indiviual IAM users. (Use ask user to create a new password on first login to aws)
Enable Identity Federation
Enable MFA, rotate credentials.
Enable IAM Access Analyzer.
User groups to assign permissions.
Apply an IAM password policy.

It is more convenient and efficient to set up groups and assign permissions to the group rather than indiviual users.

For more info follow this link:

https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html