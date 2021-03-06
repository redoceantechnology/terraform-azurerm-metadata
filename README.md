# Azure - Metadata Module

## Introduction

This module will return a map of mandatory tag for resources in Azure.<br />
<br />
It is recommended that you always use this module to generate tags as it will prevent code duplication. We also recommend leveraging this data as "metadata" to determine core details about resources in other modules.

- For example the location output can be referenced when creating a virtual machine. If you want to change regions at a later date you only need to update one place.<br />

Where applicable, the inputs will be checked against the input naming rules for Azure.

- https://github.com/Azure-Terraform/example-naming-template/<br />

This Module are based on (https://github.com/Azure-Terraform/terraform-azurerm-metadata)

<!--- BEGIN_TF_DOCS --->
## Providers

| Name | Version |
|------|---------|
| azurerm | >= 2.0.0 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:-----:|
| additional\_tags | A map of additional tags to add to the tags output | `map(string)` | `{}` | no |
| business\_unit | rba.businessUnit (https://github.com/Azure-Terraform/example-naming-template#custombusinessunit) | `string` | n/a | yes |
| customer | rba.customer (https://github.com/Azure-Terraform/example-naming-template#customcustomer) | `string` | n/a | yes |
| environment | rba.environment (https://github.com/Azure-Terraform/example-naming-template#customenvironment) | `string` | n/a | yes |
| location | rba.azureRegion (https://github.com/Azure-Terraform/example-naming-template#customazureregion) | `string` | n/a | yes |
| market | rba.market (https://github.com/Azure-Terraform/example-naming-template#custommarket) | `string` | n/a | yes |
| naming\_rules | naming conventions yaml file | `string` | n/a | yes |
| on\_prem | rba.onPrem (https://github.com/Azure-Terraform/example-naming-template#customonprem) | `string` | `""` | no |
| product\_group | rba.productGroup (https://github.com/Azure-Terraform/example-naming-template#customproductgroup) or [a-z0-9]{2,12} | `string` | n/a | yes |
| product\_name | rba.productName (https://github.com/Azure-Terraform/example-naming-template#customproductname) | `string` | n/a | yes |
| project | Jira Project | `string` | n/a | yes |
| resource\_group\_type | rba.resourceGroupType (https://github.com/Azure-Terraform/example-naming-template#customresourcegrouptype) | `string` | n/a | yes |
| service\_name | rba.serviceName (https://github.com/Azure-Terraform/example-naming-template#customservicename) | `string` | `""` | no |
| sre\_team | SRE Team owner | `string` | `""` | no |
| subnet\_type | rba.subnetType (https://github.com/Azure-Terraform/example-naming-template#customsubnettype) | `string` | `""` | no |
| subscription\_id | Azure Subscription ID | `string` | n/a | yes |
| subscription\_type | rba.subscriptionType (https://github.com/Azure-Terraform/example-naming-template#customsubscriptiontype) | `string` | n/a | yes |
| virtual\_network\_gateway\_type | virtualNetGwType (https://github.com/Azure-Terraform/example-naming-template#customvirtualnetgwtype) | `string` | `""` | no |

## Outputs

| Name | Description |
|------|-------------|
| location | Azure region |
| location\_pair | Azure paired region |
| names | Map of validated names for resources |
| tags | Map of tags with any global defaults appended |
<!--- END_TF_DOCS --->