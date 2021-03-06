# totalcoudassignment


step 1:
install AWS CLI
use this link for installing aws CLI
https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html



install kubectl
use this link to install kubectl
https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html

Configure AWS_IAM_AUTHENTICATOR


step 2:

Create a eks role using 

Click IAM console in aws and click on Roles 
and click on create role


Give any name and continue with default value

Click on create and it will be create within a minute


step 3:
create  a VPC for eks
 click on cloud formation 
 and click on create stack


 use this link in s3 bucket url and rest default value

 https://amazon-eks.s3-us-west-2.amazonaws.com/cloudformation/2019-01- 09/amazon-eks-vpc-sample.yaml



 step 4:
  create EKS cluster


using this command 
  

  aws eks create-cluster \
   --region us-east-2 \
   --name demo \
   --kubernetes-version 1.19 \
   --role-arn arn:aws:iam::970852099091:user/nijoluca \
   --resources-vpc-config subnetIds=subnet-0d6baad511fba9d95,subnet-033d964032d1b85d5,subnet-04fdf3b29465e1441,securityGroupIds=sg-00413b64ff5b398a9




step 5:
launch kubernetes worker node


open cloudformation and add this link

https://amazon-eks.s3-us-west-2.amazonaws.com/cloudformation/2019-01-
09/amazon-eks-nodegroup.yaml


Execute


kubectl apply -f aws-auth-cm.yaml


use 


kubectl get nodes --watch 


get all running nodegroups







step 6:

install web app on EKS cluster


using the command 
kubectl apply -f filename (execute all slave and master files)
