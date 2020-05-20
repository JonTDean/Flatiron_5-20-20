# Deliverable Guidelines
### 1. `Class#attribute` // Should return the attribute of an instance
- This one requires that you be able to call an instance method on an object to return a variable. This variable was something passed into either an `attr_reader`, `attr_accessor`, or `attr_writer`, depending on whether or not they are mutable. They would also be passed in as arguments in initialization and declared as variables inside the initialization scope.
- When creating a new instance a variable that is assigned `NameOfClass.new`, those same attributes will be plugged into that statement.
- To call on them later on, because it is an instance method, you need to use the variable the instance was created for. If the variable was `person`, calling `person.name` would return this person’s name.
### 2.  `Class.all` // Return an array of instances
- You need to save every instance created in a Class Variable, like `@@all` that’ll return every instance of this class ever created. The test refers to the ability of the class to save many instances and return them when requested..
- Above your initialization, assign `@@all` to an empty array.
- Inside your initialization, under all your variable declarations, write `save` to refer to a method that’ll later on be called.
- The `save` method will be the action of shoveling `self` into `@@all`, `self` in this case referring to the current object that’s being created.
```ruby
def save
	@@all << self
end
```
- The method that’ll pass the test or satisfy the requirement for a class to have many of something is `.all`, which will be called on the class itself. This will go into `@@all` and return all the instance.
```ruby
def self.all
	@@all
end
```
### 3. `Class.find_by_attribute` // Can locate an instance, with a given attribute
- This is a class method that calls on `self.all` to sift through each instance to find a particular attribute that matches the string provided as an argument.
- To approach, you need to grab `self.all` and enumerate over it using `#select` to filter an array of subjects, as you search for the attribute that matches the attribute you have.
- To use the bracket syntax for enumeration in ruby, the double pipes would take a single item to index over, `{|item| item}`. This will list out each element one by one. Then to grab the exact attribute in each instance, you would need to specify what it is you’re trying to grab. So if it’s a person’s name, you can target that with `{|item| item.name}`. Then to compare it with the string you have, `{|item| item.name == str}`.
- Because this is a class method, it will have to be called on the name of the Class, not an instance, because the list of instances to choose from will be in `@@all`
- *E.G* from Blood Oath // `Cult.find_by_name`: takes a  `String`  argument that is a name and returns a  `Cult`  instance whose name matches that argument
```ruby
def self.find_by_name(str)
	self.all.select {|cult| cult.name == str}
end
```
- *E.G.* from Silicon Valley // `Startup.find_by_founder`: given a string of a  **founder’s name**, returns the  **first startup**  whose founder’s name matches
```ruby
def  self.find_by_founder(str)
self.all.select {|startup| startup.founder == str}[0]
end
```
- *E.G. from Animal Zoo // `Animal.find_by_species`: should take in an animal’s species as an argument and return an array of all the animals, which are of that species.
```ruby
def self.find_by_species(spec)
	self.all.select {|animal| animal.species == spec}
end
```
### 4. `Class#instance` // Return all the instances that a specific instance has // Has many of something
- Whatever the relationship between objects, either *has many*, *belongs to*, *many to many*-- there needs to be a way to store who has what. This requires a connection between two classes, because one will be holding every instance of another-- because it’s been assigned to it.
- This is an instance method, so it will be called on a variable, like `Nightclub`. There could be many nightclubs with many resident DJs.
- To find the instances, you would need to check out what `ResidentDJs` has stored in their class variable `@@all`. Similar to the above method, you’re grabbing `ResidentDJs.all` and enumerating over it with `#select`. Then you target the attribute that would link both `ResidentDJs` and `Nightclub` The condition you need to match it against would be `self`, because you’re referring to the instance that this method is being called on. In on other words, this instance is being given a message to do something either to, or for itself.
```ruby
def djs
	ResidentDJs.all.select {|dj| dj.club == self}
end
```
- *E.G.* from Animal Zoo // `Zoo#animals` should return all the animals that a specific instance of a zoo has.
```ruby
def animals
	Animal.all.select {|animal| animal.zoo == self}
end
```
### 6. `Class#AttrAboutInstances` // Return data about specific instances, that this specific instance has many of
*Forgive me, I don’t know the best way to word a title about this*
- This method also requires two classes (or more) to be linked together somehow. Because this test usually asks for the details about an instance, that is tied to another instance. As an abstraction, you could picture that same `Nightclub`, and their `ResidentDJs`, and wonder what genres they play to organize an event that’ll attract the enthusiasts who love a mix of Berlin Techno with Burning Man Playatech.
- This method would be called on the parent class-- so not to an instance of `ResidentDJs`, but rather `Nightclub`, because the `ResidentDJs` belong to the `Nightclub` (for however long their contract obliges).
- This instance method gets to work with the above method-- because you need to be able to narrow down to your DJs only since they’re your residents.
- The above method sifts through all of the instances passed into `ResidentDJs` until it finds the one whose nightclub attribute matches your nightclub.
- You can then call on that method, thereby getting the results of that method, to enumerate over that, because it returns an array of those instances.
- Then you need to index through that array, but instead of filtering to match a specific condition, you just need to collect all occurrences of a certain parameter, using `#collect`. This then returns an array with each genre.
- To make sure you get one of each element, or to *de-dupe* your result, you can latch `.uniq` to the end, to delete any duplicates.
```ruby
def genres
	djs.collect {|dj| dj.genre}.uniq
end
```
- *E.G.* from Animal Zoo //`Zoo#animal_species`: should return an array of all the species (as strings) of the animals in the zoo. However, if you have two dogs, it should only return one “Dog” string (aka an **unique** array).
```ruby
# While this returns the array of instances
def animal
	Animal.all.select {|animal| animal.zoo == self}
end
# This would grab out each species as a string
def animal_species
	animals.collect {|animal| animal.species}.uniq
end
```
- *E.G.* from Art Gallery // `Gallery#artists`: Returns an  `array`  of all artists that have a painting in a gallery
```ruby
# This action has three parts
# First, we need to get all the paintings that belong in this gallery
def paintings
	Painting.all.select {|painting| painting.gallery == self}
end
# Second, we need to get all the instances of artists here-- but we only need to get one of these instances.
def artists
	paintings.collect {|gallery| gallery.artist}.uniq
end
# Third, we should call on that method to get its narrowed down results, and then we can iterate over them again, to grab the string value of a a specific attribute.
def artist_names
	artists.collect {|artist| artist.name}
end
```
### 7. `Class.total_num` // Get the total of anything
- This needs to return an integer of a total value, because the attributes might consist of items in a cart, and the total cost needs to be calculated.
- This is a class method, so that means it’ll be called on the Class itself, and iterate through each element in `@@all` to add those together.
- To grab each element in `@@all`, you need to call `self.all` with `#collect`. Within the brackets, you need to define what attribute it is that you’d like to increment, `self.all.collect {|item| item.value}`. This in effect, would return its own array.
- The next thing to do would be to add all those elements together, using `#reduce`. A more verbose way of approaching this is creating a new variable assigned to 0, called `total`. Then using either an `.each` loop that will go on for each element in an array, or a while loop with a variable for `count` assigned to 0-- anything that will run as long as a condition is true-- you can index through each element in the array, add it to `total` and return the `total`. For the while loop, you would have to manually increment the `count` to prevent an infinite loop since the method won’t know when to terminate.
- `#reduce` is the more minimal approach to this. To start, instead of creating a variable for `total`, you just declare what value you want to start at: `.reduce(0)` -- which means our total right now, is 0.
- Inside the brackets, we have two indexers in the double pipes, a `total` and a `sum`.
- `#reduce` will iterate over this array, adding each item to the total, like such `.reduce(0) {|total, sum| total + sum}`
- *E.G.* from Art Gallery // `Artist.total_experience`: Returns an  `integer`  that is the total years of experience of all artists
```ruby
def self.total_experience
	self.all.collect {|xp| xp.years_experience}.reduce(0) {|total, sum| total + sum}
end
```
Methods to explain
`Gallery#most_expensive_painting`: Returns an  `instance`  of the most expensive painting in a gallery
```ruby
def most_expensive_painting
	paintings.max_by {|painting| painting.price}
end
```
`Artist.most_prolific`: Returns an  `instance`  of the artist with the highest amount of paintings per year of experience
```ruby
def self.most_prolific
	self.all.max_by {|artist| artist.years_experience / artist.paintings.count}
end
```
`Artist#create_painting`: Given the arguments of  `title`,  `price`  and  `gallery`, creates a new painting belonging to that artist
```ruby
def create_painting(title, price, gallery)
	Painting.new(title, price, self, gallery)
end
```