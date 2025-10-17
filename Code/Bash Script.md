## scripting x programming
The main difference is that scripting don't need to compile the code 

## Starting the script
```shell-session
./script.sh <optional arguments>
bash script.sh <optional arguments>
```

its basically the same usage as a normal command
obs: to give executable permission: 
```shell-session
chmod +x script.sh
```


## Conditional Execution
```bash
#!/bin/bash

# Check for given argument
if [ $# -eq 0 ]
then
	echo -e "You need to specify the target domain.\n"
	echo -e "Usage:"
	echo -e "\t$0 <domain>"
	exit 1
else
	domain=$1
fi

<SNIP>
```
- #!/bin/bash - shebang ( says to the [[SO]] which interpreter to use )
- if-else-fi - normal if else and we know where it ends with the fi 
- comparison operators `-eq` `-gt` `-lt`  
## Arguments 
- `$#` / `$0` / `$1` - Special variables. 
- `$#` - number of arguments
- `$@` - This variable can be used to retrieve the list of command-line arguments.
- `$$` The process ID of the currently executing process.
- `$n` -  is the n'th argument up to 9
- `$?` The exit status of the script. This variable is useful to determine a command's success. The value 0 represents successful execution.

