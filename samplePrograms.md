
check the given Number is even or odd
    #!/bin/sh
	read -p "Enter the number : " myNumber 
	if [ $((myNumber%2)) -eq 0 ]
	then
	  echo "The ${myNumber} is Even"
	else
	  echo "The ${myNumber} is ODD"
	fi

Nested if / elif 

    #!/bin/bash
	read -p "Enter a number : " n
	if [ $n -gt 0 ]; then
	  echo "$n is a positive."
	elif [ $n -lt 0 ]
	then
	  echo "$n is a negative."
	elif [ $n -eq 0 ]
	then
	  echo "$n is zero number."
	else
	  echo "Oops! $n is not a number."
	fi

Find the user is present or in the UNIX

    #!/bin/bash
	# set var 
	PASSWD_FILE=/etc/passwd
	# get user name
	read -p "Please Enter a user name : " userNameTemp
	# try to locate username in in /etc/passwd
	grep "^$username" $PASSWD_FILE > /dev/null
	# store exit status of grep
	# if found grep will return 0 exit stauts
	# if not found, grep will return a nonzero exit stauts
	status=$?
	if test $status -eq 0
	  then
	  echo "User '$username' found in $PASSWD_FILE file."
	else
	  echo "User '$username' not found in $PASSWD_FILE file."
	fi

List the user's in the Unix box/System

    #!/bin/sh
	echo "Try to list the all the user in the unix terminal"
    cut -d ":" -f 1 /etc/passwd > userlist.txt
    cat userlist.txt
	
List the groups in the Unix box/System
    #!/bin/sh
    cut -d ":" -f 1 /etc/group > grouplist.txt
    echo "list the group user"
    cat grouplist.txt
	
List the user/group in the Unix box using for loop 

    #!/bin/sh
	# for user use file /etc/passwd
	# for groups use file /etc/group
	for varTemp in `cut -d ":" -f 1 /etc/passwd`
	do 
	 echo "User in the box are ${varTemp}"
	done
	
List the user/group with serial number in the Unix Terminal 
    #!/bin/sh
    echo "Try to list the all the user in the unix terminal"
    i=1
    for varTemp in `cut -d ":" -f 1 /etc/passwd`
    do
        echo "Active User ${i}- ${varTemp}"
        i=$((i+1))
    done
	echo "Total number of user in the Unix box is -- $((i-1))"

Space usage of file in the unix box

    #!/bin/sh
     space_free=$( df -h | awk '{ print $5 }' | sort -n | tail -n 1 | sed 's/%//' )
     case $space_free in
     [1-5]*)
       echo "${space_free} are used space no need to worry" 
     ;;
     [6-7]*)
       echo "${space_free} are used space, There could be a problem in the near future"
     ;; 
    8*)
     echo "${space_free} are used space, Maybe we should look at clearing out old files"
	 ;;
	 9*)
     echo "${space_free} are used space, We could have a serious problem on our hands soon"
	 ;;
	 *)
	 echo "Something went wrong" 
     ;;
    esac
