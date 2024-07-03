## New Infrastructure
To setup new AWS infrastructure, run following steps

1. Start with new infrastructure creation 
```bash
magikube new PROJECT_NAME
```
2. Select `aws` from the options in `Select a Cloud Provider` prompt
3. If you have setup a default region then `Select a Region` will show it. If that is the region you want to use then move to next step, otherwise you can change to region of your choice.
4. Use `eks-fargate` for `Select a Cluster Type`
5. Validate or update AWS profile name to be used in `Enter AWS profile to use`
6. Select your code repository provider in `Source code repository`
7. If AWS profile name does not exist then `magikube` will create a new profile with you. It will need `AWS Access Key ID` and `AWS Secret Access Key`
8. Which environment are you creating. Make selection in `Select an Environment`
9. If you are creating a `non-production` environment, then select one or more lifecyles in `Select Lifecycle(s)`

Now let magic happen 

## Destroy
🚨 If you proceed with this command, be aware that it will be a catastrophic event and can not be reverted. 🚨

In case you need to destroy infrastructure that was created using `magikube`, you can run
```bash
magikube destroy PROJECT_NAME
```
