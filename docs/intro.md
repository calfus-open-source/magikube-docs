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

### Prerequisites for setting up a cluster with magikube
Please refer to pre-requisites for each cloud provider in respective sections

### Post Deployment Setup
1. Upon successful project creation, proceed with executing the following script:
```bash
chmod +x <PROJECT_NAME>/keycloak/config.sh

<PROJECT_NAME>/keycloak/config.sh
```
