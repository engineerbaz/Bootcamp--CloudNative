# AWS



`aws iam attach-group-policy --group-name AdminGroup --policy-arn arn:aws:iam::aws:policy/AdministratorAccess`

```yaml
aws iam list-attached-group-policies --group-name AdminGroup


---
        {
            "Path": "/",
            "GroupName": "AdminGroup",
            "GroupId": "AGPA4P3SN37OWOHDISF6Q",
            "Arn": "arn:aws:iam::858696572893:group/AdminGroup",
            "CreateDate": "2021-05-23T05:26:49+00:00"
        },

        {
            "Path": "/",
            "GroupName": "AdministratorGroup",
            "GroupId": "AGPA4P3SN37O5LAAZUEW6",
            "Arn": "arn:aws:iam::858696572893:group/AdministratorGroup",
            "CreateDate": "2022-03-22T17:11:44+00:00"
        }

```


aws ec2 create-vpc --cidr-block 192.168.0.0/16 --instance-tenancy default --tag-specification ResourceType=vpc,Tags=[{Key=Name,Value="My First VPC"}]