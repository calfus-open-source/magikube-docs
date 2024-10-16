## New Infrastructure
To create a new magikube project, run following steps.

#### ** Before moving to next steps, please ensure you have configured all pre-requisites available at [Introduction](../intro.md).**

1. Start with new infrastructure creation
    - The project name must begin with a lowercase letter, contain only lowercase letters, numbers, or underscores, be between 3 to 8 characters in length, and must not end with an underscore. 
```bash
magikube new PROJECT_NAME
```
2. Please choose a cloud provider one listed in the `Select a Cloud Provider` prompt.
    - For detailed, cloud provider-specific instructions, please refer [Cloud Guide](./AWS/).
3. Enter a region in the `Select a Region` prompt.
4. Please choose a cluster type from the available options listed in the `Select a Cluster Type` prompt.
5. Validate or update cloud profile name to be used in `Enter {AWS/GCP/AZURE} profile to use` prompt.
6. Please choose a code repository provider from the available options listed in `Source code repository` prompt.
7. Enter `GitHub Organization Name`.
8. Enter `GitHub Access Token`.
9. Enter your git user name in the `What is your git user name?` prompt.
10. Which environment are you creating. Make selection in `Select an Environment`.
11. If you are creating a `non-production` environment, then select one or more lifecyles in `Select Lifecycle(s)`.
12. Enter a domain name in the `Enter the Domain Name` prompt.
13. To create applications, please refer to the application-related documentation [Apps Guide](./Apps/Apps.md).

## Post Deployment Setup
- After successfully creating the project, proceed by executing the following script:
    ```bash
    chmod +x <PROJECT_NAME>/keycloak/config.sh
    <PROJECT_NAME>/keycloak/config.sh
    ```
- How to retrive **ArgoCD** credentials?
    - Once the setup is complete, log in to the AWS Management Console to retrieve the initial ArgoCD login credentials. For both **NodeGroup and Fargate** type clusters, follow these steps:
        - Navigate to the **EKS** section in the console and select your cluster.
        - Under the **Resources** tab, go to **Config and Secrets**.
        - Locate and select the `argocd-initial-admin-secret` in the **Secrets** section, then click on **View Details**.
        - The **password** will be displayed, which can be decoded using the button on the right side. 
        - The username is **admin**.
    - For **K8S** based cluster type, connect to your cluster and execute below command to fetch your password.
        ```bash
        kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
        ```