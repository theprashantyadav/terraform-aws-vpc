<!-- This file was automatically generated by the `geine`. Make all changes to `README.yaml` and run `make readme` to rebuild this file. -->

<p align="center"> <img src="https://user-images.githubusercontent.com/50652676/62349836-882fef80-b51e-11e9-99e3-7b974309c7e3.png" width="100" height="100"></p>


<h1 align="center">
    Terraform AWS VPC
</h1>

<p align="center" style="font-size: 1.2rem;"> 
    Terraform module to create VPC resource on AWS.
     </p>

<p align="center">

<a href="https://www.terraform.io">
  <img src="https://img.shields.io/badge/Terraform-v1.1.7-green" alt="Terraform">
</a>
<a href="LICENSE.md">
  <img src="https://img.shields.io/badge/License-APACHE-blue.svg" alt="Licence">
</a>
<a href="https://github.com/clouddrove/terraform-aws-vpc/actions/workflows/tfsec.yml">
  <img src="https://github.com/clouddrove/terraform-aws-vpc/actions/workflows/tfsec.yml/badge.svg" alt="tfsec">
</a>
<a href="https://github.com/clouddrove/terraform-aws-vpc/actions/workflows/terraform.yml">
  <img src="https://github.com/clouddrove/terraform-aws-vpc/actions/workflows/terraform.yml/badge.svg" alt="static-checks">
</a>


</p>
<p align="center">

<a href='https://facebook.com/sharer/sharer.php?u=https://github.com/clouddrove/terraform-aws-vpc'>
  <img title="Share on Facebook" src="https://user-images.githubusercontent.com/50652676/62817743-4f64cb80-bb59-11e9-90c7-b057252ded50.png" />
</a>
<a href='https://www.linkedin.com/shareArticle?mini=true&title=Terraform+AWS+VPC&url=https://github.com/clouddrove/terraform-aws-vpc'>
  <img title="Share on LinkedIn" src="https://user-images.githubusercontent.com/50652676/62817742-4e339e80-bb59-11e9-87b9-a1f68cae1049.png" />
</a>
<a href='https://twitter.com/intent/tweet/?text=Terraform+AWS+VPC&url=https://github.com/clouddrove/terraform-aws-vpc'>
  <img title="Share on Twitter" src="https://user-images.githubusercontent.com/50652676/62817740-4c69db00-bb59-11e9-8a79-3580fbbf6d5c.png" />
</a>

</p>
<hr>


We eat, drink, sleep and most importantly love **DevOps**. We are working towards strategies for standardizing architecture while ensuring security for the infrastructure. We are strong believer of the philosophy <b>Bigger problems are always solved by breaking them into smaller manageable problems</b>. Resonating with microservices architecture, it is considered best-practice to run database, cluster, storage in smaller <b>connected yet manageable pieces</b> within the infrastructure. 

