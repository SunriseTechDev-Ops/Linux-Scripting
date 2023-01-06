## Linux-Scripting
#linux scripting     
#author		 :sunrise tech (noel balingwe)
#date            :01/06/2022
#version         :1.0 

## User Defined Variables

``` sh
#!/bin/bash 
name="noel balingwe"
id="12345"
echo "The name varibale value is: "$name
echo "The id variable value is: "$id
```
## Command Line Arguments
``` sh
#!/bin/bash 
#Number of arguments on the command line.
echo '$#:' $#
#Process number of the current process.
echo '$$:' $$
#Display the 3rd argument on the command line, from left to right.
echo '$3:' $3
#Display the 10th argument on the command line, from left to right.
echo '${10}:' ${10}
#Display the name of the current shell or program.
echo '$0:' $0
#Display all the arguments on the command line using * symbol.
echo '$*:' $*
#Display all the arguments on the command line using @ symbol.
echo '$@:' $@
date
echo '$?:' $?
#if (( $# >= 3 ))
#if [ $# -gt 3 ]
#if [ $# -lt 3 ]
if (( $# == 3 ))
then
#Number of arguments on the command line.
echo '$#:' $#
#Process number of the current process.
echo '$$:' $$
#Display the 3rd argument on the command line, from left to right.
echo '$3:' $3
#Display the 10th argument on the command line, from left to right.
echo '${10}:' ${10}
#Display the name of the current shell or program.
echo '$0:' $0
#Display all the arguments on the command line using * symbol.
echo '$*:' $*
#Display all the arguments on the command line using @ symbol.
echo '$@:' $@
date
echo '$?:' $?
else
echo "Please Pass the 3 command line args along with script"
```
## strings
``` sh
#!/bin/bash 
string_var="Hi Team, My name is  noel balingwe, working  at SRT"

echo "The value of string_var value is: " ${string_var}

echo "The length of the string is: " ${#string_var}

echo "The sub string is:"  ${string_var:20:14}

#Index from right end  of the string
echo The sub tring value is:  ${string_var: (-8)}

echo The sub tring value is:  ${string_var: -17}
```

## Arithmetic operations
``` sh
#!/bin/bash 
expr 3 + 2
expr 3 - 2
expr 3 \* 2
expr 10 / 2
expr 20 % 3
echo addition of 3 and 2 is : `expr 3 + 2`
```
## Arrays
``` sh
#!/bin/bash 
declare -a devopstools
devopstools[0]=GitHub
devopstools[1]=Ant
devopstools[2]=Maven
devopstools[3]=Tomcat
devopstools[4]=Wildfly
devopstools[5]=SonarQube


#Displaying 1st value
echo ${devopstools[0]}

#Displaying 5th value
echo ${devopstools[4]}

#Displaying all values
echo ${devopstools[*]}

#Displaying all values

echo ${devopstools[@]}
```

## Reading inputs
``` sh
#!/bin/bash 
echo "Please enter your name"
read name
echo "Your name is: " $name
echo please enter 1st number1
read number1
echo please enter 2nd number2
read number2
echo The sum is `expr $number1 + $number2`
```

## creating a user
## With simple commands
``` sh
#!/bin/bash 
#Creating a user
echo "Please enter the user name for the account you want to create!"
read userName
echo "The name you entered is: "  $userName
/usr/sbin/useradd   $userName
/usr/sbin/usermod -G devops $userName
echo ".......User is created..........."
echo ".......Now Set the password for  ....... $userName"
passwd $userName
```
# Purpose - Script to add a user to Linux system with passsword
## Remember you have to be Root user or has root previlleges?
``` sh
if [ $(id -u) -eq 0 ]; then
	read -p "Enter username : " username
	read -s -p "Enter password : " password
	egrep "^$username" /etc/passwd >/dev/null
	if [ $? -eq 0 ]; then
		echo "$username exists!"
		exit 1
	else
		pass=$(perl -e 'print crypt($ARGV[0], "password")' $password)
		useradd -m -p "$pass" "$username"
		[ $? -eq 0 ] && echo "User has been added to system!" || echo "Failed to add a user!"
	fi
else
	echo "Only root may add a user to the system."
	exit 2
fi
```
## Create user and grant sudo access
``` sh

#!/bin/bash 
if [ $# -ne 1 ]
then
  echo "Usage: $0  username"
  exit
else
  USERNAME=$1
fi

# creating user
/usr/sbin/useradd $USERNAME
passwd $USERNAME

echo "User has created successfully.."
echo "Providing sudo access.."

# Giving sudo access
sed -i "/NOPASSWD/a\\$USERNAME ALL=(ALL)       NOPASSWD: ALL" /etc/sudoers

echo "Sudo access successfully granted to $USERNAME"
```
# Loops
## For loop
```sh
#!bin/bash
echo "For loop starts.."
for (( i=98; i<=100; i++))
do
echo $i
done
echo "Loop is done.."
```
## while loop
``` sh
#!bin/bash
echo "while demo loop ..."
i=1
while [ $i -le 5 ]
do
echo $i
i='expr $i + 1'
done
echo "while loop is over"
```
