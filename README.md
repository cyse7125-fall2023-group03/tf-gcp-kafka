# tf-gcp-kafka

GCP Infrastructure

- In this repo, we will create a GKE cluster by accessing it via bastion Host.
- Helm Charts *.tgz will be copied from Github release into the bastion host to install helm charts and run the cluster.

# Terraform commands
- cd in to the repo directory 
- terraform init .
- terraform apply -var-file=dev.tfvars
- terraform destroy -var-file=dev.tfvars

- Tf-gcp-kafka  terraform init
terraform apply

- gcloud container clusters get-credentials my-vpc-native-cluster --region us-east1 --internal-ip
- gcloud auth login
- gcloud container clusters get-credentials my-vpc-native-cluster --region us-east1 --internal-ip
- export PATH=$PATH:/usr/local/go/bin
- export GOPATH=$HOME/go
- export PATH=$PATH:$GOPATH/bin
-  # to install istio
- helm repo add istio https://istio-release.storage.googleapis.com/charts
- helm repo update
- helm install istio-base istio/base -n istio-system --create-namespace
- helm install istiod istio/istiod -n istio-system
-  #scp  - to copy tar files to bastion host cd Downloads
- scp -i ~/.ssh/ec2 ./webapp-helm-chart-1.2.4.tar.gz udaykk@34.75.4.5:~/ 
- scp -i ~/.ssh/ec2 ./kafka-helm-chart-1.0.3.tar.gz udaykk@34.75.4.5:~/
- scp -i ~/.ssh/ec2 ./kube-operator-1.0.16.tar.gz udaykk@34.75.4.5:~/ 

# after scp to unpack the tar files the below command  tar -xvzf webapp-helm-chart-1.2.4.tar.gz
- tar -xvzf kafka-helm-chart-1.2.4.tar.gz
- tar -xvzf kube-operator-1.2.4.tar.gz

# after unpacking install helm by navigating into each folder  helm install —generate-name ./  # to check the database
- k exec -it chart-1702121668-postgres-kafka-0 -n consumer -- /bin/bash
- psql -U postgres app
- \dt
- SELECT * FROM health_check;
