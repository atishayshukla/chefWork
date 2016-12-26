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
