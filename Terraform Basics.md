    - Terraform Providers:
        Plugins for providers are downloaded when using terraform init
        Are a part of a plugin architecture, used by Terraform
        Distributed by HashiCorp and publicy available at registry.terraform.io
        Downloaded in a hidden directory (.terraform)

    - Terraform Provider Tiers:
        Official
        Partner
        Community
    
    -  The plugin name is also known as the source address.  It is comprised of the following:
        Organizational Namespace
        Resource Type
        Hostname (source of resource. This is optional)

    - Configuration Directory
        Single configuration file to create the infrastructure/resources
        main.tf - main configuration file containing resource definition
        variables.tf - contains variable declarations
        outpus.tf - Contains output from resources
        providers.tf - contains provider definitions
        

