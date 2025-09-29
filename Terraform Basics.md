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

    - Configuration Directory:
        Single configuration file to create the infrastructure/resources
        main.tf - main configuration file containing resource definition
        variables.tf - contains variable declarations
        outpus.tf - Contains output from resources
        providers.tf - contains provider definitions

    - Variables:
        contained in variables.tf file
        Is defined by the 'variable' keyword
        Should generally be named as value being filled
        when using in the resource block, fill in the argument what 'var.variable_name'
        variable parameters:
            default - defines the value of the variable
            type - defines the type of the variable being defined
                string
                boolean
                number
                list
                map
                object
                set - list with no duplicates
                tuple - different, but exact
                any
            description - gives description of variable
        Not having a default for the variable will cause terraform to prompt for input
        Using the '-var' on the command line will allow for inline variables
        Variables can be exported using the "TF_VAR_" prefix
        Variables can be automatically applied automatically using the variable.auto.tfvars file
        Variables can be stored in the terraform.tfvars file (similiar to Ansible vars file) 


    


