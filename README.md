# Pulsion project

[ ![Codeship Status for deescut/Pulsion](https://codeship.com/projects/45add3d0-507b-0133-46c0-5abe51be460d/status?branch=master)](https://codeship.com/projects/107676)

## Install

You must download /bin/pulsion of this repository and put it in /usr/local/bin with execute right.
Then, you can go to your project folder and execute :

  ```shell
  pulsion init
  ```

## Usage

After install, you can run at the root of project :

  ```shell
  pulsion
  ```
  
This command list all commands availables in you Pulsion project.

## Create your own commands

You can create your own commands in pulsion/config_pulsion file and run it with pulsion command.

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


## Available helpers

TODO : List and document high level bash functions available in Pulsion by default

  - hasParam
  - verbose
  - getParamValue
  - ...

Have fun !  
