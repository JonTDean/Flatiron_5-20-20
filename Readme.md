# Group 5-20-20 - Dealing with Classes and SQL

## Big Thanks to Dina and Jack for everything!

Links for information:

[Google Sheets 5-20-20](https://docs.google.com/spreadsheets/d/1RGOYBuG0Bu5QgQnuIgoaBYOLj2vm-I4ev9T_l9tXRng/edit?usp=sharing)

[Relationship Diagram](https://drive.google.com/file/d/1Tgu8KHpLVkpyrsYzIf382tGSlmfKa3jR/view?usp=sharing)

-----

## Rules

### Create a relational database between Artist, Album, Song

#### Consider the following, how would you explain these
1. **A -< A -< S**
```zsh
        Artist -< Album -< Song
```

<Details>
<summary> A -< A -< S </summary>

#### A proper breakdown is

* An Artist has many Albums

```zsh
        Artist -< Album
```

* An Album has many Songs

```zsh
        Album -< Song
```

* A Song belongs to an Album

```zsh
        Song >- Album
```

* An Album belongs to an Artist

```zsh
        Album >- Artist
```

</Details>

2. **A -< A >- S**
```zsh
    Artist -< Album >- Song
```
<Details>
<summary> A -< A >- S</summary>

#### A proper breakdown is

* An Artist has many Albums

```zsh
        Artist -< Album
```

* An Song has many Albums

```zsh
        Song -< Album
```

* An Album belongs to an Artist

```zsh
        Album >- Artist
```

* An Album belongs to a Song

```zsh
        Album >- Song

```
</Details>

3.  SO >-< AL >- RL -< AG >-< AR

```zsh
        Song >-< Album >- RecordLabel -< Agent -< Artist
```
<Details>
<summary>S >-< A >- RL -< LS >-< A</summary>

* A Song has many Albums and An Album has many Songs

```zsh
        Song >-< Album
```

* An Album Belongs to a Record Label and a Record Label has many Albums

```zsh
        Album >- RecordLabel
```

* A Record label has many Agents and Agents have many Record Labels

```zsh
        RecordLabel -< Agent
```

* An Agent has many Artists and an Artist has an Agent

```zsh
        Agent -< Artist
```
</Details>

## Instructions

```<Class :: Artist>```

<Details>
<Summary>Artist</Summary>

\<Class :: Artist>

1. An instance of ```<Class :: Artist>``` is related to many instances of ```<Class :: Album>```
  
2. An instance of ```<Class :: Artist>``` is related to many instances of ```<Class :: Song>``` from ```<Class :: Album>```

3. An instance of ```<Class :: Artist>``` should have the following attributes:

    1. String :: Name of Artist
    2. String :: Stage Name of Artist
    3. Date :: Date of Birth (DD/MM/YYYY)
    4. Integer :: Years Performing

</Details>

-----

```<Class :: Album>```

<Details>
<Summary>Album</Summary>

\<Class :: Album>

1. An instance of ```<Class :: Album>``` is related to many instances of ```<Class :: Song>```

2. An instance of ```<Class :: Album>``` belongs to an instance of ```<Class :: Artist>```

3. An instance of ```<Class :: Album>``` should have the following attributes:

    1. String :: Album Name
    2. Date :: Date of Release (DD/MM/YYYY)
    3. Object :: \<Class :: Song>
    4. Object :: \<Class :: Artist>

</Details>

-----

```<Class :: Song>```

<Details>
<Summary>Song</Summary>

\<Class :: Song>

1. An instance of ```<Class :: Song>``` belongs to an instance of ```<Class :: Album>```

2. An instance of ```<Class :: Song>``` is related to an instance of ```<Class :: Artist>```  from  ```<Class :: Album>```

3. An instance of ```<Class :: Song>``` should have the following attributes:

    1. String :: Name of Song
    2. Date :: Date of Release (DD/MM/YYYY)
    3. Integer :: Song Length in Seconds

</Details>
