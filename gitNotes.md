# Git and Github 
git --version






## 3 stages
 - working directory
 - staging area
 - Repository



# git commands
1. git init 

    this is used to initilize a watchman in our working directory whcich tracked our files.it make a folder like .git and it is our local directory which will be hidden by default but you can unhide it.

2.  git add file_name

    after initilize git in your working directory files are not tracked to tracked our files we write this command git add filename if we want to tracked our all files then we can write (git add .)

3. git commit -m "message"

     after git add. our files remain in a stagging area where we can modify or change but to push that changes in our local directory or in .git we write this command with a commit message.

4. **git branch -M main**

    before push our code on remote repositiry we change the branch in local repository branch is master but in github it is main.

5. git remote add origin (github repository link):
    if we first time push our code and we did not tell the repository where we want to store our code then we run this command first
    git remote add origin (http://github repository link)

6. git push -u origin main
    to push our code in remote directory like to gitHub we write this commad if we first time write this commad then we write this complete but after that we can write (git push) only.

# git status
 by this command we can check that which files are tracked and modify and untracked







# git log --oneline
 with this command we can check or see all our commits 
 it has flag like --oneline in which you can check commits in shorts summary

# git restore filename
 this command is used when we want to undo when we are in satgging area and  still not push our code.We can also untracked our file if we want but before push.to make a file untracked we write this command (git restore --staged file_name)

 for undo from staging area 
- git restore filename

 for untracked file which is in staging area
 - git restore --staged filename



# git Revert 
we mostly used this command if we want to undo our code from after commit.
this used to undo your code.
but it did not delete your commit it make a new commit.

# git reset
this work same like revert but, 
we dont use so much this command because it is not save.
this is also used to undo your code but it delete your commit
it has three flag
- --mixed (by default)
- --soft  
- --hard  (dangerous)

# to make alias of commad
    we can make a shorter alias for commands 
    git config --global alias.b branch
    here we make a alias b for our branch command so if we now write git b it still work same

    and if we do not write --global flag then it alias work only that directory not global 

    we can write alias by edit .gitconfig file
    go in bash and write  nano ~/.gitconfig and here we can make alias

    [alias]
            st = status
            b = branch

# branch concept in git
  we can make multiple copies of our original code and we can make chnages these branches and after finalize we can merge that branch with our main branch we actually make branches so that different member work on different things and  actual branch not effect.

  **we can make new branch by :**
  git branch seconed
  **and to come in this branch :**
  git checkout seconed  
  or
  git switch seconed
  **or to create and switch to that branch together:**
  git checkout -b third
  or 
  git switch -c fourth

  **to delete a branch:**
  git branch -D third


  **to merge branch into main branch**
  if we done in our branch and want to merge with main branch first we came in main branch and then write 

  git merge seconed
  git push  -u origin main

# git amend
  in git we commit when we make a complete function or functionality and add in our code we dont commit after each line change. so when we change in our previous commit then we dont create a new commit we only add this is previous commit 
  for that we write:
  git commit --amend -m "Homepage"
  in commit message we can write the old commit and we can aldo change it with new.but it did not add a new commit it only change new commit message
  and if you push the code on github then dont amend the commit it is not good practice because it make a new hash which conflict wih other member.

# git clone
  if you want to contribute in a project then you should have a project in your system for that you make a clone of that project.
  create a  new folder and open gitbash terminal and write this commad:
  *git clone repository link .* add . to clone in current directoryf

  we should not download the zip folder because in this way we cannot have .git directory in which our code track include and it is not best practice

  if you want to clone a specfic branch not main branch then 
  *git clone --branch branch-name reository-link*

# git pull and git fetch

 if our tem member change something and we want to have that code also in our system for that we use that fetch command

 *git fetch origin*

 by run this command it did not change our working directory first we check how many commits are done 

 *git status*

 and then we merge:

 *git merge origin/main*

and git pull command do the both work means it fetch and merge together dont  which can be dangerous while working on a big project because it can overwrite the code or change your code by your member

*git pull origin main*


# deploy your (staticfiles) project on github:
  for simple html and css javscript file you only push code and in pages you can deploy it.

  for React:
  first you install gh-pages
  npm i gh-pages
 
  then you add in vite.config file
  base:"/movies-website/",

  then you change your packge.json file

  like in script you add 

  "deploy":"gh-pages -d dist"

  after that you push your code on github
  then we make a build file of our code beacaue our browser dont know react it knows only html css and javscipt file that why we maka a build version

  npm run build 
  it makes a dist folder production ready project

  then we run:
   npm run deploy

   it make a branch on gh-pages use dist folder to deploy project

# git diff

   to check differnce between your working directory or local directory

   git diff --staged to check between differnce working directory and staged directory

   git diff origin/main to check diff betwen local directory and remote directory

   git diff --name-only


   ## skip stagging area
   git commit -a -m "skip staging area"









# Docker

   we make a docker file in our root directory of app by the name of dokerfile and write commands in it.

   **.dockerignore**
   it is a file like .gitignore we write folder or files name to ignore while building the image of app


   **to make a image of your project**
   docker build -t my-app .

   **to check images**
   docker images

   **to remove all images and conatiner**
   docker system prune -a 

   **to update in app**

   when we do some changes we did not make new image we make version of our image

   docker build -t my-app:v2 .

# Volumes

  **storage mechnaism**
   if we used volume : chnages made in the local project directory are automatically reflected inside the container then we dont need to make new images after some update

   docker run --name my-container -p 3000:3000 --rm -v "E:/Devops:/app" my-app 
  
# compose file
 this file used to write configuration to create an image and run the conatiner with only one command we write all commands in it and write one command

 **docker compose up**








