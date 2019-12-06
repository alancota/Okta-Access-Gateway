# Okta Access Gateway - Deploy in AWS
Build the Okta Access Gateway infrastructure in AWS

## Pre-requsites

* Install wget/curl

* Install Terraform in your local system

A quick guide is [here](https://letslearndevops.com/2017/07/23/how-to-install-terraform/)

* Install and configure AWS CLI in your local system

* Download OVA
https://download.oag.okta.com/ga/oag.ova

## Setup

cd /Users/indraniljha/Okta/FY20/Work/Internal/Assets/Okta-Access-Gateway/Deploy/terraform

$ terraform init

Verify -
        Downloading plugin for provider "aws" (hashicorp/aws) ........

Determine Region -
https://help.okta.com/en/prod/Content/Topics/Access-Gateway/setup-using-ovf-aws.htm#Determine_Region

Create file `terraform.tfvars` under **`./terraform`** directory. Provide appropriate values for the variables.

*Example -*

```
udp_target_env = "dev"
S3_OBJECT_KEY = "tf-okta-example.zip"
TF_ARTIFACT_FILENAME = "tf-okta-example"
UDP_API_URL = "https://api-dev.udp-okta.io/api/configs"
aws_access_key_id = "*******"
aws_secret_access_key = "*********"
aws_region = "us-east-1"
```

## Execute

To create the infrastructure, run the following command from base directory. Make note of the **`terraform_url`** displayed as the final output 

```
make deploy
```

To destroy the infrastructure, run the following command from base directory.

```
make destroy
```


## Test



