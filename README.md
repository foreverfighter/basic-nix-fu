# basic-nix-fu

Basic nix-fu commands


## To delete all .pyc cache files within a directory and subdirectories

find . -name "*.pyc" -exec rm -f {} \;

## To count the number of files in a directory

ls -1 | wc -l

```
pwd
echo $SHELL
cat foo.txt
cat > foo.txt
cat ls > foo.txt
ls
ls -a
ls ..
cd
mkdir my_dir
mkdir {1..9}
rmdir \*
cp a_file a_dir
cp -r a_dir a_dir
mv anything a_dir
mv a_file renamed_file
rm \*.txt
rm a_file
rm -rf a_dir
ls | head -3
head a_file
tail a_file
nl a_file
sort a_file
wc a_file
cut -f 1,2 -d ' ' mysampledata.txt
sed 's/oranges/bananas/g' mysampledata.txt
top
grep '^no\(fork\|group\)' /etc/group
grep -E '^no(fork|group)' /etc/group
chmod 755 a_script.
date
date +%F
find . -name "*.py" | xargs -L 1 cat >> input.txt (find all the .py files from
here and subdirectories and combine them into input.txt)

#!/bin/bash
# Backs up a single project directory
# Ryan 25/7/2018

if [ $# != 1 ]
then
    echo Usage: A single argument which is the directory to backup
    exit
fi
if [ ! -d ~/projects/$1 ]
then
    echo 'The given directory does not seem to exist (possible typo?)'
    exit
fi
date=`date +%F`

# Do we already have a backup folder for todays date?
if [ -d ~/projectbackups/$1_$date ]
then
    echo 'This project has already been backed up today, overwrite?'
    read answer
    if [ $answer != 'y' ]
    then
        exit
    fi
else
    mkdir ~/projectbackups/$1_$date
fi
cp -R ~/projects/$1 ~/projectbackups/$1_$date
echo Backup of $1 completed
```
