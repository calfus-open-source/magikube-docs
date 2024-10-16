---
sidebar_position: 1
---

# Introduction

Magikube helps you create production ready infrastructure and applications in minutes.⚡️

## Getting Started

We love mac. Currently `magikube` is at home on macOS. Other operating systems will be added in future.

Install `magikube` from npm
```bash
npm i -g magikube
```

## Pre-requisites for Creating Infrastructure Using Magikube

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
   tfenv use 1.8.2
   ```
- Ansible
  - To verify the current installed Ansible version, execute the command: `ansible --version`.
  ```bash
  brew install ansible@10
  ```
- GitHub
  - Create a GitHub personal access token by following the instructions in the [GitHub documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic). Ensure that the *delete_repo*, *user*, *admin:org*  and *workflow* permission is enabled for the generated token.
  - Have the GitHub organization name ready where you want the repositories to be created. If no organization is specified, repositories will be created under the executing user’s account.

- Domain Name
  - In order to run magikube and deploy application, you would need a domain name. Please keep one domain name ready before moving to next steps.

##### Note: Please refer to pre-requisites for each cloud provider in respective sections.

## Next Steps
To create new infrastructure using Magikube, please refer [Create Project](./how-to/Create-Project.md) guide.
