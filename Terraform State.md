    - Terraform State:
        - Doesn't exist prior to 'terraform apply' being run
        - Stored in the 'terraform.tfstate' file, with the a unique ID associated with the transactions it just made.
        - Terraform state file is the single source of truth.
        - Allows tracking of drift between current state and resource config files
        - Should have state file in remote location when collaborating with a team.
        - terraform play --refresh=false disbles refreshing the terraform state
        - It is refreshed when the 'plan' and 'apply' options are exeercise, but not with 'init'.
        