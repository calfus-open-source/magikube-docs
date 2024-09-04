## How to Deploy a Node Application using Magikube
To deploy a Node application along with its cloud infrastructure, please follow below steps:

1. To create base infrastructure using Magikube please refer [Create Project](../../Create-Project.md) guide.
2. Please choose any frontend application from the options listed in the `Select a frontend application type` prompt.
3. Please choose `node-express` from the options listed in the `Select a backend application type` prompt.
4. Follow steps mentioned under section `Post Deployment Setup` in the [Create Project](../../Create-Project.md) guide.
5. Post successful deployment, to start node application, move into `PROJECT_NAME/my-node-app` directory and run below commands:
```bash
npm run build
npm start
```
6. To verify that the application is up and running, open the [link](http://localhost:3000/) in your browser.
 
## Destroy Project
To destroy infrastructure and applications, created using `magikube` please refer [Destroy Project](../../Destroy-Project.md) guide.