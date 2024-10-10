## New Infrastructure
To setup new AWS infrastructure, follow below steps:

1. To create base infrastructure using Magikube please refer [Create Project](../Create-Project.md) guide. 
2. Select `aws` from the options in `Select a Cloud Provider` prompt.
3. If you have setup a default region then `Select a Region` will show it. If that is the region you want to use then move to next step, otherwise you can change to region of your choice.
4. Use `k8s` for `Select a Cluster Type`.
5. Validate or update AWS profile name to be used in `Enter AWS profile to use`.
6. Select your code repository provider in `Source code repository`.
7. If AWS profile name does not exist then `magikube` will create a new profile with you. It will need `AWS Access Key ID` and `AWS Secret Access Key`.
8. Which environment are you creating. Make selection in `Select an Environment`.
9. If you are creating a `non-production` environment, then select one or more lifecyles in `Select Lifecycle(s)`.
10. Enter a domain name in the `Enter the Domain Name` prompt.
11. To create applications, please refer [Apps Guide](../Apps/Apps.md).

## Post Deployment Setup for K8s
1. Using terminal ssh into your master server using command
```bash
ssh {{ project_name }}-{{ environment }}-master
```
2. Execute command to get the list of namespaces
```bash 
kubectl get namespace
```
3. Execute command to list all the service running 
```bash
kubectl get svc -n {{ project_name }}-{{ environment }}-app
```
4. Execute command and fetch the frontend(Eg: react) IP Value. Here *frontend_app* is the name of frontend service from step 3.
```bash
kubectl get {{ frontend_app }} -n {{ project_name }}-{{ environment }}-app -o jsonpath='{.spec.clusterIP}'
```
5. Create a file i.e. */etc/nginx/sites-available/application-nginx.conf*
using below content and replace the value for *`{{ hostname }} and {{ frontend_service_ip }}`*
```bash
   ## server configuration for Application
server {
    listen 80;
    server_name {{ hostname }};

    if ($http_x_forwarded_proto = '') {
        set $http_x_forwarded_proto  $scheme;
    }

    ## Application specific logs
    chunked_transfer_encoding on;
    client_max_body_size 0;

    location / {
        proxy_read_timeout  2400s;
        proxy_pass_header   Server;
        proxy_cookie_path   ~*^/.* /;
        proxy_pass          http://{{ frontend_service_ip }}:80;  
        proxy_next_upstream error timeout non_idempotent;
        proxy_next_upstream_tries    1;
        proxy_set_header    X-Forwarded-Port  $server_port;
        proxy_set_header    X-Forwarded-Proto $http_x_forwarded_proto;
        proxy_set_header    Host              $http_host;
        proxy_set_header    X-Forwarded-For   $proxy_add_x_forwarded_for;
    }
}
```
6. Create a symlink for the nginx configurations using command
```bash
sudo ln -s /etc/nginx/sites-available/application-nginx.conf /etc/nginx/sites-enabled/application-nginx.conf
```
7. Restart Niginx using command
```bash
sudo systemctl reload nginx
```

## Destroy Project
To destroy infrastructure and applications, created using `magikube` please refer [Destroy Project](../Destroy-Project.md) guide.
