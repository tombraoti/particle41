# Create a EKS Cluster using AWS account

# The tools needed for this simulation in AWS includes the following
AWS CloudFormation to write the codes and do deployments
AWS S3 for storage of the codes before deploying to the AWS console
AWS IAM to grant roles and permissions for the services
AWS VPC to create and secure the network for the Clusters. But this is optional you might have existing VPC in your environment that meets specific requirement.
AWS EKS to create the cluster
Github source code management tool and version control system

test
### 1. Create an IAM Role
 Create an IAM Role for EKS Cluster using cloud formation template - eksClusterRole
 https://docs.aws.amazon.com/eks/latest/userguide/service_IAM_role.html

### 2. Create your Amazon EKS cluster VPC
 Create VPC using cloud formation template - amazon-eks-vpc-sample.yaml

 Go to Outputs once VPC is created and notedown VPC, Security group etc.


### 3. Create your Amazon EKS cluster

 Create an EKS Cluster from AWS Console, select appropriate VPC, Security group etc.

 When your cluster provisioning is complete (usually between 10 and 15 minutes), note the API server endpoint and Certificate authority values. These are used in your kubectl configuration.

### 4. Create a kubeconfig file

```sh
aws eks --region <Used_region> update-kubeconfig --name <cluster_name>
kubectl get svc
```


### 5. Create your Amazon EKS node role for Compute nodes
In Order to create compute, we will first create a role for the compute nodes using cloud formation and then we will use that role for compute nodes.
amazon-eks-nodegroup-role.yaml
https://docs.aws.amazon.com/eks/latest/userguide/create-node-role.html

### 6. Create compute
 Create Node group and provide appropriate parameters
