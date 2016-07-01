# Pulsion project

[ ![Codeship Status for deescut/Pulsion](https://codeship.com/projects/45add3d0-507b-0133-46c0-5abe51be460d/status?branch=master)](https://codeship.com/projects/107676)

## Description

Pulsion centralize all commands of your project in one unique place with no pain.

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

### Why to use it ?

	- Pulsion have no external dependencies, we just need bash (available by default on linux, osx (and windows soon))
	- Pulsion can be use without any install (but we provide a small optionnal script to help you create a new pulsion project and use it daily)
	- You write your scripts in bash. Bash is one of the most universal language. Moreover, Pulsion provides some functions in top of bash to write your scripts faster (seen Available helpers)
	- Coming soon : You can build a project hierarchy. Pulsion project can import another Pulsion project. So, you can have a unique place where all commands on a very very large project are centralized (ex: backend, frontend, database, deployment...)

### Status of project

We use Pulsion massively on OSX without any problems for 2 years. However, Pulsion **is under heavy development** and need to be tested on multiples platforms. Your issues and pull request are welcome.

## Install

!! This step is optionnal but recommanded if you want to discover Pulsion easily or use it dayli !!

You must download /bin/pulsion of this repository and put it in /usr/local/bin with execute right.
Then, you can go to your project folder and execute :

  ```shell
  pulsion init
  ```

Your first pulsion project is now created.

## Usage

After install, you can run at the root of project :

  ```shell
  pulsion
  ```

This command list all commands availables in your current Pulsion project.

## Create your own commands

You can create your own commands in pulsion/config_pulsion file and run it with pulsion command.

### Overview

A command looks like that :

```shell
function command_hello {

	function help {

		echo -e "Example of pulsion command"

	}

	function process {

		if hasParam --name "$@"; then
			myname="$(getParamValue --name "$@")"
			verbose 1 "Hello $myname !"
		else
			verbose 1 "Hello world !"
		fi

	}

}
```

### Define a new command

A Pulsion command is a function. The name of this function start with ```command_```.
A command contain two functions : ```help``` and ```process```.
For example, the command ```command_hello``` can be use with ```pulsion hello``` command in terminal.

### Help function

The help function is used when you call a pulsion command with -h parameter.
For example ```pulsion hello -h```

You can describe inside the help function the doc of your command.

### Process function

Here you can write your bash script. Using helpers you can develop you bash script faster than ever.

### Available helpers

Pulsion help you to develop your bash script faster. It provides a list of functions to make generic actions in your command process. This functions, available by default in Pulsion, are called helpers.

TODO : List and document all helpers

  - hasParam
  - verbose
  - getParamValue
  - ...

#### Contributions to helpers

If you think that an helper can be added, create an issue and talk us about it or push a pull request.

## Upgrade your pulsion project

Once your pulsion project is configured, you can update it using auto-update command.

```
pulsion auto-update
```

Note that Pulsion project are independant and Pulsion will be updated only for the current project.

Have fun !  
