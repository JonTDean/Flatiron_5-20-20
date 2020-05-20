
## Quick Code Tips:

<a name="dir_han">1</a>: Directory Handling
<Details>
<summary> Directory Handling Command List </summary>

1. In order to change to that directory:

```zsh
    cd ./directory_name/
```

2. In order to change into a nested directory:

```zsh
    cd ./directory1_name/directory1_name
```

3. In order to go to the root folder:

```zsh
    cd ~
```

4. In order to see what directories you have:

```zsh
    ls
```

5. In order to see your current Directory:

```zsh
    pwd
```

6. In order to create a Directory:

```zsh
    mkdir Folder_Name
```

7. In order to create a File:

```zsh
    touch file_name.fileType
```

8. In order to move a file to a Directory:

```zsh
    mv file_name Directory_Name

    (If a !!folder!! doesn't exist, file is recreated with Directory_Name value!!)
```

9. In order to copy file:

```zsh
    cp file_to_copy target_file

    (If a file doesn't exist one is created)
```

10. (Cut: a) In order to rename and delete file (Renames to target):

```zsh
    cp file_to_cut target_file && rm file_to_cut

    (If a file doesn't exist one is created)
```

11. (Cut: b) In order to cut file and delete file (Renames to target):

```zsh
    mv file_to_copy target

    (If a !!folder!! doesn't exist a file is created)
```

</Details>

----

<a name="git">2</a>: Git Life
<Details>
<summary> Git Command List </summary>

1. To create a repository

    1. Go to https://github.com/new

    2. Type in repository name, and a description

    3. Ignore gitignore

    4. Ignore License (or use MIT)

    5. Hit "Create Repository"

2. To use an empty repository

    *If you have not created a folder, create one.*

    1. In your terminal cd into the folder you're using and type:

        ``` git init ```

    2. Add the repository to the .git:

        ``` git remote add origin git@github.com:admin/git_link.git ```

3. To use an existing repository on local machine
    1. Go to repository link and click -- **Fork** --

    2. Clone repository to machine in Current Folder

```zsh
    git clone git@github.com:admin/git_link.git
```

4. To update local copy with new commits and data from Repository

```zsh
    git pull git@github.com:admin/git_link.git
```

5. To update local copy with new commits

```zsh
    git fetch git@github.com:admin/git_link.git
```

6. To push current local copy to Repository

    Stage All Files (Including new files)

    1. Add all files ( **.** is a wildcard) 

        ``` git add . ```

    2. Commit files (Quotes can contain anything)

        ``` git commit -m "Test Commit" ```

    OR Stage All Files (Not including new files)

    1. Automattically stage files that have been modified

        ``` git commit -a -m "Test Commit" ```

    Push files

    1. Push files to repositiory

```zsh
        git push -u origin branch_name
```

7. How to create a branch and How to switch a branch
    1. Create a Branch

        ``` git branch branch_name ```

    2. Switch to a Branch

        ``` git checkout branch_name ```

9. To merge branches

    1. Check what branch you're on

    2. Switch to the branch you want to merge into.
        
        If you want to take branch_B and merge it into branch_A:

        **You need to checkout to branch_A**

    3. Merge branches

```zsh
        git merge branch_B
```

10. To delete a remote branch and a local branch

    Remote Branch:

    ``` git branch -d branch_name ```

    Local branch:

    ```git branch -D branch_name```

</Details>

----

<!-- <a name="myfootnote1">1</a>: Ruby Enumerators
<Details>
<summary> Directory Handling List </summary>
</Details> -->
