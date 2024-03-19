You want git to ignore certain files/folders even so you put them into .ignore and then git add . will ignore them, right? Wrong! git add . will add ALL files to the staging area. git commit is the command that will pass over files/folders listed in .gitignore so that these do NOT go to your public repo on github. So, what happens if you do this? Well, I did it with a mailchimp API and fortunately they check and disabled the api key and have an option on their site to create a new key. If you do push a file to Github that you dont want there then you can delete the file or the entire repo if its just for testing and doesnt really matter.

Be careful with the format of the .gitignore file. While # can be used as a comment if used after a file name on a line it can be interpreted as something else. So its a good idea to format the file like this ..

#JS node_mdules

node modules

# confidential files

.env

config.json

#ignore these files

scraps.js

AFTER you do **git add .** and BEFORE you do **git commit** check **git status** and **git status --ignored** it will show you the files that are staged ignored and you can make sure that you want to commit those files. You can roll back before the commit by doing **git rm --cached -r .**

if you do git commit without adding the -m "reason for version" it will bring up a VIM text editor. You can add a comment there and type **:q!** and press enter to quit and save. It is easier, I think, to git commit -m "Changed fileX".
