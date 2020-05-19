# Git Terminal Basic Commands
- [Download Git](https://git-scm.com/download/win)
- Ckeck all ckeckbox and click on Next...
- After installing git in your system. Follow these seteps.

**Step 1:**  Create a Folder anywhere in your PC. 

**Step 2:**  Onen thet Folder and right click in it.

**Step 3:**  You will get an option ```Git Bash here```. Click on it. You will see a commandline prompt.

Now follow the below commands:

```
$ git config --global user.name "Your Name"
$ git config --global user.email "Your_email@Example.com"
$ git status
```
The above command will show you the status of your repository like 
```
Output:
fatal: not a git repository (or any of the parent directories): .git
```
It means your directory is not a git repository.

To make a directory as a git repository run ```git init``` command.
```
Output:
Initialized empty Git repository in D:/Git BAsic/.git/
```
After this run ```git ststus``` commnad.
```
Output:
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```
It means either your directory is empty or you have already commited the untracket or staged file/folder.

#### Assuming that you have created some file and folder related to your project and now you want to push it in a repository.
Run ``` git status ``` again. You will get:
```
Output:
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
         <file>
         <file>
nothing added to commit but untracked files present (use "git add" to track)
```

<file> will be in red color i.e it's untracked or modified
  
  
Below command will stage all the files and  Folder
```
$ git add .
or
$ git add -A
```

Now check the status ```git status``` The new file: <file> will be shown in green color i.e the files are staged.
  
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   <file>
        new file:   <file>
```
  
Now Commit the files
```
$ git commit -m "Initial Commit"
```
You can use any appropriate message at the place of "Initial Commit" while commiting. This message will give you the knowledge about the changes in your projects like "Bug fix", "Structure Modified" etc. 

## Create a New Repository
Login to GitHub and click on the ``` + ``` on the top right of browser. select New Repository.

![New Repository](https://help.github.com/assets/images/help/repository/repo-create.png)

Enter Repositroy Name

![Repo Name](https://help.github.com/assets/images/help/repository/create-repository-owner.png)

Select Public or Private as per your requirement. 

If you wanna initialize this repository with a README then click on checkbox else skip it and click on ``` Create Repository ```
Assume that your repository name is **planets** and username is **mkuzak**

![Repository](https://swcarpentry.github.io/git-novice/fig/github-create-repo-03.png)

Congo! you have successfully created a new repository named planets.

# Make a connection between local repository to GitHub repository 
Use below command with your own username.
```
$ git remote add origin https://github.com/usename/planets.git
```

Before pushing the repository you need to add a ```SSH key``` to your account.

# Add SSH key to your account
### You don't have need to add the SSH key again and again if you are using same email and same system. Just add it once for authentication.

Paste the text below, substituting in your GitHub Enterprise email address.
```
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.
```
Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):[Press enter]
Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]
Enter passphrase (empty for no passphrase): [Type a passphrase]> 
Enter same passphrase again: [Type passphrase again]
```
![New SSH Key](https://github-images.s3.amazonaws.com/enterprise/2.15/assets/images/help/settings/userbar-account-settings.png)

![Select SSH and GPG key](https://github-images.s3.amazonaws.com/enterprise/2.15/assets/images/help/settings/settings-sidebar-ssh-keys.png)

![Add SSH key](https://github-images.s3.amazonaws.com/enterprise/2.15/assets/images/help/settings/ssh-add-ssh-key.png)

In the "Title" field, add a descriptive label for the new key. For example, if you're using a presonal computer, you might call this key "My PC".

Find **Your Public key has been saved in ** ```/c/Users/your_username/.ssh/id_rsa.pub```

copy the Publick Key path and use the command below
```
tail /c/Users/your_username/.ssh/id_rsa.pub
```
You will get some text begins with 'ssh-rsa', 'ssh-dss', 'ssh-ed25519', 'ecdsa-sha2-nistp256', 'ecdsa-sha2-nistp384', or 'ecdsa-sha2-nistp521'

Copy it and Paste your key into the "Key" field. Click on Add SSH key.

![Paste Key](https://github-images.s3.amazonaws.com/enterprise/2.15/assets/images/help/settings/ssh-key-paste.png)

or try below command.
```
$ clip < ~/.ssh/id_rsa.pub
# Copies the contents of the id_rsa.pub file to your clipboard
```
If ``` clip ``` isn't working, you can locate the hidden ```.ssh``` folder, open the file in your favorite text editor, and copy it to your clipboard.


Now you are ready to push your repository to GitHub. Once you type the below command and press enter, your repository will pushed on GitHub in a while depending on the size of files.
```
git push origin master
```
If you want to see the log of your repository use ```git log ``` command.

To get the your name used to config the repository, use command ```git config user.name```
To get your email useed to config the repository, use command ```git config user.email```

> ## For more details [click here](https://git-scm.com/docs/gittutorial)

> ## To get more knowledge on README.md formating [click here](https://guides.github.com/features/mastering-markdown/). 

> ## You may visit this site to get more on Markdown [click here](https://medium.com/swlh/how-to-make-the-perfect-readme-md-on-github-92ed5771c061)
