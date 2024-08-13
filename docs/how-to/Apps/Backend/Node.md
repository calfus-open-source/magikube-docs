## How to Deploy a Node Application using Magikube
To deploy a Node application along with its cloud infrastructure, please follow these steps:

1. Create a new project
    - The PROJECT_NAME should be in lowercase and must not include any capital letters.
```bash
magikube new PROJECT_NAME
```
2. Please choose one of the available cloud providers from the options listed in the `Select a Cloud Provider` prompt.
3. If you have setup a default region then `Select a Region` will show it. If that is the region you want to use then move to next step, otherwise you can change to region of your choice.
4. Please choose one of the available cluster type from the options listed in the `Select a Cluster Type` prompt.
5. Validate or update AWS profile name to be used in `Enter AWS profile to use`.
6. Select your code repository provider in the `Source code repository` prompt.
7. If AWS profile name does not exist then `magikube` will create a new profile with you. It will need `AWS Access Key ID` and `AWS Secret Access Key`.
8. Enter `GitHub Organization Name`.
9. Enter `GitHub Access Token`.
10. Please choose one of the available environment type from the options listed in the `Select an Environment` prompt.
11. If you are creating a `non-production` environment, then select one or more lifecyles in `Select Lifecycle(s)`.
12. Enter your git user name in the `What is your git user name?` prompt.
13. Please choose `node-express` from the options listed in the `Select a backend application type` prompt.
14. To start node application, move into `PROJECT_NAME/my-node-app` directory and run below commands:
```bash
npm run build
npm start
```
15. To check application is running, open `http://localhost:3000/` in Browser.
 

## Destroy Project
🚨 If you proceed with this command, be aware that it will be a catastrophic event and can not be reverted. 🚨

In case you need to destroy infrastructure and application that was created using `magikube`, you can run
- All files from ECR repository `<prj-name>-<app-name>-app`, must be cleaned before executing the destroy command.
```bash
magikube destroy PROJECT_NAME
```
