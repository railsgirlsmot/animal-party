# Animal Party


### The Challenge
Make a pull request to add to this collaborative tale about an EXCITING ANIMAL PARTY.

You will:

* Edit the files in this project
* Add those changes to your staging area
* Commit them
* And push them to github
* You'll then (if you're really brave) learn how to manage merge conflicts!

####  **Here's how ...**

1. ###### Open your terminal and navigate to where you're going to store these files on your computer.
  *(just shout out if you don't know who or what your terminal is!)*


2. ###### Clone this repository


  ```sh
  $ git clone https://github.com/railsgirlswgtn/fan-fiction-github-challenge.git
  ```

  This creates a copy of this **repository** on your computer. In other words, it creates a new folder called `fan-fiction-github-challenge` full of everything you see here.


3. ###### Navigate into the folder

  ```sh
  $ cd fan-fiction-github-challenge
  ```

  `cd` is short for **change directory**. This is how you navigate through your file system using the terminal.

  You can go back to the directory you were in before by typing `cd -` or the directory that contains the one you are in by typing `cd ..`.

  If you want to see what directory you're in, you can type `pwd`, which is short for **print working directory**. To see what is in the directory you're in, type `ls`, which is sort of a weird abbreviation for **list** I guess.


4. ###### Checkout a branch


  ```sh
  $ git checkout -b your_name
  ```

  This creates a new **branch**. That means it keeps track of changes separately.

  You don't need to surround the name of your branch with brackets or anything like that, but generally it should just be made up of letters, numbers, `-`s and `_`s. So you could write `git checkout -b terrible_dragons` or `git checkout -b revenge-of-albus-severus`.

  You need the `-b` to create the new branch. Without `-b` it will want to change to a branch that already exists with that name. That can be useful later.


5. ###### Make an edit


  Open the file fan-fiction.md in your text editor. This file is in **markdown**. Check out [this guide](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) to formatting in markdown. You can embed images, links, lists, headings, whatever you like!


6. ###### Add your changed file to the staging area


  ```sh
  $ git add fan-fiction.md
  ```

  This puts fan-fiction.md into the **staging area**. If you make another change, it will be removed from it.

  To see what files you've changed and what is in your **staging area**, you can type `git status`. `git diff` will show you a more detailed view of the changes in your files.


7. ###### Commit your changes with a sweet commit message


  ```sh
  $ git commit -m 'A new animal appears!'
  ```

  A commit is the point at which the state of everything in the **staging area** is recorded.

8. ###### Push your changes to a branch on github


  ```sh
  $ git push origin your_branch_name
  ```

  This copies your branch information to the repository on GitHub.

  You should be able to see your branch [here](https://github.com/railsgirlswgtn/fan-fiction-github-challenge/branches).


9. ###### Create a pull request to master on github


  ![](http://i.imgur.com/zZPQLw0.png)

  Go through the steps to create a pull request on GitHub. The coaches will merge pull requests into master.

#### The next step: Updating your repository

  Hopefully when you create your pull request it should be able to successfully be merged and you should see this button:
  ![](http://i.imgur.com/XW3prtc.png)

  If you don't, you haven't done anything wrong, your branch is most likely just slightly out of date - maybe someone else's pull request was merged to master in the time since you cloned the repo.
  That means that you will have to **pull** from **origin** to get everyone elses' commits into your own.
  If you've got your Gryffindor or Ravenclaw hat on, you can do this yourself. Ready?

  1. First of all, if you are on a branch, make sure you have **committed** all of the changes you want to make. When you type `git status`, you want it to say: 'nothing to commit, working directory clean'.
    * There are more detailed instructions above about `git add` and `git commit`.
    * If you don't want to commit but you do want to switch branches, you can use `git stash` to hide the changes you have made and `git stash pop` to bring them back.

  2. Next, check out the master branch: `git checkout master`.

  3. Your task now is to `git pull`.
    * As long as your working directory is clean and you have only made commits to your branch and not to master, this should just pull the changes down from GitHub that everyone else has made. Your master branch should now look like the master branch on GitHub.
    * If you have made commits to master, you might get merge conflicts here. Skip ahead to point 8 for tips on resolving merge conflicts, and find a coach to get some help with getting your commits onto a branch.

  4. Now head back to the branch that your commits are on: `git checkout whatever_your_branch_is_called`.

  5. The next part is hard. Are you ready for it?

  6. Are you sure?

  7. Ok. Take a deep breath and type `git merge master`.
    * If you haven't made any commits since making this branch, or if you have only edited things that don't conflict with anything else, this will probably just come up with a text editor screen asking you for a commit message. You can just exit out of it by typing `:q`. Shazam. You are done. Proceed to step 11.
    * If you have made commits since making the branch, given that there a bunch of people editing the same file, it is extremely likely that you will have **merge conflicts**. You'll see this:

      ```
      Auto-merging fan-fiction.md
      CONFLICT (content): Merge conflict in fan-fiction.md
      Automatic merge failed; fix conflicts and then commit the result.
      ```

      * I have nightmares about merge conflicts.
      * They happen a lot less when there aren't a bunch of people editing the same parts of the same file.
      * Computers are great and fun. Really.

  8. `git status` will tell you what files are conflicted. Open them up in your text editor.

  9. You will probably see a bunch of things like this:
    ```
    <<<<<<< HEAD
      8. `git status` will tell you what files are conflicted. Open them up in your text editor.
    =======
      8. `git status` will tell you what cats are conflicted. Open those cats up in your text editor.
    >>>>>>> master
    ```
    Between `<<<<<<< HEAD` and `=======` is the stuff you have in your `HEAD`, which is your current branch.

    Between `=======` and `>>>>>>> master` is the stuff from master.

    So basically you want to manually move things around to make sure everyones' contributions are all there, nothing is doubled up, and you have deleted all of the `<<<<<<< HEAD` things.

    Grab a coach at this stage, or any stage, if you need help.

  10. `git status` should give you something like this:
    ```
    You have unmerged paths.
    (fix conflicts and run "git commit")

    Unmerged paths:
    (use "git add <file>..." to mark resolution)

    both modified:   fan-fiction.md
    ```
    If you `git add fan-fiction.md` then run `git status` again you should get:
    ```
    All conflicts fixed but you are still merging.
    (use "git commit" to conclude merge)

    Changes to be committed:

    modified:   fan-fiction.md
    ```
    Now, like it suggests, you can run `git commit` - or `git commit -m 'whatever your message is'` if you want to include a custom commit message.

    YOU WILL BE UP TO DATE and your MERGE CONFLICT WILL BE FIXED.

  11. You are the `git merge master`. You have overpowered the machine. High five someone.

#### Troubleshooting

* ###### I'm not sure what I have done and I am very confused and I think I have broken something!
  Excellent. You are doing well. Breaking things is very important.

  * `git status` has a lot of useful information about the branch you are on, what you have edited, and what you have added to the stage.
  * `git log` shows you a record of commits. It opens up in your command line text file reader, which you can get out of by typing `:q`.
  * `git branch` has information about all of the branches you have going on and which one is active.
  * `git stash` and `git stash pop` are quite useful commands. `git stash` basically hides away all of the changes you have made and not committed, then `git stash pop` brings them back out again.
  * If none of these are working, you might not be in the right directory - try `pwd` to see what directory you are in, `ls` to see what folders are in the directory you are in, and `cd fan-fiction-github-challenge` if you're in the parent directory.

* ###### I want to add a picture!
  Great. You can do this two ways:

  * A picture hosted elsewhere on the internet
  Grab the URL of your picture
  There are more instructions for markdown tricks in this [markdown cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
  ```
  ![Bub!](http://i.imgur.com/RkcdUD1.gif)
  ```
  ![Bub!](http://i.imgur.com/RkcdUD1.gif)

  * Putting a picture in this repository

  ```
  ![Merrin's cat!](images/merrins-cat.jpg)
  ```
  ![Merrin's cat!](images/merrins-cat.jpg)

