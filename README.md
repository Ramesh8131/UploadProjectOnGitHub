# How to Upload Project On GitHub Website

This is not complex to upload project on github and how to show commit of project.

# % Follow Steps for Upload project on gitHub %

Step-1 
:- Login your's GitHub Account.
<br />
Step-2
:- Create new repository (or for more help show image pic1.png and pic2.png)
<br />
Step-3
:-Open Command Prompt
<br />
Step-4
:- Go to Current working directory where your project
(Ex--Like Project Name "Java" then run cmd "cd Java")
<br />
Step-5
:- git init
<br />
Step-6
:- git add .
<br />
Step-7
:- git commit -m "Add all my files"
<br />
Step-8
:-git remote add origin https://github.com/yourusername/your-repo-name.git   
# if not working
for more help show image pic3.png and from here copy cmd and run on your Command Prompt
<br />
Step-9

:-git push -u origin master 
# if not working
then show image  pic4.png and from here copy cmd and run on your Command Prompt
<br />
Step-10 
# Show commit of your project
:- git log 
<br />
# Ex---
 pc@linux:~/Downloads/GIT/UploadProject$ git log
 <br />
 commit l8ab9f78534a5g8de5d90ac15cdf796afd770e8e (HEAD -> master, origin/master)
 Author: Your Name <you@example.com>
 Date:   Thu Aug 29 10:07:30 2019 +0530

   add all my files
# this is Your Commit:--l8ab9f78534a5g8de5d90ac15cdf796afd770e8e
