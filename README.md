# chefWork

This is the setup for chef server, chef workstation and in future chef node.
Use the existing Vagrantfile which will setup a chef server on your machine using Virtual box.
Make a note of the organisation which is being created in the file and note the admin.pem file which is being created.
There is also a admin user created for the organisation.

Setting up chef workstation:
----------------------------------------------------------
After you have configured chef server, now go to workstation and do the following:
Install chefDk as per your system.
Create a chef-repo in your machine.
Create .chef directory in it and create a file knife.rb in it.
Make a knife.rb with the settings as in repository.
Copy the admin.pem file from chef server using scp command.
Initialize the git repo in the folder.
Add .chef to gitignore using echo ".chef" >> .gitignore
Commit all the changes.
------------------------------------------------------------

Issues faced while the setup:
------------------------------------------------------------
By default powershell was adding few unknown characters to .gitignore.
To make it work first remove all the git cache and re add everything.
You can also edit your repo on github and make a pull to remove unnecassry characters from the file.

Commit all pending changes, then run this command:
git rm -r --cached .
git add .
git commit -m ".gitignore is now working"

Extremely important and common mistake that is made:

The name must begin with a lower-case letter or digit, may only contain lower-case letters, digits, hyphens, and underscores, and must be between 1 and 255 characters. For example: chef.
So if you accidently give a upper case do following:

In order to keep the settings perisiting do chef-server-ctl reconfigure. This will remove chef from the host machine.
Now reinstall it with correct company name.

- What happens on workstation if organisation is not set:
You will get 404 Object does not exists if the organisation name is incorrect in knife.rb file. Once you have reinstalled using above steps. 

Run knife ssl check && knife client list to see if you orgname-validator.pem is listed back and not 404.
-------------------------------------------------------------------------------------------------------------