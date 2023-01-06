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
