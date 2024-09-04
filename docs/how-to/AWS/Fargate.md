## New Infrastructure
To setup new AWS infrastructure, follow below steps:

1. To create base infrastructure using Magikube please refer [Create Project](../Create-Project.md) guide. 
2. Select `aws` from the options in `Select a Cloud Provider` prompt.
3. If you have setup a default region then `Select a Region` will show it. If that is the region you want to use then move to next step, otherwise you can change to region of your choice.
4. Use `eks-fargate` for `Select a Cluster Type`.
5. Validate or update AWS profile name to be used in `Enter AWS profile to use`.
6. Select your code repository provider in `Source code repository`.
7. If AWS profile name does not exist then `magikube` will create a new profile with you. It will need `AWS Access Key ID` and `AWS Secret Access Key`.
8. Which environment are you creating. Make selection in `Select an Environment`.
9. If you are creating a `non-production` environment, then select one or more lifecyles in `Select Lifecycle(s)`.
10. Enter a domain name in the `Enter the Domain Name` prompt.
11. To create applications, please refer [Apps Guide](../Apps/Backend/Backend.md).

## Destroy Project
To destroy infrastructure and applications, created using `magikube` please refer [Destroy Project](../Destroy-Project.md) guide.
