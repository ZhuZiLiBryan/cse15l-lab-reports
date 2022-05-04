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

The second trick I learned was to setup access to GitHub through my remote computer on ieng6.

To accomplish this, I used the `ssh-keygen` command to create a private key and public key.  The public key can be found both on GitHub and on my user account.
![pic_4](Images/report3/pic_4.png)
The public key is accessible through the SSH and GPG keys tab in my GitHub settings.  Shown above are keys for my local computer and my ieng6 remote computer.
![pic_5](Images/report3/pic_5.png)
As shown above, a local copy of the SSH key is also in my `.ssh` directory.  It is the file denoted `id_ed25519.pub`.  Also note that the private key can be found in this same directory, which is `id_ed25519`.  This is not copied anywhere else, and is only accessible on my local account.

After generating these keys and adding them to GitHub, I was able to run `git push origin main` on my ieng6 computer.  Below, I created a file called `push_test.txt`, which I added to the staging area, committed it, and used `git push origin main`.  It was succesfully pushed to the main branch.

![pic_6](Images/report3/pic_6.png)

A link to the commit itself is found here: [Link to Commit](https://github.com/ZhuZiLiBryan/skilldemoone/commit/cc77fe183d3085d09809e12fe79babb294e56d2e)

## Copy Whole Directories with `scp -r`

---

[Return To Home](https://zhuzilibryan.github.io/cse15l-lab-reports/)