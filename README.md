# emasomocred (Codes [below](https://github.com/SimonDouglas-bit/emasomocred/files/9616385/emasomocred.zip))
##### Dated: April 17<sup>th</sup> 2021
A hacky script that using a specified convention, generates login credentials for the [e-Masomo](https://emasomo.cuk.ac.ke) platform (a moodle used for learning management). [Emasomo](https://emasomo.cuk.ac.ke) moodle is being used by [The Cooperative University of Kenya (CUK) ](https://cuk.ac.ke) for learning and administering assignments.
## Running the code

###### This code should be run in python3 or higher environment.

You may need to change the permission mode before running
e.g in linux:
	
    sudo chmod 777 emasomocred.py
    
   
Note that you may be required to install any other needed modules if they are missing

1. You can run from the terminal by typing:
	
    ./emasomocred.py
    
    or
    
    python3.9 emasomocred.py

2. You can run it using IDLE or any other relevant software in any platform

## Confidentiality
In no event shall I be liable to anyone for special, incidental,
collateral or consequential damages arising out of the use of
this information.

## Disclaimer
The information presented in here is provided as is. The
findings assessments are a “point in time” analysis and as such
it is possible that something in the environment could have
changed since the tests reflected in this report were run. Also,
it is possible that new findings may have been discovered since
the tests were run.

## Executive Summary
Emasomo is playing a big role in data and information sharing
especially at this time of speaking (Covid19 Era). Among others, it is a medium
for assignments and cats completion. Every CUK student has an emasomo
account of which he or she has a unique username and a password
for. There would not be a need of login credentials if emasomo is
not implementing confidentiality.
What if people have each others credentials and anyone can be
anybody else? This will not be privacy.
Therefore here in this context am discussing my findings on
disclosing the login credentials for emasomo.

## Breakdown
Among the latest upgrades to the CUK emasomo website
was generation of new usernames and passwords. Each credential
was emailed to its respective student email account.
From the email it was deterministic that this credentials were
computer-generated because it is quite a huge task to be done
manually. 
If it is a computer that generates the credentials then it must
be following a certain pattern under circumstances in which it is
programmed.
Below were my personal computer-generated credentials:

	username: simondou
	password: SimonDou@2022

My full name as it appear in emasomo is **Simon Douglas**.
## Findings
### The username
As from the above credentials, it can be deduced that the username is
formed from the full name.
Here are the rules that username follows:
1. comprise of concatenation of the first name followed by the
first three characters of the second name,
2. all characters are in lower case and
3. no separators in concatenation
### The password
The password is also generated from the full name but with a
slight modification as compared to the user name. The following
are the rules that password follows:
1. the first letter of the first name and the first letter of the second name must be uppercase,
2. all other characters are lowercase,
3. comprise of concatenation of the first name, followed by the first three characters of the second name and lastly @2022 string and
4. no separators in concatenation.

## Other information
With the above knowledge one needs to know the first name and the second name and then calculates the correct username and
password.
Again getting the correct full name of any student is easier than one could think of searching from a big database
### Getting any student full name
Provided that one have logged in successfully to emasomo account, one can see who is the next person, who is the previous person and
so on down the stream. First you need to get the profile link which can be found by clicking on the profile at the navigation menu.
The profile link will then display in the search bar in clear
text format.
At the end of this link, there is a parameter id that seems to
hold integers.
By adding 1 to the id value assigned to your (logged in) profile and refreshing the page displays the next person’s profile under your profile. By
subtracting a 1 will do the reverse and just a guess to any appropriate number displays the respective person’s profile.
In addition to the above, these scenario also works for the id parameter value in the course link where, by changing this value
will open up another course.

## The code
Since this works, a script can be developed to automate the task.
Using python3.9, I developed a script and named it emasomocred.py, link given below.
This script prompts for the input of the first name, second name and even the third name (if a student have the third name).
It then generates the possible username and password and prints it out. To make the script somewhat productive, I have extended it to save all possible combinations of usernames and passwords from the first name, second name and the third name if it exists. This combinations are saved in a text file named possibles.txt that will automatically be generated when emasomocred.py script is run.
This combinations stored in possibles.txt might result to discovering the credentials of other students out of scope. This script does not stop there but goes on to ask for the user feedback.
If am the user running the script and accepts to send the feedback, it will prompt for my email information and then tries
to send an email with a possibles.txt file attachment to another
email from my email. Therefore a huge dictionary can be created from the information gained by this script that will have several right credentials.
## Conclusion
If confidentiality really matters to information delivered through emasomo then such script may be used to break it.

## emasomocred.py
[emasomocred.zip](https://github.com/SimonDouglas-bit/emasomocred/files/9616385/emasomocred.zip)

