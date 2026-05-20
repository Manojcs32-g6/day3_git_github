1) git init => it initilizes the git into the folder where we wanted and closely observes the actions we do in the folder and sub-folders.

2) git status => it is the most frequently used command for checking the folder. what has been changed since the last snapshot.
it has:
untracked files: It is the files that it dont know by the git.
modified files: It is the files that has been modified since the last commit.
staaging files: It is the files where files are ready to commited.

3) git add => "git add" moves changes from your working directory into the "staging area."
git add "file_name.text" => it only moves changes specific file from the working directory to the staring area.
git add . => it will move complete files from working directory to the staging area. If already added it will moves modified one to the staging area.

4) git commit => This permanently saves your staged changes into the Git history. It takes whatever is in the staging area and locks it down with a unique ID.
example : git commit -m "Fix login page layout bug"

5) git log => this shows the chronological history of commits made in repo. It displayes the commit id(SHA-), the author, the date, the commit message. 

6) git branch => It shouws all the parallel versions of the project. by default, we start the branch named main or master.

7) git checkout -b new-feature => here -b means branch, when entered this command this copies the main project one to the parallel version named new-features here we can do all risky and edits in the file. when we are changing here the main file will be safe and untouched.

8) git merge => once all the edits and risk code done in new-feature and if it looks safe and wanted to take this code to the main we use git merge new-feature. this will take all the work to the main and blend it into your main project.

after want to go back to main then we should use:
git checkout main      # 1. Step out of your feature room and back into the main room
git pull                # 2. Make sure your main room has the absolute latest cloud updates
git merge new-feature   # 3. Pull the feature's changes into the main room

9) Conflict-makers => imagine you and a teammate both edit line 10 of the exact same file at the same time. When you try to merge them, Git gets confused: "Whose version should I keep?"

Git stops everything and drops Conflict Markers right into your code file to show you the clash. They look like this:
<<<<<<< HEAD
This is my version of the code (on main).
=======
This is my teammate's version of the code (on new-feature).
>>>>>>> new-feature
To fix it, you literally just delete the markers (<<<<<<<, =======, >>>>>>>) and edit the text until it looks exactly how you want it to, then make a new commit.

10) git remote add origin <url> => This connects the local scrap book into an online version. You are telling Git: "Hey, the cloud version of this project lives at this web address, and I'm going to nickname it 'origin'.

11) git push => This takes all the commits (snapshots) you made on your computer and uploads them to GitHub. It "pushes" your local work up to the cloud.

12) git pull => If git push is uploading your changes to the cloud, git pull is downloading everyone else's changes from the cloud to your computer.

Imagine you are working on a project with a friend. While you were sleeping, they wrote some new code, committed it, and git pushed it to GitHub. Your laptop doesn't know about this yet.

Before you start writing any new code, you run:
git pull

This tells Git: "Check the cloud, grab whatever new pages my friend added, and instantly blend them into the scrapbook on my laptop.".


Flow 1: Project Setup (Do This First) :

[Create a project folder on your computer]
       |
       v
    git init               (Creates your local Git repository)
       |
       v
    git remote add origin  (Connects your local Git to GitHub)
       |
       v
    git add .              (Stages your initial project files)
       |
       v
    git commit -m "init"   (Saves your very first snapshot)
       |
       v
    git push -u origin main (Uploads your project to GitHub)

Flow 2: The Daily Work Cycle (Do This For Every Feature)

    git pull               (Download latest updates from your team)
       |
       v
    git checkout -b feature (Create and jump into a safe branch)
       |
       v
[Write your code / make changes to files]
       |
       v
    git status             (Check which files you modified)
       |
       v
    git add .              (Stage your changes to be saved)
       |
       v
    git commit -m "message" (Save a snapshot of your work locally)
       |
       +-------------------> [Still editing?] ---> Loop back to "Write your code"
       |
[Finished with the feature!]
       |
       v
    git push origin feature (Upload your safe branch to GitHub)
       |
       v
[Open a Pull Request]       (Ask your team on GitHub to review it)
       |
       +-------------------> [If Conflict Markers appear] -> Fix files -> git add/commit
       |
       v
[Merge Pull Request]       (Merge your feature into the main project!)
       |
       v
    git log                (View your updated history of snapshots)


