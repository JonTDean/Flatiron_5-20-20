
Answer:

hmmm, in terms of the domain you set up, Id say most of these are correct. The changes id make are:

* An album and artist don't need to have a unique name! The unique identifier for each instance of an album or artist is their primary_id, or key, or id, or whatever you want to call it. This allows our database to be able to differentiate instances by their id, so that multiple instance could share similarities. To relate it to real world, bands can share names inadvertently, and albums are certainly named the same. For the database, the id keeps them unique

* A song can have multiple albums if the relationship is to be believed! The album is the join table? so a song can be created independent to an album, and is only joined to an artist and album through the joiner.

Also, to write out domain relationships, make sure your chicken feet (arrows) point to the right way

    Zoo -< Animals
    Owner -< Pets
    Artist -< Album >- Songs

Separate thought, I find this domain to be incorrect! In my opinion. You could make a case for this, but when I think of it logically:

    An Artist has_many Albums
    An Albums has_many songs

    A Song belongs_to an Album
    An Album belongs_to an Artist
    
    Artist -< Album -< Song

 You can use this relationship to create through-relationships though: an Artist has_many Songs through Albums, and a Song belongs_to an Artist through Albums

Just food for thought lol