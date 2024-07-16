Run terraform init to download specific version of k8 provider 
- terraform init - installs new version of provider
- $ terraform init -upgrade - to get most up to date provider version

Run terraform plan to display resources to be created & highlight any possible unknown attributes
- terraform plan - determines if upgrade will affect any existing resources

---------- CANNOT GO BACK AFTER THIS POINT ----------
- Best practice to make a copy of .terraform.tfstate before running terraform refresh or terraform apply

terraform refresh - if update fails

Run terraform apply to create the resources 

Resources now visible in k8 cluster

kubectl get all -n nginx

web server can be access using public IP of node running the deployment

get IP using: minikube ip

curl$(minikube ip):30201

Alternatively:
$ kubectl get pod nginx-86c669bff4-zgjkv -n nginx -o json | jq .status.hostIP
"192.168.39.189"

$ kubectl get services -n nginx
NAME    TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
nginx   NodePort   10.109.205.23           80:30201/TCP   19m

$ curl 192.168.39.189:30201