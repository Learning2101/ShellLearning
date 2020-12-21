Variable is storing the values in the defined name

Mainly shell Variables are 3 types those are 
 
   1. Envrionment\System Variables
   2. Local Varaible 
   3. Shell Varaible
   
   
   Environment variables are dynamic values which affect the processes or programs on a computer.
   
| Command | Purpose | Example Command | 
| ------ | ------ | ---- |
| $env or $printenv or $set | display all system/envrionment variable | $printenv | 
| variable_name= variable_value |setting or updating the variable | myvar= testvalue set $myvar |
| unset variable_name |Deleting Variables |unset myvar | 

#### Dont leave space between variablename and = sign otherwise we may encouter an error

```sh
$ env
$ printenv
$ echo $variablename
$ myvar= <<variablename>>
$ export $myvar
$ echo $myvar
$ unset $<<variablename>>
$ unset $myvar
```


Variable Names can contain only letters , number or the underscore character _
  - letters (a to z or A to Z)
  - numbers ( 0 to 9)
  - underscore character (_)
   
  
variable_name=variable_value
example myVariable= testvalue
```sh 
myVariable= testvalue
```
to view or dispaly 
echo $variable_name
```sh 
echo $variable_name
```

Read-only Variables
Shell provides a way to mark variables as read-only by using the read-only command. After a variable is marked read-only, its value cannot be modified 

```sh
myVariable="test myvalue"
readonly myVariable
myVariable="myVariablechange"
```

Unsetting Variables


| Purpose  | Command | Example Command | 
| ------ | ------ | ---- |
| Set Variable | variable_name= <<variable_value>> | myVariable="test myvalue" | 
| Set Readonly Variable| readonly <<variable_name>>| readonly myVariable |
| unset variable | unset  <<variable_name>>  |unset myVariable | 



| Command   | Description |  
| ------ | ------ |
| $0 | The file name of the script | 
| $n | the first argument is $1 and second argument $2 and so on |
| $# | The number of arguments supplied to a script. |
| $* | All the arguments are double quoted |
| $@ | All the arguments are individually double quoted. |
| $? | The exit status of the last command executed. |


```sh 
#!/bin/sh

echo "File Name(0th argument): $0"
echo "First Parameter(1st argument) : $1"
echo "Second Parameter(2nd argument) : $2"
echo "Quoted Values ($@values): $@"
echo "Quoted Values ($*Values): $*"
echo "Total Number of Parameters ($#values): $#"
```
