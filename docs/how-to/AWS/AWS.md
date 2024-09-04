### Prerequisites for setting up a cluster with magikube on AWS
Before you can set up a cluster in AWS with magikube, you will need to complete the following steps:

1. Ensure you have your AWS credentials ready.
2. Follow the instructions in the [AWS documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) to generate your AWS Access Key and Secret Key.
3. Once you have your AWS Access Key and Secret Key, install the AWS CLI on your local machine. Refer to the [AWS CLI installation guide](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) for detailed instructions.
4. Configure your AWS profile on your local machine using the following command:
```bash
aws configure --profile <profile_name>
```
5. In order to run magikube and deploy application, you would need a domain name which is registered in AWS route 53. Follow [AWS documentation](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-register.html) for Domain resgitration.

### For AWS hosted target environments please use following links

- [Fargate](./Fargate.md)
- [Nodegroup](./Nodegroup.md)