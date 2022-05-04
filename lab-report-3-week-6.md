# Week 6 Lab Report

## Streamlining ssh configuration
The first trick I learned was to adjust the configuration of the remote login, such
that I could login without typing a long remote address.


![pic_1](Images/report3/pic_1.png)
First, I used VSCode to access the config file in my `.ssh` folder.  I configured it
by adding the lines below:
```
Host brzhu
    HostName ieng6.ucsd.edu
    User cs15lsp22auc 
    IdentityFile ~/.ssh/id_rsa
```
Note that the name to the right of `Host` can be customized; this will be used to login through
the terminal.

After configuring the config file, I could simply use `ssh brzhu` to login to the remote server.
![pic_2](Images/report3/pic_2.png)

As you can see, it is no longer necessary to type an entire remote address.  To test the functionality,
I created a new file `scp_file.txt` and copied it over using the new username.
![pic_3](Images/report3/pic_3.png)

It is seen that the new file can indeed be found on the remote server, indicating that the new functionality
works.

## Setup Github Access from ieng6
---

[Return To Home](https://zhuzilibryan.github.io/cse15l-lab-reports/)