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
  - When installing Node.js, you are recommended to check all checkboxes related to dependencies.
- [homebrew](https://brew.sh)
- Python 3.12
  ```bash
  brew install python@3.12
  ```
- `tfenv` using brew
   ```bash
   brew install tfenv
   ```
- Terraform 1.8.2
   ```bash
   tfenv install 1.8.2
   ```
- Ansible
  ```bash
  brew install ansible@10
  ```

### Prerequisites for Setting Up a Cluster with magikube
Before you can set up a cluster with magikube, you will need to complete the following steps:

1. Ensure you have your AWS credentials ready.
2. Follow the instructions in the [AWS Keyspaces documentation](https://docs.aws.amazon.com/keyspaces/latest/devguide/access.credentials.html) to generate your AWS Access Key and Secret Key.
3. Once you have your AWS Access Key and Secret Key, install the AWS CLI on your local machine. Refer to the [AWS CLI installation guide](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) for detailed instructions.
4. Configure your AWS profile on your local machine using the following command:
```bash
aws configure --profile <profile_name>
```
5. Create a GitHub personal access token by following the instructions in the [GitHub documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic).
6. Have the GitHub organization name ready where you want the repositories to be created. If no organization is specified, repositories will be created under the executing user’s account.