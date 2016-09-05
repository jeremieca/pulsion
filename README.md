# Pulsion project

[ ![Codeship Status for deescut/Pulsion](https://codeship.com/projects/45add3d0-507b-0133-46c0-5abe51be460d/status?branch=open-source)](https://codeship.com/projects/107676)
[![Build Status](https://semaphoreci.com/api/v1/jeremieca/pulsion/branches/open-source/badge.svg)](https://semaphoreci.com/jeremieca/pulsion)

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

  - **Reduce barriers to entry on project** : To manage all the project, developpers have just one command to use regardless of your stack : ```pulsion``` (instead of grunt, gulp, mongod, mvn, npm, bower...)
  - **Write complex bash cli easily and very fast** : bash is one of the most universal and documented language. Howhever it is not always easy to use. It's why Pulsion provides functions and conventions in top of bash that transform it in a smart language.
  - **Gather all your projects in one place** : Front, back, database, deployment in one place. You can build a project hierarchy. Pulsion project can import another Pulsion project. So, you can have a unique place where all commands on a very very large project are centralized (ex: backend, frontend, database, deployment...).
  - **Light and easy to export** : Pulsion have no external dependencies, we just need bash (available by default on linux, osx (and windows soon)) to launch it. So, if you move your project on a new machine, import your project folder is enough to use pulsion. Install is optionnal to launch pulsion.


### Install

  1. Download ```/bin/pulsion```  
  2. Move it in ```/usr/local/bin``` with execute right.  
  3. Go to your project folder and execute ``` pulsion init ```  

Your first pulsion project is now created.

### Usage

After install, you can run at the root of project :

  ```shell
  pulsion
  ```

This command list all commands availables in your current Pulsion project.

### Create your own commands

You can create your own commands in pulsion/config_pulsion file and run it with pulsion command.

A Pulsion command looks like that :

```shell
function command_hello { # create a hello command

	function help {      # user can add --help or -h argument to display help

		echo "Example of pulsion command"

	}

	function process {   # your bash script

		if has_param --introduce-me "$@"; then   # helpers functions help you to develop faster
			print 1 "Hello world !"
			print 1 "My name is Pulsion"
		else
			print 1 "Hello world !"
		fi

	}

}
```

```
pulsion hello --introduce-me

# Hello world !
# My name is Pulsion
```

[Create your own command with Pulsion](https://github.com/jeremieca/pulsion/wiki/Create-your-own-command)

### Helpers

Helpers are predefined functions that help you to develop your bash scripts faster and safer.

  - [Generic helpers](https://github.com/jeremieca/pulsion/wiki/Helpers#generic-helpers) : Small easy to user functions (print, require_root, get_platform...)
  - [Stream helpers](https://github.com/jeremieca/pulsion/wiki/Helpers#stream-helpers) : Easly manage stdin and stdout feeds with filter, duplicators, actions...


### Pulsion for very large projects

You can import a pulsion project in another.

Imagine you have multiple pulsion projects for backend, frontend and deployment. But you need a unique place to manage all your project. So, you can just create a new pulsion project and import the three others.

[Know more about Import](https://github.com/jeremieca/pulsion/wiki/Projects-hierarchy)

### Status of project

Pulsion continuous integration run on Linux but Pulsion also works on OSX (we use it everyday) and on Windows (with bash emulator).  
  
Currently, Pulsion require Git to be updated easily. But soon, we'll remove this dependency between Pulsion and Git. Then, the only dependency to use Pulsion will be bash (>= 3).  
  
Note that Pulsion **is under heavy development**. Your issues and pull request are welcome.

Have fun !  
