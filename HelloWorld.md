## This is a markdown file..

If RStudio prompts you for a username and password every time you try to push your project to Github, open the shell (Git menu: More/Shel…) and do the following:

1) Set username and email (if you did not do that before)
git config --global user.name "your_username"
git config --global user.email "your_email@example.com"

2) Create SSH key
ssh-keygen -t rsa -C "your_email@example.com" 
In RStudio, go to menu Tools / Global options / Git SVN / View public key and copy the key to your Github account setting (Edit profile / SSH keys / Add SSH key).

To check that ssh-authentication works, try to run
ssh -T git@github.com

and you should get something like

Hi your_username! You’ve successfully authenticated, but GitHub does not provide shell access. 

3) Change remote.origin.url from HTTPS to HTTP 

It might be Windows specific, but after 1)+2) RStudio still asks me for user name and password. After a long Google search, I have found a solution here and that is
git config remote.origin.url git@github.com:your_username/your_project.git

Hip, Hip, Hurrah!

