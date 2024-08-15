---
sidebar_position: 1
---

# Introduction

magikube helps you create production ready infrastructure and applications in minutes.⚡️

## Getting Started

We love mac. Currently `magikube` is at home on macOS. Other operating systems will be added in future.

Install `magikube` from npm
```bash
npm i -g magikube
```

### What you'll need installed

There are a few things that you will need before starting with `magikube`. If you already have some of these things on your mac, please skip over the step.

- [Node.js](https://nodejs.org/en/download/) version 18.0 or above:
  - To verify the current installed Node.js version, execute the command: `node --version`.
  - When installing Node.js, you are recommended to check all checkboxes related to dependencies.
- [homebrew](https://brew.sh)
- Python 3.12
  - To verify the current installed Python version, execute the command: `python3 --version`.
  ```bash
  brew install python@3.12
  ```
- `tfenv` using brew
  - To verify the current installed TFenv version, execute the command: `tfenv --version`.
   ```bash
   brew install tfenv
   ```
- Terraform 1.8.2
  - To verify the current installed Terraform version, execute the command: `terraform --version`.
   ```bash
   tfenv install 1.8.2
   ```
- Ansible
  - To verify the current installed Ansible version, execute the command: `ansible --version`.
  ```bash
  brew install ansible@10
  ```

### Prerequisites for Setting Up a Cluster with magikube
Before you can set up a cluster with magikube, you will need to complete the following steps:

1. Ensure you have your AWS credentials ready.
2. Follow the instructions in the [AWS documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) to generate your AWS Access Key and Secret Key.
3. Once you have your AWS Access Key and Secret Key, install the AWS CLI on your local machine. Refer to the [AWS CLI installation guide](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) for detailed instructions.
4. Configure your AWS profile on your local machine using the following command:
```bash
aws configure --profile <profile_name>
```
5. Create a GitHub personal access token by following the instructions in the [GitHub documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic). Ensure that the *delete_repo*, *user*, *admin:org*  and *workflow* permission is enabled for the generated token.
6. Have the GitHub organization name ready where you want the repositories to be created. If no organization is specified, repositories will be created under the executing user’s account.
7. In order to run magikube and deploy application, you would need a domain name which is registered in AWS route 53. Follow [AWS documentation](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-register.html) for Domain resgitration.

### Post Deployment Setup
1. Upon successful project creation, proceed with executing the following script:
```bash
chmod +x <PROJECT_NAME>/keycloak/config.sh

<PROJECT_NAME>/keycloak/config.sh
```
