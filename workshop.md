# Service Catalog Workshop

Welcome to the minimal Service Catalog session. Today we are going dive deeper into how we create an application for the service catalog.

## Workshop Stages

1. Create a Working application deployment.
2. Create a Service Catalog item
3. Tie the two together

### Create a Application deployment

The workload that was chosen for this workshop was something that is relevant to the company and its upcoming workloads - Drupal.

There is an AWS reference deployment for Drupal available [here](https://aws.amazon.com/quickstart/architecture/drupal/).

Due to time constraints (the full deployment takes over 45 minutes due to the cloudfront distribution - the session today will deploy a reduced version of the architecture as described below)

![drupal_deployment](drupal_deployment.png)

The deployment which is written in [Cloudformation](https://aws.amazon.com/cloudformation/) will perform the following

1. Create a VPC across 2 availability zones - default region is Virginia - `us-east-1`
2. The VPC will include 2 public subnets and 2 private subnets
3. Two NAT Gateways with be deployed in the public subnets
4. An IGW will be attached to the VPC
5. In each of the public subnets, a bastion host will be deployed (for redundancy)