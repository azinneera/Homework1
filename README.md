# Homework1
OverTheWire: Wargames - Bandit


Hints and commands given in the [OverTheWire website][1] was used as a guide to find the password fro the next level.

The screenshots illustrate the commands used to discover the password.


  [1]: http://overthewire.org/wargames/bandit/

## bandit0 

**Level Goal**

Connect to the OverTheWire game server using SSH using provided credentials and discover password for Level 1.
hostname: bandit.labs.overthewire.org
username: bandit0
password: bandit0

**How To**

Use an SSH application and SSH to bandit0@bandit.labs.overthewire.org. Given that the file is in the home directory, use ***ls*** command to list the content of the directory.Notice the file named ***readme***, and simply read this filename to find the password for the next level using the command  ***cat readme***.

Terminate the SSH session by typing ***exit*** and reconnect to the bandit game using thenew username and password for level 1.

**Learning/Conclusion**

Possibilities are there to receive a few prompts regarding RSA keys, or a warning that someone may be eavesdropping on you. Research and remove keys belonging to the hostname to overcome this issue. Also it covered a few basic commands.

![bandit0](https://cloud.githubusercontent.com/assets/18344003/14392700/65dc9206-fde0-11e5-8bc6-76b46f53f920.jpg)

## bandit1

**Level Goal**

Discover password for the next level stored in a file called - located in the home directory.

**How To**

Login as *bandit1* using the password recovered from level0 and land in the home directory. Given that the file is in the home directory named -, the command ***cat ./-*** produces the intended result. The period denotes the current working directory which in this case can be substituted with /home/bandit1.

Terminate the SSH session and login to next level.

**Learning/Conclusion**

The file cannot be simply read using the command ***cat -*** since ***-*** in bash is used to redirect to/from stdin or stdout, meaning that whatever is typed after the command will be read standard in and will be repeated standard out. Further researching in Bash/Linux special characters would reveal more.

![bandit1](https://cloud.githubusercontent.com/assets/18344003/14392701/65de29d6-fde0-11e5-90ba-23cd8dfd37a8.jpg)

## bandit2

**Level Goal**

Discover password for the next level stored in a file called "spaces in this filename" located in the home directory.

**How To**

Given that the file is in the home directory named again the command cat should produce results. The file can is read using the command ***cat spaces\ in\ this\ filename*** in which the backslash preserves the space following it or simply type ***cat sp*** and hit *Tab* for the shell to fill the rest.

Terminate the SSH session and login to next level.

**Learning/Conclusion**

When using the cat command to read the file, space character cannot be typed directly since linux uses it to separate items. From the file "spaces in this filename" only the first word, that is "spaces" will be taken as the filename. A preceding backslash is used before the space character to recognize it and read it as it is.

Escape characters are powerful when programming and helpful when dealing with weird filenames. Additionally tab completion is extremely powerful which would reduce errors made in spelling filenames and can really be efficient for traversing through file structures.

![bandit2](https://cloud.githubusercontent.com/assets/18344003/14392702/65e0927a-fde0-11e5-943f-253d687ab915.jpg)

## bandit3

**Level Goal**

Discover password for the next level stored in a hidden file in a directory named "inhere".

**How To**

Try to list all what inhere directory holds with the ***ls*** command and it would show it as blank. Go through the manual of for ls command by typing in ***man ls*** and notice the argument ***-a*** used to list all items. Press q and exit. Then use the command with the argument to list literally all items. 
This should show three things listed. A period, two periods and .hidden. The period denotes the current directory, two periods references the parent directory and .hidden is the hidden file containing the password for the next level.

Read the file using ***cat /inhere/.hidden*** from the home directory to recover the password.

Terminate the SSH session and login to next level.

**Learning/Conclusion**

A hidden file can be created by adding a period in at the beginning of the filename which will not be visible to a simple ***ls*** command.
ls command can be used with several arguments to get more information about the items in a directory. The manual can and should be used in order to get a detailed description about commands and their usage.

![bandit3](https://cloud.githubusercontent.com/assets/18344003/14392703/65e3517c-fde0-11e5-9eb9-6ef5abb020aa.jpg)

## bandit4

**Level Goal**

Discover password for the next level stored in the only human-readable file in the directory named "inhere".

**How To**

List all the items in the folder and notice the file names beginning with a dash meaning that we should adjust the command. Given that there is only one human-readable file in the directory, using wildcard type in the command ***file ./**** to identify the file with ASCII characters. This should show the only human-readable file as -file07.

Read the password, terminate the SSH session and login to next level.

**Learning/Conclusion**

A human readable means a human can read it without the need of computer translation. Therefore, human readable content will be in ASCII or similar while non-human readable data will be in binary. To explore the type of data file command can be used with arguments. 

Moreover usage of a wildcard often represented by the ‘*’, commonly referred to as ‘splat’ with commands the shell will match any character to any length. Different wildcards are used for different purposes which greatly increases the flexibility and efficiency of searches.

![bandit4](https://cloud.githubusercontent.com/assets/18344003/14378261/a6e0f08e-fd91-11e5-801c-037d08e7f093.jpg)

bandit5

![bandit5](https://cloud.githubusercontent.com/assets/18344003/14378260/a6df54ea-fd91-11e5-858b-ccbd50f19b8d.jpg)

bandit6

![bandit6](https://cloud.githubusercontent.com/assets/18344003/14378263/a6f83834-fd91-11e5-93c5-673c7815bb36.jpg)

bandit7

![bandit7](https://cloud.githubusercontent.com/assets/18344003/14378264/a6f8f3a0-fd91-11e5-9e43-73a3a2247c4b.jpg)

bandit8

![bandit8](https://cloud.githubusercontent.com/assets/18344003/14378265/a6fcd22c-fd91-11e5-85e0-f0aec7881444.jpg)

bandit9

![bandit9](https://cloud.githubusercontent.com/assets/18344003/14378266/a70e37a6-fd91-11e5-9c5f-e2d502acdf6a.jpg)

bandit10

![bandit10](https://cloud.githubusercontent.com/assets/18344003/14378268/a70fae4c-fd91-11e5-9bac-6d00d6049ce8.jpg)

bandit11

![bandit11](https://cloud.githubusercontent.com/assets/18344003/14378267/a70f5fe6-fd91-11e5-99e8-6896a183dd51.jpg)

bandit12

![bandit12](https://cloud.githubusercontent.com/assets/18344003/14378269/a71e3868-fd91-11e5-8583-8848dec4fe38.jpg)

bandit13

![bandit13-1](https://cloud.githubusercontent.com/assets/18344003/14378270/a725725e-fd91-11e5-9a8a-99414212469f.jpg)

![bandit13-2](https://cloud.githubusercontent.com/assets/18344003/14378271/a726ad22-fd91-11e5-9203-a2524b6a64ec.jpg)

bandit14

![bandit14](https://cloud.githubusercontent.com/assets/18344003/14378272/a73c3458-fd91-11e5-9cac-486b559dfeeb.jpg)

bandit15

![bandit15](https://cloud.githubusercontent.com/assets/18344003/14378274/a740129e-fd91-11e5-83fa-84b3ec1e91c8.jpg)

bandit16

![bandit16](https://cloud.githubusercontent.com/assets/18344003/14378273/a73d9a28-fd91-11e5-8795-081c90da44f1.jpg)

bandit17

![bandit17](https://cloud.githubusercontent.com/assets/18344003/14378275/a744113c-fd91-11e5-8ea6-57a540157bed.jpg)

bandit18

![bandit18](https://cloud.githubusercontent.com/assets/18344003/14378276/a74ad116-fd91-11e5-8439-b36b9920bdd4.jpg)

bandit19

![bandit19](https://cloud.githubusercontent.com/assets/18344003/14378277/a74bc472-fd91-11e5-9198-d9244005c937.jpg)

bandit20

![bandit20](https://cloud.githubusercontent.com/assets/18344003/14378280/a76e4e0c-fd91-11e5-8196-6cb516d935a8.jpg)

bandit21

![bandit21](https://cloud.githubusercontent.com/assets/18344003/14378279/a76d03f8-fd91-11e5-9564-06c0dc70197d.jpg)

bandit22

![bandit22](https://cloud.githubusercontent.com/assets/18344003/14378278/a76a8a6a-fd91-11e5-8fab-04a5dd2bd6b1.jpg)

bandit23

![bandit23](https://cloud.githubusercontent.com/assets/18344003/14378281/a7752fd8-fd91-11e5-9a7d-0e479e980f45.jpg)
