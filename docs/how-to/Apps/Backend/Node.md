## How to Deploy a Node Application using Magikube
To deploy a Node application along with its cloud infrastructure, please follow these steps:

1. To create base infrastructure using Magikube please refer to the documentation available at `/how-to/Create-Project`.
2. Please choose any frontend application from the options listed in the `Select a frontend application type` prompt.
3. Please choose `node-express` from the options listed in the `Select a backend application type` prompt.
4. Follow steps mentioned under section `Post Deployment Setup` in the documentation available at `/how-to/Create-Project`.
5. Post successful deployment, to start node application, move into `PROJECT_NAME/my-node-app` directory and run below commands:
```bash
npm run build
npm start
```
6. To check application is running, open `http://localhost:3000/` in Browser.
 
## Destroy Project
To destroy infrastructure and applications, created using `magikube` please refer to the documentation available at `/how-to/Destroy-Project`.