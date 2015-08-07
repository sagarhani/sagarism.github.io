---
layout: post
title:  Mid-night git session at dgplug
summary: Learning git by solving a prog
permalink: as per akshay's suggestion :P
---


I’m using git since few months. The world of git is too big. You have lot of things to explore in that.

One way to explore things in any technology or programming language is by solving the problems.

On [#dgplug][dgplug] (Durgapur Linux Users’ Group) channel, someone had a problem with git.

The problem statement goes like this :

A person has made 4 commits and sent a pull request. Now, the owner of the GitHub repository is asking that person to remove the last 2 commits i.e commit number – 3 and commit number – 4. How can one remove the last 2 commits keeping first 2 commits as it is ?

[Sayan][sayan] was there to help in this problem. He took a hands-on session at that late night (It was around 11.45 p.m IST).

If you want to learn to solve this problem, just follow these instructions :

First we cloned this repository :

```$ git clone https://github.com/kushaldas/pym/```

As usual, you need to change your current directory to project directory, so hit :

```$ cd pym```

Now you are inside the project directory. We moved into code directory of the project. To do this, hit :

```$ cd code```

We added a new file called helloworld.py

After this, check the status of the git by executing :

```$ git status```

You will be able to see ```helloworld.py``` file name in red color under Untracked files. This tells that the file has not been tracked by the git.
Please remember this point as this is important.

Next do :

```$ git diff```

This will not show any changes as of now.

Now add this statement in argvtest.py  file :

```print 'hello world'```

Note : argvtest.py file is already present in the code directory

Now again, check the status of the git by executing :

```$ git status```

Can you see the changes now ?

We can see argvtest.py file in red color under modified files and hellowold.py file in red color under Untracked files.

Now do :

```$ git diff```

You can see the changes you have made. If you have added a new line you will be able see it in green color preceding with ```+``` (plus) symbol. If you have deleted a line you will be able see it in red color preceding with ```–``` (minus) symbol.

I hope you have completely understood till here. :)

Now do :

```$ git add argvtest.py```

The argvtest.py file is now staged. To check this, do :

```$ git status```

You can see the color of the modified file i.e argvtest.py has been changed from red to green. This represent that the file has been staged and tracked by git.

Now do :

```$ git diff```

You don’t see nothing, because by default git diff shows whatever is there in modified.

Since we have nothing in modified area, it doesn’t show anything.

argvtest.py file is now staged and if you want to see the changes, do :

$``` git diff --staged```

This will show the changes in the staged area.

Note : ```$ git diff --staged``` and ```$ git diff --cached``` does same thing.

Now let’s commit this by doing :

```$ git commit```

This will open a text editor and you will see the text in there “Changes to be committed”.

Now write the commit message in the first line, then save and quit. (Lines starting with # will be ignored)

To see your commit, do :

```$ git log```

To see the changes made in the commit, do :

```$ git log -p```

There will be lot of commits, now do :

```$ git reset --soft HEAD~1```

```$ git status```

See the output. Understood what ```$ git reset --soft HEAD~1``` did ?

Soft reset brings the changes to staged.

Now,

```$ git reset HEAD argvtest.py```

will bring into unstaged area as you can see in the output, it shows the file name under Unstaged changes.

HEAD is referred as the topmost commit in git just like tip is referred as the topmost commit in mercurial.

HEAD~1 takes 1 commit behind.
HEAD~2 takes 2 commit behind and so on…

Important note : If we do ```$ git reset --soft HEAD``` then we won’t loose the changes made in other commits which were removed.

I hope after reading this post you would have understood how to solve the above mentioned problem. :)

[dgplug]: http://dgplug.org
[sayan]: sayanchowdhury.dgplug.org