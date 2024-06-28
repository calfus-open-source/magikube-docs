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

### What you will need to create instance
`magikube` will need a few things to be able to setup a cluster for you.
1. If you have already configured AWS credentials then you will need profile name and can skip to step 3
2. AWS Access Key/Secret
3. Github personal access token for user that has admin rights
4. Github organization name where you want repositories to be created. If no organization is provided, repositories will be created under executing user.