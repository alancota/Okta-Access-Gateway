# Okta Access Gateway - Deploy in AWS

## Purpose
Build the Okta Access Gateway infrastructure in AWS

## Pre-requsites

* Install wget/curl in your local build machine if not already there

* Install Terraform in your local system. A quick guide is [here](https://letslearndevops.com/2017/07/23/how-to-install-terraform/).

* Install and configure AWS CLI in your local system. Instructions [here](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv1.html) and [here](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html#cli-quick-configuration).


## Setup

* Clone the git repo

````
git clone https://github.com/indranilokg/Okta-Access-Gateway.git
````

* Go to the aws deploy directory

````
cd Okta-Access-Gateway/deploy/aws
````

* Create file `terraform.tfvars` under **`./oag-upload`** directory. Provide appropriate values for the variables.

*Example -*

```
S3_OBJECT_KEY = "Okta-Access-Gateway.ova"
OAG_OVA_FILE_PATH = "../../Okta-Access-Gateway.ova"
aws_region = "us-east-1"
OAG_AMI_NAME = "okta-access-gateway"
```

[How can you determine your AWS region](https://help.okta.com/en/prod/Content/Topics/Access-Gateway/setup-using-ovf-aws.htm#Determine_Region)

* Create file `terraform.tfvars` under **`./oag-config`** directory. Provide appropriate values for the variables.

*Example -*

```
OAG_KEY_PATH = "~/.ssh/oagkey.pub"
OAG_SSO_COOKIE_DOMAIN= "gateway.info"
OAG_HOSTNAME = "gw.gateway.info"
OAG_AMI_NAME = "okta-access-gateway"
```


## Upload OAG OVA to AWS

To upload the Okta Access Gateway OVA to AWS, run the following command from aws deploy directory. 

```
make upload
```

To remove the OVA, run the following command from aws deploy directory.

```
make removeUpload
```

## Configure OAG

To upload the Okta Access Gateway OVA to AWS, run the following command from aws deploy directory. 

```
make config
```

To remove the OVA, run the following command from aws deploy directory.

```
make removeConfig
```

## Test



