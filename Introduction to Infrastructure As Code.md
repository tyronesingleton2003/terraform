
Types of IAC Tools:
     Configuration management:
          - Uses:
               Designed to Install and Manage Software
               Maintains Standard Structure
               Supports Version Control
               Is Idempotent
          - Tools:
               Ansible
               Puppet
               Chef
               SaltStack

     Server Templating Tools
          - Uses:
               Pre Installed Software and Dependencies
               Virtual Machine or Docker Images
               Immutable Infrastructure
          Tools:
               Docker
               Packer
               Vagrant

     Provisioning Tools:
          - Uses
               Deploy immutable Infrastructure resources
               Servers, Databases, Network Components
               Multiple Providers (Terraform is Cloud Agnostic)
          Tools:
               Terraform
               CloudFormation

     Why Terraform:
     - Terraform is Cloud Agnostic, as it supports different cloud platforms through its "providers". 
       This gives Terraform an advantage over other IAC Tools.

     - Terraform Features:
          Uses HasiCorp Configuration Language
          Has Providers for all Cloud Platforms
          Uses the '.tf' extension for identification

     - Terraform Stages:
          Init - Initializes project and identifies providers to be used for the target environment
          Plan - Develops plan to Get to destired project state
          Apply - Makes changes on the target environment to bring it to the desired state

     - Every Object that Terraform Manages is called a "resource".
     - Terraform "state" is a blueprint of the infrastructure deployed by Terraform (.tfstate)
     - Terraform can import resources created outside of its resources, bringing it under its control and    
       allowing it to be managed.