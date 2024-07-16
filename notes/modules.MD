# Modules

A **MODULE** is a **container for multiple resources that are used together**.

- modules are the main way to package & reuse resource configurations w/ terraform 

- You can use modules to create lightweight abstractions, so that you can describe your infrastructure in terms of its architecture, rather than directly in terms of physical objects.

- module consist of a **collection** of .tf and/or .tf.json files in same directory

## Root Module

- Every Terraform configuration has at least **ONE** module, known as its **ROOT** module, which **consists of the resources defined** in the *.tf files* in the *main working directory*.

- *.tf* and/or *.tf.json* in working directory run **TOGETHER** forming the **ROOT** module. **ROOT** module may *call other modules* & *connect them* by *passing output values from one to the input values of another module*.

## Child Module

- A Terraform module (usually the root module of a configuration) can call other modules to include their resources into the configuration. A module that has been called by another module is often referred to as a child module.

- Child modules can be called multiple times within the same configuration, and multiple configurations can use the same child module.

## Published Modules

- In addition to modules from the local filesystem, Terraform can load modules from a public or private registry. This makes it possible to publish modules for others to use, and to use modules that others have published.

- The **Terraform Registry** (https://registry.terraform.io/browse/modules) hosts a broad collection of publicly available Terraform modules for configuring many kinds of common infrastructure. These modules are free to use, and Terraform can download them automatically if you specify the appropriate source and version in a module call block.

- Also, members of your organization might produce modules specifically crafted for your own infrastructure needs. **HCP Terraform** (https://cloud.hashicorp.com/products/terraform) and **Terraform Enterprise** (https://developer.hashicorp.com/terraform/enterprise) both include a private module registry for sharing modules internally within your organization.

## Using Modules
- Module Blocks (https://developer.hashicorp.com/terraform/language/modules/syntax) documents the syntax for calling a child module from a parent module, including meta-arguments like for_each.

- Module Sources (https://developer.hashicorp.com/terraform/language/modules/sources) documents what kinds of paths, addresses, and URIs can be used in the *source* argument of a module block.

- The Meta-Arguments section documents special arguments that can be used with every module, including providers (https://developer.hashicorp.com/terraform/language/meta-arguments/module-providers), depends_on (https://developer.hashicorp.com/terraform/language/meta-arguments/depends_on), count (https://developer.hashicorp.com/terraform/language/meta-arguments/count), and for_each (https://developer.hashicorp.com/terraform/language/meta-arguments/for_each).

## Module Development

