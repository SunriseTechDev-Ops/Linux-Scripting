# Linux-Scripting
linux scripting



User Defined Variables


!/bin/bash      
#title           :
#description     :
#author		     :sunrise tech (noel balingwe)
#date            :01/06/2022
#version         :1.0    

name="noel balingwe"
id="12345"
echo "The name varibale value is: "$name
echo "The id variable value is: "$id



Command Line Arguments


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



strings



string_var="Hi Team, My name is  noel balingwe, working  at SRT"

echo "The value of string_var value is: " ${string_var}

echo "The length of the string is: " ${#string_var}

echo "The sub string is:"  ${string_var:20:14}

#Index from right end  of the string
echo The sub tring value is:  ${string_var: (-8)}

echo The sub tring value is:  ${string_var: -17}



#title           : Arithmetic operations



expr 3 + 2
expr 3 - 2
expr 3 \* 2
expr 10 / 2
expr 20 % 3
echo addition of 3 and 2 is : `expr 3 + 2`