This module is basically combination of [Terraform open source](https://www.terraform.io/) and includes automatation tests and examples. It also helps to create and improve your infrastructure with minimalistic code instead of maintaining the whole infrastructure code yourself.

We have [*fifty plus terraform modules*][terraform_modules]. A few of them are comepleted and are available for open source usage while a few others are in progress.




## Prerequisites

This module has a few dependencies: 

- [Terraform 1.x.x](https://learn.hashicorp.com/terraform/getting-started/install.html)
- [Go](https://golang.org/doc/install)
- [github.com/stretchr/testify/assert](https://github.com/stretchr/testify)
- [github.com/gruntwork-io/terratest/modules/terraform](https://github.com/gruntwork-io/terratest)







## Examples


**IMPORTANT:** Since the `master` branch used in `source` varies based on new modifications, we suggest that you use the release versions [here](https://github.com/clouddrove/terraform-aws-vpc/releases).


### Simple Example
Here is an example of how you can use this module in your inventory structure:
  ```hcl
  module "vpc" {
      source      = "clouddrove/vpc/aws"
      version     = "1.3.0"
      name        = "vpc"
      environment = "test"
      label_order = ["name", "environment"]
      cidr_block  = "10.0.0.0/16"
    }
  ```






## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| additional\_cidr\_block | List of secondary CIDR blocks of the VPC. | `list(string)` | `[]` | no |
| attributes | Additional attributes (e.g. `1`). | `list(any)` | `[]` | no |
| cidr\_block | CIDR for the VPC. | `string` | `""` | no |
| default\_security\_group\_egress | List of maps of egress rules to set on the default security group | `list(map(string))` | `[]` | no |
| default\_security\_group\_ingress | List of maps of ingress rules to set on the default security group | `list(map(string))` | `[]` | no |
| dhcp\_options\_domain\_name | Specifies DNS name for DHCP options set (requires enable\_dhcp\_options set to true) | `string` | `""` | no |
| dhcp\_options\_domain\_name\_servers | Specify a list of DNS server addresses for DHCP options set, default to AWS provided (requires enable\_dhcp\_options set to true) | `list(string)` | <pre>[<br>  "AmazonProvidedDNS"<br>]</pre> | no |
| dhcp\_options\_netbios\_name\_servers | Specify a list of netbios servers for DHCP options set (requires enable\_dhcp\_options set to true) | `list(string)` | `[]` | no |
| dhcp\_options\_netbios\_node\_type | Specify netbios node\_type for DHCP options set (requires enable\_dhcp\_options set to true) | `string` | `""` | no |
| dhcp\_options\_ntp\_servers | Specify a list of NTP servers for DHCP options set (requires enable\_dhcp\_options set to true) | `list(string)` | `[]` | no |
| enable\_dhcp\_options | Should be true if you want to specify a DHCP options set with a custom domain name, DNS servers, NTP servers, netbios servers, and/or netbios server type | `bool` | `false` | no |
| enable\_dns\_hostnames | A boolean flag to enable/disable DNS hostnames in the VPC. | `bool` | `true` | no |
| enable\_dns\_support | A boolean flag to enable/disable DNS support in the VPC. | `bool` | `true` | no |
| enable\_flow\_log | Enable vpc\_flow\_log logs. | `bool` | `false` | no |
| enabled\_ipv6\_egress\_only\_internet\_gateway | A boolean flag to enable/disable IPv6 Egress-Only Internet Gateway creation | `bool` | `false` | no |
| environment | Environment (e.g. `prod`, `dev`, `staging`). | `string` | `""` | no |
| instance\_tenancy | A tenancy option for instances launched into the VPC. | `string` | `"default"` | no |
| ipv4\_ipam\_pool\_id | The ID of an IPv4 IPAM pool you want to use for allocating this VPC's CIDR. | `string` | `""` | no |
| ipv4\_netmask\_length | The netmask length of the IPv4 CIDR you want to allocate to this VPC. Requires specifying a ipv4\_ipam\_pool\_id | `string` | `null` | no |
| label\_order | Label order, e.g. `name`,`application`. | `list(any)` | `[]` | no |
| managedby | ManagedBy, eg 'CloudDrove' | `string` | `"hello@clouddrove.com"` | no |
| name | Name  (e.g. `app` or `cluster`). | `string` | `""` | no |
| repository | Terraform current module repo | `string` | `"https://github.com/clouddrove/terraform-aws-vpc"` | no |
| restrict\_default\_sg | Flag to control the restrict default sg creation. | `bool` | `true` | no |
| s3\_bucket\_arn | S3 ARN for vpc logs. | `string` | `""` | no |
| tags | Additional tags (e.g. map(`BusinessUnit`,`XYZ`). | `map(any)` | `{}` | no |
| traffic\_type | Type of traffic to capture. Valid values: ACCEPT,REJECT, ALL. | `string` | `"ALL"` | no |
| vpc\_enabled | Flag to control the vpc creation. | `bool` | `true` | no |

## Outputs

| Name | Description |
|------|-------------|
| arn | Amazon Resource Name (ARN) of VPC |
| igw\_id | The ID of the Internet Gateway. |
| ipv6\_cidr\_block | The IPv6 CIDR block. |
| tags | A mapping of tags to assign to the resource. |
| vpc\_cidr\_block | The CIDR block of the VPC. |
| vpc\_default\_network\_acl\_id | The ID of the network ACL created by default on VPC creation. |
| vpc\_default\_route\_table\_id | The ID of the route table created by default on VPC creation. |
| vpc\_default\_security\_group\_id | The ID of the security group created by default on VPC creation. |
| vpc\_id | The ID of the VPC. |
| vpc\_ipv6\_association\_id | The association ID for the IPv6 CIDR block. |
| vpc\_main\_route\_table\_id | The ID of the main route table associated with this VPC. |




## Testing
In this module testing is performed with [terratest](https://github.com/gruntwork-io/terratest) and it creates a small piece of infrastructure, matches the output like ARN, ID and Tags name etc and destroy infrastructure in your AWS account. This testing is written in GO, so you need a [GO environment](https://golang.org/doc/install) in your system. 

You need to run the following command in the testing folder:
```hcl
  go test -run Test
```



## Feedback 
If you come accross a bug or have any feedback, please log it in our [issue tracker](https://github.com/clouddrove/terraform-aws-vpc/issues), or feel free to drop us an email at [hello@clouddrove.com](mailto:hello@clouddrove.com).

If you have found it worth your time, go ahead and give us a ★ on [our GitHub](https://github.com/clouddrove/terraform-aws-vpc)!

## About us

At [CloudDrove][website], we offer expert guidance, implementation support and services to help organisations accelerate their journey to the cloud. Our services include docker and container orchestration, cloud migration and adoption, infrastructure automation, application modernisation and remediation, and performance engineering.

<p align="center">We are <b> The Cloud Experts!</b></p>
<hr />
<p align="center">We ❤️  <a href="https://github.com/clouddrove">Open Source</a> and you can check out <a href="https://github.com/clouddrove">our other modules</a> to get help with your new Cloud ideas.</p>

  [website]: https://clouddrove.com
  [github]: https://github.com/clouddrove
  [linkedin]: https://cpco.io/linkedin
  [twitter]: https://twitter.com/clouddrove/
  [email]: https://clouddrove.com/contact-us.html
  [terraform_modules]: https://github.com/clouddrove?utf8=%E2%9C%93&q=terraform-&type=&language=
