
## Quick Code Tips:
Contents

[Directory Handling](#dir_han)
<Details>
<summary>Contents</summary>

1. [To change to a directory](#dir_han_1)

2. [To change into a nested directory](#dir_han_2)

3. [To go to the root system folder](#dir_han_3)

4. [To see what directories you have](#dir_han_4)

5. [To see your current Directory](#dir_han_5)

6. [To create a Directory](#dir_han_6)

7. [To create a File](#dir_han_7)

8. [To move a file to a Directory](#dir_han_8)

9. [To copy file](#dir_han_9)

10. [(Cut: a)To cut and delete file (Renames to target)](#dir_han_10)

11. [(Cut: b) To cut file and delete file (Renames to target)](#dir_han_11)
∂∂
</Details>

[Git](#git)

<Details>
<summary>Contents</summary>

1.[To create a repository](#git_1)

2.[To use an empty repository](#git_2)

3.[To use an existing repository on local machine](#git_3)

4.[To update local copy with new commits and data from Repository](#git_4)

5.[To update local copy with new commits](#git_5)

6.[To push current local copy to Repository](#git_6)

7.[How to create a branch and How to switch a branch](#git_7)

8.[To merge branches](#git_8)

9.[To delete a remote branch and a local branch](#git_9)

</Details>

----

<a name="dir_han">1</a>: Directory Handling
<Details>
<summary> Directory Handling Command List </summary>



<a name="dir_han__1">1.</a> In order to change to that directory:

```zsh
    cd ./directory_name/
```

<a name="dir_han__2">2.</a> In order to change into a nested directory:

```zsh
    cd ./directory1_name/directory1_name
```

<a name="dir_han__3">3.</a> In order to go to the root System folder:

```zsh
    cd ~
```

<a name="dir_han__4">4.</a> In order to see what directories you have:

```zsh
    ls
```

<a name="dir_han__5">5.</a> In order to see your current Directory:

```zsh
    pwd
```

<a name="dir_han__6">6.</a> In order to create a Directory:

```zsh
    mkdir Folder_Name
```

<a name="dir_han__7">7.</a> In order to create a File:

```zsh
    touch file_name.fileType
```

<a name="dir_han__8">8.</a> In order to move a file to a Directory:

```zsh
    mv file_name Directory_Name

    (If a !!folder!! doesn't exist, file is recreated with Directory_Name value!!)
```

<a name="dir_han__9">9.</a> In order to copy file:

```zsh
    cp file_to_copy target_file

    (If a file doesn't exist one is created)
```

<a name="dir_han__10">10.</a> (Cut: a) In order to rename and delete file (Renames to target):

```zsh
    cp file_to_cut target_file && rm file_to_cut

    (If a file doesn't exist one is created)
```

<a name="dir_han__11">11.</a> (Cut: b) In order to cut file and delete file (Renames to target):

```zsh
    mv file_to_copy target

    (If a !!folder!! doesn't exist a file is created)
```

</Details>

<a name="git">2</a>: Git Life
<Details>
<summary> Git Command List </summary>

<a name="git_o">1.</a> To create a repository

    1. Go to https://github.com/new

    2. Type in repository name, and a description

    3. Ignore gitignore

    4. Ignore License (or use MIT)

    5. Hit "Create Repository"

----

<a name="git_2">2.</a> To use an empty repository

*If you have not created a folder, create one.*

1. In your terminal cd into the folder you're using and type:

```zsh
         git init
```

2. Add the repository to the .git:

```zsh
        git remote add origin git@github.com:admin/git_link.git
```

----

<a name="git_3">3.</a> To use an existing repository on local machine

1. Go to repository link and click -- **Fork** --

2. Clone repository to machine in Current Folder

```zsh
    git clone git@github.com:admin/git_link.git
```

----

<a name="git_4">4.</a> To update local copy with new commits and data from Repository

```zsh
    git pull git@github.com:admin/git_link.git
```

----

<a name="git_5">5.</a> To update local copy with new commits

```zsh
    git fetch git@github.com:admin/git_link.git
```

----

<a name="git_6">6.</a> To push current local copy to Repository

Stage All Files (Including new files)

1. Add all files ( **.** is a wildcard)

```zsh
    git add .
```

2. Commit files (Quotes can contain anything)

```zsh
         git commit -m "Test Commit"
```

OR Stage All Files (Not including new files)

1. Automattically stage files that have been modified

```zsh
         git commit -a -m "Test Commit"
```

Push files

1. Push files to repositiory

```zsh
        git push -u origin branch_name
```

----

<a name="git_7">7.</a> How to create a branch and How to switch a branch

1. Create a Branch

        ``` git branch branch_name ```

2. Switch to a Branch

        ``` git checkout branch_name ```

----

<a name="git_8">8.</a> To merge branches

1. Check what branch you're on

2. Switch to the branch you want to merge into.

```
        If you want to take branch_B and merge it into branch_A:

        You need to:
        git checkout branch_A
```

3. Merge branches

```zsh
        git merge branch_B
```

----

<a name="git_9">9.</a> To delete a remote branch and a local branch

Remote Branch

``` zsh
    git branch -d branch_name
 ```

Local branch

```zsh
    git branch -D branch_name
```

</Details>

<!-- <a name="myfootnote1">1</a>: Ruby Enumerators
<Details>
<summary> Directory Handling List </summary>
</Details> -->
