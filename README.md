# terraform

## What is Terraform?
- Is a Infrastructure as a code tool that lets you build, change and version cloud and on prem resources safely and effectively.
- HashiCorp Terraform is an infrastructure as code tool that lets you define both cloud and on-prem resources in human-readable configuration files that you can version, reuse, and share.
- You can then use a consistent workflow to provision and manage all of your infrastructure throughout its lifecycle.
- Terraform can manage low-level components like compute, storage, and networking resources, as well as high-level components like DNS entries and SaaS features.
- Terraform creates and manages resources on cloud platforms and other services through their application programming interfaces (APIs).
- Providers enable Terraform to work with virtually any platform or service with an accessible API.

## Terraform features:
- Terraform supports parallel execution - Terraform does not wait for one resource to finish before starting the next unless there’s a dependency. This means subnets can be created at the same time as long as they don’t depend on each other, speeding up the overall provisioning.
- Automatic dependency management - You do not need to specify in detail the sequence of actions or worry about the interdependencies; Terraform figures that out for you.
- State Management: Terraform keeps track of the current state of the infrastructure and ensures that any changes to the configuration are only applied when necessary. For example, if a resource was already created, Terraform will not recreate it unnecessarily.
  
### The core Terraform workflow consists of three stages:

-->Write: You define resources, which may be across multiple cloud providers and services. For example, you might create a configuration to deploy an application on virtual machines in a Virtual Private Cloud (VPC) network with security groups and a load balancer.

-->Plan: Terraform creates an execution plan describing the infrastructure it will create, update, or destroy based on the existing infrastructure and your configuration.

-->Apply: On approval, Terraform performs the proposed operations in the correct order, respecting any resource dependencies. For example, if you update the properties of a VPC and change the number of virtual machines in that VPC, Terraform will recreate the VPC before scaling the virtual machines.

## State File - Tracking the infrastructure
Terraform generates a plan and prompts you for your approval before modifying your infrastructure. It also keeps track of your real infrastructure in a state file, which acts as a source of truth for your environment. Terraform uses the state file to determine the changes to make to your infrastructure so that it will match your configuration.

-->Terraform configuration files are declarative, meaning that they describe the end state of your infrastructure.

-->You do not need to write step-by-step instructions to create resources because Terraform handles the underlying logic.

-->Terraform builds a resource graph to determine resource dependencies and creates or modifies non-dependent resources in parallel. This allows Terraform to provision resources efficiently.

-->Terraform supports reusable configuration components called modules that define configurable collections of infrastructure, saving time and encouraging best practices.

-->Since your configuration is written in a file, you can commit it to a Version Control System (VCS) and use HCP Terraform to efficiently manage Terraform workflows across teams. HCP Terraform runs Terraform in a consistent, reliable environment and provides secure access to shared state and secret data, role-based access controls, a private registry for sharing both modules and providers, and more.

### Variables
- Terraform input variables are used to pass certain values from utside of the configuration.
- Hashicorp recommends creating a seperate file with the name of *.tfvars to define all variables in a project.

Structure of defining variables in a project:
   1. main configuration file
   2. variables.tf where we define all the variables
   3. terraform.tfvars where we defines the values of all the variables


