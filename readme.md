# Git and github

Git/Github tutorials can make it seem like rocket surgery. It doesn't have to be this way. It's much easier to get started if you focus on the three or four commands you typically use when working on a personal project. Below I describe how to do this. It is a kind of minimal kernel to get your repository set up locally and at github. The following assumes you have some project in a directory you want to share publicly on github.

# Set up your Git/Github accounts
### Set up Git on your local machine :rocket:
a. Download and install Git (http://git-scm.com/downloads) and set it up so you can execute git commands from the terminal (Gitbash on Windows). This guide seems pretty good: https://www.atlassian.com/git/tutorials/install-git

b. From the terminal, configure your username and email:

    git config --global user.name <your user name>
    git config --global user.email <your email address>

### Sign up your Github account
Sign up at https://github.com. For now, I recommend registering using the email you used in your Git configuration above, just to make everything simpler and easy to remember.

# Turn your project into a repository
First, initialize your repository:
1. In your project folder, make a `.gitignore` file that has the names of things you don't want to be version controlled (e.g., docx files, executables, pycache folders, and anything else you want hidden). You can include the wildcard character (\*). For Python programmers, there is a [standard Python `.gitignore` file at github](https://github.com/github/gitignore/blob/main/Python.gitignore) that is a good starting point.
2. cd to your project folder, and enter `git init`.  You now have a local github repository! You pretty much are done, frankly. You can start to enter commands.
3. `git status` to see what's up.
4. `git add .` to add everything to staging area.
5. `git commit -m "my first commit!"` to commit to repository

Now work on your project locally. When you have something cool, then commit it with the `add` and `commit` commands from lines 4 and 5.  You are using git. Use `git status` to see what's going on in your repository. That's pretty much all I ever do locally. Use informative, short commit statements. I would recommend making a `readme.md` file and putting it in your project folder, as it will show up automatically nicely formatted at Github when you push (VS Code is a decent editor that lets you preview Markdown).

If you want to just add one or a few files to the staging area, just put their names instead of the period:

    git add file1 file2 file3

This can be useful if you have one file that you have worked on a lot, and another that is half done and not ready to stage yet. Also, if you want to stage a bunch of files that are thematically related and commit them together, with logically individuated comments, then it is useful to do this.

Note if you make a mistake and want to *remove* a file from the staging area (say `file3`), then:

    git reset HEAD -- file3

will pull it from the staging area back into the working directory.

# Set up a remote repository and push your project to github
1. At github, point and click to create repository with project name that you want (e.g., foo). The url of the repository will be provided to you (e.g., `https://github.com/yourname/foo.git`).
2. Connect your local repository to the remote one using that url you just got. At your terminal:

    `git remote add origin https://github.com/yourname/foo.git`
3. Push your local repository to github:

     `git push origin main`    
It will ask you for your remote username and pw.

Now, whenever you have finished working on your local machine and are ready for your results to show up at github, just enter that same command from step 3 and your work will be pushed to github!

# Use it for a while
There, you've done it. Go check out your repository at github. Share it. Write that code! Frankly, the above is 99% of what I do with my little one-person projects. When it comes to working with larger projects, then things will get a little more complicated: you will need to learn about things like forks, branches, and pull requests. But for now, I would just focus on the above until you need to branch out.

Note if you need to clone a repository, just go to it at github, click on the green 'clone or download' icon, copy the url, and in a directory you have set up to contain the repo's folder, and type in `git clone <url>` where the url is the one you just copied. Now you have a local version of the repo.

# Good resources :question:
Once you have messed around for a bit with the above, or need to expand into [pull requests](https://www.freecodecamp.org/news/how-to-make-your-first-pull-request-on-github-3/) and such, the following are great resources to get started:    

- https://rogerdudler.github.io/git-guide/    
- https://realpython.com/python-git-github-intro/
- https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners

Then there is the online book put out by Git, which is great if you want the authoritative source with more details than the above links: https://git-scm.com/book/en/v2.    
