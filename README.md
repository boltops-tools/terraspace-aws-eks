# Terraspace AWS EKS Example

This project shows how to use the [EKS Terraform registry module](https://registry.terraform.io/modules/terraform-aws-modules/eks/aws) with [Terraspace](https://terraspace.cloud/).

* Thanks and credit goes to the author of this module: Brandon B.
* Most contributors are doing this on their own free time. Please support them. Contribute back and send them a pull request. Some may ask for donations. Donate to them. Some are consultants. Hire them.

## Setup

    git clone https://github.com/boltops-tools/terraspace-aws-eks
    cd terraspace-aws-eks
    bundle

## Deploy Cluster

To deploy:

    terraspace up basic

The EKS cluster is created in the `us-west-2` region.

## Connecting to Cluster

    $ aws eks list-clusters --region us-west-2
    {
        "clusters": [
            "test-eks-VNoR1okp"
        ]
    }
    $ aws eks --region us-west-2 update-kubeconfig --name test-eks-VNoR1okp
    $ kubectl get node
    NAME                                       STATUS   ROLES    AGE     VERSION
    ip-10-0-4-157.us-west-2.compute.internal   Ready    <none>   5m41s   v1.17.11-eks-cfdc40
    ip-10-0-4-34.us-west-2.compute.internal    Ready    <none>   5m42s   v1.17.11-eks-cfdc40
    ip-10-0-5-229.us-west-2.compute.internal   Ready    <none>   5m43s   v1.17.11-eks-cfdc40
    ip-10-0-6-218.us-west-2.compute.internal   Ready    <none>   5m46s   v1.17.11-eks-cfdc40
    ip-10-0-6-231.us-west-2.compute.internal   Ready    <none>   5m45s   v1.17.11-eks-cfdc40
    $

AWS EKS Docs: [Create a kubeconfig for Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/create-kubeconfig.html)

## Create App

To create and deploy a Kubernetes app onto the cluster check out: [Kubes: Kubernetes Deployment Tool](https://kubes.guru/)

## Updating

To update the modules to the latest version from the Terraform registry.

    terraspace bundle update

## More Examples

    $ terraspace list
    app/stacks/basic
    app/stacks/create_false
    app/stacks/irsa
    app/stacks/launch_templates
    app/stacks/managed_node_groups
    app/stacks/secrets_encryption
    app/stacks/spot_instances

## About

[![BoltOps Badge](https://img.boltops.com/boltops/badges/boltops-badge.png)](https://www.boltops.com)

[Terraspace](https://terraspace.cloud/) and this project was built by [BoltOps](https://www.boltops.com). We also offer:

* [Paid Consulting Services](https://www.boltops.com/consulting)
* [BoltOps Pro: Infrastructure Code as a Service](https://www.boltops.com/pro)
