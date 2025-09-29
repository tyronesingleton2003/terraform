    - Terraform Commands
        - terraform validate - used to validate the syntax of the terraform configuration
        - terraform fmt - scans terraform file, formatting it in a the proper terraform configuration
        - terraform show - shows all information objects being managed
        - terraform providers - lists all providers currently installed
            - terraform providers lock - locks provider into a specific version 
            - terraform providers mirror /path - copies provider to another directory
        - terraform output - prints output
        - terraform apply -refresh-only - picks up changes that have been done outside of terraform
        - terraform graph - used to create a diagram, showing the dependencies of objects.

    - Mutable Upgrade - Requires requirements to be met before being upgraded
    - Immutable upgrade - Replacing hosts instead of upgrading in-place.

    - Lifecycle Rules:
        - Changes default behavior in creation/destruction of objects
        - 'lifecycle' block is used to changed the lifecycle of an object 
            - create_before_destroy - ensures object is created, before it's destroyed
            - prevent_destroy - preventing object from being destroyed
            - ignore_changes - prevents object from being updated; accepts a list of attributes, or the keyword 'all'
        - Using create_before_destroy with local_file resources is not always advisable, as the file path must be unique for simultaneous creation.

    - Datasources:
        - Allow Terraform to have read attributes from objects, for input, that were created outside of its control.
        - The keyword 'data' is used to define a data source.
        - 'data.resource.object' is used to acquire input from an object.
        - A data source once created, can not be used to create, update, and destroy infrastructure

    - Loops:
        - To create multiple instances of a resource, you can use the 'count' keyword.
            - Using a list makes this 'better'
            - length is used to dynamically count the number of items in a list
            - Drawback is that it can delete a file you wouldn't want deleted
            - Example:
                resource "local_sensitive_file" "name" {
                filename = var.users[count.index] # Count the number in the 'user' list
                content = var.content # Use the content of the variable
                count = length(var.users) # Loop through the list based on the length
                }
                
        - The 'for_each' keyword can be used for creating multiple objects. 
            - Only works with a set or map
            - toset(var.filename)/filename = each.value --- parameters used prevent unwanted deletions
            - Example:
                resource "local_sensitive_file" "name" {
                    filename = each.value
                    content = var.content
                    for_each = toset(var.users)
                }   

                variable "users" {
                    type = list(string)
                    default = [ "/root/user10", "/root/user11", "/root/user12", "/root/user10"]
                }

                variable "content" {
                    default = "password: S3cr3tP@ssw0rd"
                }
    - Versioning:
        - Create an object called 'required_providers' to lock in a version of a provider.
            - keyword 'version' determines what version to use (or not use)
            - ~ only allows for minor version upgrade
