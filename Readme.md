# Group 5-20-20 - Dealing with Classes and SQL

Links for information:

[Google Sheets 5-20-20](https://docs.google.com/spreadsheets/d/1RGOYBuG0Bu5QgQnuIgoaBYOLj2vm-I4ev9T_l9tXRng/edit?usp=sharing)

[Relationship Diagram](https://drive.google.com/file/d/1Tgu8KHpLVkpyrsYzIf382tGSlmfKa3jR/view?usp=sharing)

-----
## Assignment:

Create a relational database between

1. Class :: Artist

2. Class :: Album

3. Class :: Song

## RULES
<dl> 
<dt>Class :: Album: </dt>
    <dd>An album belongs to one artist</dd>
    <dd>An album has multiple items</dd>

<dt> Class :: Artist: </dt>
    <dd>An artist must have a unique name</dd>
    <dd>An artist must have unique album names and unique song names.</dd>
    <dd>An artist has multiple albums</dd>
    <dd>An artist has multiple songs through albums</dd>

<dt>Class :: Song: </dt>
    <dd>A song must be unique to an album</dd>
    <dd>A song belongs to one album</dd>
    <dd>A song belongs to an artist through album</dd>
</dl>  

Step 1: Create Classes
We know we have three classes we need to create: Artist, Album, Song.

Example:

```ruby
class ClassName

end
```

<Details>
<summary> Final Code for Step 1 </summary>

1. Artist:

For <sup>[1](#dir_han)</sup> *./lib/artist.rb*

```ruby
class Artist

end
```

2. Album:

For <sup>[1](#dir_han)</sup> *./lib/album.rb*

```ruby
class Album

end
```

3. Song:

For <sup>[1](#dir_han)</sup> *./lib/song.rb*

```ruby
class Song

end
```
</Details>


---
