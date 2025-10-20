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
- #!/bin/bash - shebang ( says to the [[SO]] which [[interpreter]] to use )
- if-else-fi - normal if else and we know where it ends with the fi 
## Arguments 
- `$#` / `$0` / `$1` - Special variables. 
- `$#` - number of arguments
- `$@` - This variable can be used to retrieve the list of command-line arguments.
- `$$` The process ID of the currently executing process.
- `$n` -  is the n'th argument up to 9
- `$?` The exit status of the script. This variable is useful to determine a command's success. The value 0 represents successful execution.

## Variables and Array

```
#variable
var = "asd ad" #don't need the "" if doesn't have special characters
var2 = 2

#array
array = (x y z)
echo ${array[0]}
```

## Operators

- comparison operators `-eq` `-gt` `-lt`  for integers
- `=` contains into
- `==` is equal to
- `!=` is not equal to
- `<` is less than in ASCII alphabetical order
- `>` is greater than in ASCII alphabetical order
- `-z` if the string is empty (null)
- `-n` if the string is not null
### File Operators
- `-e` if the file exists 
- `-f` tests if it is a file
- `-d` tests if it is a directory
- `-L` tests if it is a symbolic link
- `-N` checks if the file was modified after it was last read
- `-O` if the current user owns the file
- `-G` if the file's group id matches the current user's
- `-s` tests if the file has a size greater than 0
- `-r` tests if the file has read permission
- `-w` tests if the file has write permission
- `-x` tests if the file has execute permission
### Logical Operators
- `!` logical negation NOT
- `&&` logical AND
- `&&` logical OR
### Arithmetic Operators

- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division
- `%` Modulus
- `variable++` Increase the value of the variable by 1
- `variable--` Decrease the value of the variable by 1
- `${#variable}` Counts the letters 
## Flow

```bash
for variable in 1 2 3 4
do
	echo $variable
done
```

```bash
while [ $variable -lt 10 ]
do
	echo $variable
	((variable++))
done
```

