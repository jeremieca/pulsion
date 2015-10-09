# Pulsion project

The high productivity library to develop development tools in bash. The repository contains :  

  - Pulsion project development folder  
  - Scripts folder for development tools  
  - Tests folder  
  - Output folder  

[ ![Codeship Status for deescut/Pulsion](https://codeship.com/projects/4a7bfc80-5021-0133-13af-6686e2a963df/status?branch=master)](https://codeship.com/projects/107567)

## Complete the project installation

You must get the last fusionned version of Pulsion script :  

    :::shell 
        sudo scripts/get_pulsion [[ branch name | "master" as default ]]  

Then, you can access to the pulsion application with the following command :  

    :::shell 
        sudo scripts/pulsion  

## Struture branches

  - Master : Always stable  
  - Feature/* : Development of a specific feature  
  
# Develop with Pulsion

Pulsion facilitates the development of scripts routine in your projects. Simply implement the deployment of test routines, scripts installation. Pulsion offers a fully customizable architecture for your projects.  

## Structure projects

A Pulsion project is generally structured as follows :  

  - Scripts folder : Contains Pulsion script and the configuration file of Pulsion "config_pulsion"  
  - Project folder : Contains the sources of the project  
  - Tests : Contains the tests of the project  
  - Config : Contains the specific configuration to a user  

### Write .gitignore for a Pulsion project

    :::shell
        # Pulsion configuration
        pulsion/*
        !pulsion/config
        pulsion/config/*
        !pulsion/config/*_default
        !pulsion/config/*_default
        !pulsion/config_pulsion
        !pulsion/get_pulsion
        !pulsion/extern

Usually, a getPulsion script is create in scripts folder. It download the lastest version of Pulsion. You have one Pulsion version in each project you develop.  

## Implement config_pulsion script

The scripts/config_pulsion file contains all your routines project.
You can add a routine developing a new command.  

## Deployment configuration

You can easily develop routines deployment using the "deploy" command.  
  
Have fun !  
