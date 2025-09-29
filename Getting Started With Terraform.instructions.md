Method for Installing Terraform
    - Pull zip file from HashiCorp and unzip
    - mv terraform executable to user's path.


HashiCorp Language consists of blocks and arguments.

Resources
    A resource is an object that Terraform that terraform managers.
    Resource blocks are identified by the word 'resource'.
    A resource block is compiled of the following:
        resource - identifies the block type
        provider - provider of the resource type
        resource - type of resource to be managed
        name - name of the resource to be managed

Terraform uses an immutable methodology.  Instead of making updates to an object, it will destroy and recreate the object.
