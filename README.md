# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
^d
```
### Display the content of the files

## OUTPUT
cat < file1
![Alt text](img/Screenshot_001.png)

## OUTPUT
cat < file2
![Alt text](img/Screenshot_002.png)
# Comparing Files

## OUTPUT
cmp file1 file2
![Alt text](img/Screenshot_003.png)
 ## OUTPUT
comm file1 file2
![Alt text](img/Screenshot_004.png)
## OUTPUT
diff file1 file2
![Alt text](img/Screenshot_005.png)
# Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```

## OUTPUT
cut -c1-3 file11
![Alt text](img/Screenshot_006.png)
![Alt text](img/Screenshot_008.png)
## OUTPUT
cut -d "|" -f 1 file22
![Alt text](img/Screenshot_007.png)
![Alt text](img/Screenshot_009.png)
## OUTPUT
cut -d "|" -f 2 file22
![Alt text](img/Screenshot_010.png)

### Create the following file newfile as follows:

cat < newfile 
```
Hello world
hello world
^d
```

## OUTPUT
grep Hello newfile 
![Alt text](img/Screenshot_013.png)
## OUTPUT
grep hello newfile 
![Alt text](img/Screenshot_013.png)
## OUTPUT
grep -v hello newfile 
![Alt text](img/Screenshot_014.png)

## OUTPUT
cat newfile | grep -i "hello"
![Alt text](img/Screenshot_015.png)

## OUTPUT
cat newfile | grep -i -c "hello"
![Alt text](img/Screenshot_015.png)

## OUTPUT
grep -R ubuntu /etc
![Alt text](img/Screenshot_016.png)
## OUTPUT
grep -w -n world newfile   
![Alt text](img/Screenshot_017.png)
### Create the following file newfile as follows:

cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```


## OUTPUT
egrep -w 'Hello|hello' newfile 
![Alt text](img/Screenshot_019.png)
![Alt text](img/Screenshot_020.png)
## OUTPUT
egrep -w '(H|h)ello' newfile 
![Alt text](img/Screenshot_021.png)
## OUTPUT
egrep -w '(H|h)ell[a-z]' newfile 
![Alt text](img/Screenshot_023.png)
## OUTPUT
egrep '(^hello)' newfile 
![Alt text](img/Screenshot_024.png)
## OUTPUT
egrep '(world$)' newfile 
![Alt text](img/Screenshot_025.png)

## OUTPUT
egrep '((W|w)orld$)' newfile 
![Alt text](img/Screenshot_027.png)
## OUTPUT
egrep '[1-9]' newfile 
![Alt text](img/Screenshot_028.png)
## OUTPUT
egrep 'Linux.*world' newfile 
![Alt text](img/Screenshot_030.png)
## OUTPUT
egrep l{2} newfile
![Alt text](img/Screenshot_030.png)

## OUTPUT 
egrep 's{1,2}' newfile
![Alt text](img/Screenshot_031.png)
### Create the following file file23 as follows:
cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```

## OUTPUT
sed -n -e '3p' file23
![Alt text](img/Screenshot_032.png)
![Alt text](img/Screenshot_033.png)
## OUTPUT
sed -n -e '$p' file23
![Alt text](img/Screenshot_034.png)
## OUTPUT
sed  -e 's/Ram/Sita/' file23
![Alt text](img/Screenshot_035.png)
## OUTPUT
sed  -e '2s/Ram/Sita/' file23
![Alt text](img/Screenshot_036.png)
## OUTPUT
sed  '/tom/s/5000/6000/' file23
![Alt text](img/Screenshot_037.png)
## OUTPUT
sed -n -e '1,5p' file23
![Alt text](img/Screenshot_038.png)
## OUTPUT
sed -n -e '2,/Joe/p' file23
![Alt text](img/Screenshot_039.png)
## OUTPUT
sed -n -e '/tom/,/Joe/p' file23
![Alt text](img/Screenshot_039.png)
## OUTPUT
seq 10 
![Alt text](img/Screenshot_040.png)
## OUTPUT
seq 10 | sed -n '4,6p'
![Alt text](img/Screenshot_041.png)
## OUTPUT
seq 10 | sed -n '2,~4p'
![Alt text](img/Screenshot_042.png)
## OUTPUT
seq 3 | sed '2a hello'
![Alt text](img/Screenshot_043.png)
## OUTPUT
seq 2 | sed '2i hello'
![Alt text](img/Screenshot_044.png)
## OUTPUT
seq 10 | sed '2,9c hello'
![Alt text](img/Screenshot_045.png)
## OUTPUT
sed -n '2,4{s/^/$/;p}' file23
![Alt text](img/Screenshot_046.png)
## OUTPUT
sed -n '2,4{s/$/*/;p}' file23
![Alt text](img/Screenshot_047.png)
# Sorting File content
### Create the following file file21 file24 as follows:
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
cat > file24
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```

## OUTPUT
sort file21
![Alt text](img/Screenshot_048.png)
## OUTPUT
uniq file24
![Alt text](img/Screenshot_049.png)
# Using tr command
### Create the following file urllist.txt as follows:
cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```

 ## OUTPUT
