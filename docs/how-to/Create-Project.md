## New Infrastructure

To create a new magikube project, run the following steps.

#### **Before moving to the next steps, please ensure you have configured all pre-requisites available at [Introduction](../intro.md).**

1. Start with new infrastructure creation:
    - The project name must begin with a lowercase letter, contain only lowercase letters, numbers, or underscores, be between 3 to 8 characters in length, and must not end with an underscore. 
    ```bash
    magikube new PROJECT_NAME
    ```
2. Please choose a cloud provider from the options listed in the `Select a Cloud Provider` prompt.
    - For detailed, cloud provider-specific instructions, please refer to the [Cloud Guide](./AWS/).
3. Enter a region in the `Select a Region` prompt.
4. Please choose a cluster type from the available options listed in the `Select a Cluster Type` prompt.
5. Validate or update the cloud profile name to be used in the `Enter {AWS/GCP/AZURE} profile to use` prompt.
6. Please choose a code repository provider from the available options listed in the `Source code repository` prompt.
7. Enter `GitHub Organization Name`.
8. Enter `GitHub Access Token`.
9. Enter your Git username in the `What is your git user name?` prompt.
10. Specify the environment being created by making a selection in the `Select an Environment` prompt.
11. If you are creating a `non-production` environment, select one or more lifecycles in the `Select Lifecycle(s)` prompt.
12. Enter a domain name in the `Enter the Domain Name` prompt.
13. To create applications, please refer to the application-related documentation [Apps Guide](./Apps/Apps.md).

---

### **Individual Module Functionality**

#### 1. Creating a Blank Project
- **Command:**  
  ```bash
  magikube new_template <ProjectName>
  ```
- **Description:**  
  This command is used to create a blank project. The project will only contain the `.magikube` configuration file. Upon executing this command, the following user inputs are required:
  - **cloud-provider:** Specify the cloud provider (e.g., AWS).
  - **aws profile:** Provide the AWS profile name.
  - **environment:** Define the deployment environment (e.g., dev, prod).
  - **aws region:** Mention the AWS region where resources will be provisioned.
- **Output:**  
  An empty project structure with a `.magikube` file in the specified project folder.

#### 2. Using Grouping Templates
- **Command:**  
  ```bash
  magikube new_template <ProjectName> -t <template>
  ```
- **Description:**  
  This command is used when a user wants to provision a specific set of modules instead of the entire infrastructure. Grouping templates provide pre-defined combinations of modules tailored to various use cases.
  - **Available Templates:**
    - eks-fargate-vpc
    - eks-nodegroup-vpc
    - rds-vpc
    - ec2-vpc
    - vpc-rds-nodegroup-acm-ingress
  - **Pre-requisite:**  
    Before using grouping templates, the user must first create a blank project using the following command:
    ```bash
    magikube new_template <ProjectName>
    ```
- **Usage Example:**  
  To create a blank project:
  ```bash
  magikube new_template myproject
  ```
  To add a specific grouping template:
  ```bash
  magikube new_template myproject -t eks-nodegroup-vpc
  ```
- **Output:**  
  The selected grouping template modules will be added to the existing project structure.

#### 3. Adding Individual Modules
- **Command:**  
  ```bash
  magikube new_module <ProjectName> <ModuleType> <ModuleName>
  ```
- **Description:**  
  This command is used when a user wants to create and add individual modules to a project, one at a time. It provides flexibility for incremental infrastructure provisioning, where modules can be appended as per requirements.
  - **Available Module Types:**
    - vpc
    - rds
    - eks-fargate
    - eks-nodegroup
    - acm

- **Steps:**  
  1. Create a blank project using:
     ```bash
     magikube new_template <ProjectName>
     ```
  2. Add individual modules using:
     ```bash
     magikube new_module <ProjectName> <ModuleType> <ModuleName>
     ```
- **Usage Example:**  
  To create a blank project:
  ```bash
  magikube new_template myproject
  ```
  To add a single module, e.g., an EC2 module:
  ```bash
  magikube new_module myproject compute ec2-instance
  ```
- **Output:**  
  The specified module will be added to the existing project structure.

---

### **Post Deployment Setup**

- After successfully creating the project, proceed by executing the following script:
  ```bash
  chmod +x <PROJECT_NAME>/keycloak/config.sh
  <PROJECT_NAME>/keycloak/config.sh
  ```

- **How to retrieve ArgoCD credentials?**
  - Once the setup is complete, log in to the AWS Management Console to retrieve the initial ArgoCD login credentials. For both **NodeGroup and Fargate** type clusters, follow these steps:
    - Navigate to the **EKS** section in the console and select your cluster.
    - Under the **Resources** tab, go to **Config and Secrets**.
    - Locate and select the `argocd-initial-admin-secret` in the **Secrets** section, then click on **View Details**.
    - The **password** will be displayed, which can be decoded using the button on the right side. 
    - The username is **admin**.
  - For **K8S** based cluster types, connect to your cluster and execute the following command to fetch your password:
    ```bash
    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
    ```
