## New Infrastructure
To create a new magikube project, run following steps

1. Start with new infrastructure creation
    - The project name must begin with a lowercase letter, contain only lowercase letters, numbers, or underscores, be between 3 to 8 characters in length, and must not end with an underscore. 
```bash
magikube new PROJECT_NAME
```
2. Please choose a cloud provider ons listed in the `Select a Cloud Provider` prompt.
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
13. To create applications, please refer to the application-related documentation available at `/how-to/Apps/`.

## Post Deployment Setup
After successfully creating the project, proceed by executing the following script:
```bash
chmod +x <PROJECT_NAME>/keycloak/config.sh
<PROJECT_NAME>/keycloak/config.sh
```