cat file23 | tr [:lower:] [:upper:]
![Alt text](img/Screenshot_050.png)
 ## OUTPUT
cat urllist.txt | tr -d ' '
![Alt text](img/Screenshot_053.png)
![Alt text](img/Screenshot_054.png)
## OUTPUT
cat urllist.txt | tr -d ' ' | tr -s '.'
![Alt text](img/Screenshot_055.png)
# Backup commands
### commands
mkdir backupdir
mv backup.tar backupdir
cd backupdir

## OUTPUT
tar -cvf backup.tar *
![Alt text](img/Screenshot_056.png)

## OUTPUT
tar -tvf backup.tar
![Alt text](img/Screenshot_058.png)
## OUTPUT
tar -xvf backup.tar
![Alt text](img/Screenshot_059.png)

## OUTPUT
gzip backup.tar
ls .gz
![Alt text](img/Screenshot_060.png)
## OUTPUT
gunzi![Alt text](img/Screenshot_062.png)p backup.tar.gz

# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
## OUTPUT
chmod 755 my-script.sh
./my-script.sh
![Alt text](img/Screenshot_063.png)
# commands 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

## OUTPUT
cat herecheck.txt
![Alt text](img/Screenshot_065.png)
# commands 
cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
## OUTPUT
./scriptest.sh 1 2 3
![Alt text](img/Screenshot_068.png)
## OUTPUT
ls file1
![Alt text](img/Screenshot_069.png)
## OUTPUT 
echo $?
![Alt text](img/Screenshot_070.png)
# mis-using string comparisons

cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
## commands
chmod 755 strcomp.sh
./strcomp.sh 
## OUTPUT
![Alt text](img/Screenshot_076.png)
# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```

## OUTPUT
./psswdperm.sh
![Alt text](img/Screenshot_077.png)
# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 

```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

## OUTPUT
![Alt text](img/Screenshot_080.png)
./ifnested.sh 
# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```
cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```
## OUTPUT
$ chmod 755 iftest.sh
$ ./iftest.sh 
![Alt text](img/Screenshot_081.png)
# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

## OUTPUT
$ chmod 755 ifnested.sh
$ ./ifnested.sh 
![Alt text](img/Screenshot_085.png)
# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```
## OUTPUT
$ chmod 755 elifcheck.sh
$ ./elifcheck.sh 
![Alt text](img/Screenshot_086.png)
# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
## OUTPUT
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
![Alt text](img/Screenshot_087.png)
# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
 ## OUTPUT
$ chmod 755 casecheck.sh 
$ ./casecheck.sh
![Alt text](img/Screenshot_088.png)
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
## OUTPUT
$ chmod 755 whiletest.sh
$ ./whiletest.sh
![Alt text](img/Screenshot_090.png)
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
## OUTPUT
chmod 755 untiltest.sh
![Alt text](img/Screenshot_092.png)
cat > forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
## OUTPUT
chmod 755 forin1.sh
![Alt text](img/Screenshot_093.png)
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
## OUTPUT
chmod 755 forin2.sh
./forin2.sh 
![Alt text](img/Screenshot_095.png)
cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
## OUTPUT
./forin3.sh 
![Alt text](img/Screenshot_098.png)
cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
## OUTPUT
chmod 755 forin1.sh
![Alt text](img/Screenshot_101.png)
cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh
$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

## OUTPUT
![Alt text](img/Screenshot_101.png)
cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
```
## OUTPUT
chmod 755 forctype.sh
./forctype.sh 
![Alt text](img/Screenshot_103.png)

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
## OUTPUT
chmod 755 forctype.sh
./forctype1.sh 
![Alt text](img/Screenshot_105.png)

cat fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```

 ## OUTPUT
$ chmod 755 fornested1.sh
$ ./fornested1.sh 
![Alt text](img/Screenshot_108.png)

cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
## OUTPUT
$ chmod 755 forbreak.sh
$ ./forbreak.sh 

![Alt text](img/Screenshot_110.png)
cat forcontinue.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
## OUTPUT
chmod 755 forcontinue.sh
./forcontinue.sh 
![Alt text](img/Screenshot_111.png)
cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
## OUTPUT
$ chmod 755 exread.sh 
$ ./exread.sh 
![Alt text](img/Screenshot_112.png)

 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
## OUTPUT
chmod 755 exread1.sh 
./exread1.sh 

![Alt text](img/Screenshot_113.png)
cat funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT
./funcex.sh 
./funcex.sh 1 2
![Alt text](img/Screenshot_114.png)

cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
## OUTPUT
chmod 777 argshift.sh
./argshift.sh 1 2 3
![Alt text](img/Screenshot_117.png)

 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
## OUTPUT
chmod 777 argshift.sh
./argshift.sh 1 2 3
![Alt text](img/Screenshot_117.png)

cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
 ./argshift.sh 1 2 3
![Alt text](img/Screenshot_117.png)

cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```

## OUTPUT 
awk -f nc.awk data.dat

![Alt text](img/Screenshot_118.png)
![Alt text](img/Screenshot_119.png)
cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 
![Alt text](img/Screenshot_120.png)
![Alt text](img/Screenshot_121.png)

# RESULT:
The Commands are executed successfully.
