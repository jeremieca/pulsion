# Pulsion project

[ ![Codeship Status for deescut/Pulsion](https://codeship.com/projects/45add3d0-507b-0133-46c0-5abe51be460d/status?branch=open-source)](https://codeship.com/projects/107676)

### Description

**Pulsion centralize all commands of your project in one unique place with no pain.**

You can easily create aliases for all your terminal commands and create your own command line tool in few minutes.
Just use our high level bash tool to manage your commands.

When your project is configured, you can from a unique place :

  - Start your database
  - Install dependencies
  - Compile your code
  - Deploy your project
  - ...
  - And all other things you want to do

Pulsion is initially a tool for developper or sysadmin in a development environment.

#### Why to use it ?

  - Pulsion have no external dependencies, we just need bash (available by default on linux, osx (and windows soon))
  - You write your scripts in bash. Bash is one of the most universal language. Moreover, Pulsion provides some functions in top of bash to write your scripts faster (seen Available helpers)
  - You can build a project hierarchy. Pulsion project can import another Pulsion project. So, you can have a unique place where all commands on a very very large project are centralized (ex: backend, frontend, database, deployment...)

### Install

1) Download ```/bin/pulsion```  
2) Move it in ```/usr/local/bin``` with execute right.  
3) Go to your project folder and execute ``` pulsion init ```  

Your first pulsion project is now created.

### Usage

After install, you can run at the root of project :

  ```shell
  pulsion
  ```

This command list all commands availables in your current Pulsion project.

## Create your own commands

You can create your own commands in pulsion/config_pulsion file and run it with pulsion command.

A Pulsion command looks like that :

```shell
function command_hello {    # hello is the name of command

	function help {     # help is the function executed when user add --help or -h argument

		echo -e "Example of pulsion command"

	}

	function process {  # process is the function to execute when command is launched

		if has_param --name "$@"; then                   # has_param is an helper to check if an argument exist
			myname="$(get_param_value --name "$@")"  # get_param_value is an helper to get value of an argument
			verbose 1 "Hello $myname !"
		else
			verbose 1 "Hello world !"                # verbose provide multiple levels of echo (error, warn...)
		fi

	}

}
```

[Create your own command with Pulsion](https://github.com/jeremieca/pulsion/wiki/Create-your-own-command)

### Import other pulsion project

You can import pulsion projects in another.

Imagine you have a pulsion project for backend, frontend and deployment. But you need a unique place to manage all your project. So, you can just create a new pulsion project and import the three others.

[Know more about Import](https://github.com/jeremieca/pulsion/wiki/Projects-hierarchy)

### Helpers

Helpers are functions that help you to develop your bash scripts faster.

[All helpers](https://github.com/jeremieca/pulsion/wiki/Helpers)

### Status of project

We use Pulsion massively on OSX without any problems for 2 years. However, Pulsion **is under heavy development** and need to be tested on multiples platforms. Your issues and pull request are welcome.

Have fun !  
