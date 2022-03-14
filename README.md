# cli-terraform-builds
Temporary! CLI Terraform Builds.

Builds for the Akamai Terraform CLI that includes create-appsec command.

My steps:

1) Download the cli-terraform build and put it in a clean folder.
2) Navigate to folder in your terminal
3) Run ./cli-terraform-macos --section securitylevelup create-appsec wildcard.securitylevelup.eu (NOTE: your own edgec section and config name of course)
4) Add the contract ID and group ID values to your appsec-variables.tf file OR create a terraform.tfvars file - save that file. You can use the CLI to grab those values. DO NOT USE grp_ for Group ID. It does not like that.
variable "group_id" { default = "156905" }
variable "contract_id" { default = "ctr_P-31YPZJ9" }
BONUS) if your edgerc section is not default - update line 3 in appsec-main.tf for the right section, otherwise the next step won't work.
5) Run sh appsec-import.sh on terminal - Init and import will take several minutes
6) Run terraform plan and verify what will be added/changed.

ERROR? Copy it in here so we can solve it.

7) Run terraform apply and verify what is being changed, should only be activation.

ERROR? Copy it in here so we can solve it.

I did this for my own config and so far, this all works fine. In less than 5-7 minutes, I went from having an Akamai AppSec KRS+AAG file to a fully compatible Terraform code and had to code … ahem… 2 lines of variables. 
