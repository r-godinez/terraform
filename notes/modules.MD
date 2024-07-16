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


