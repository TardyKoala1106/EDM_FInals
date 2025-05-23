## Final Task 6 - MongoDB

## 1 - INSERTS

1. Insert Movies
# Code:
db.movies.insertMany([
  {title: "Fight Club", writer: "Chuck Palahniuk", year: "1999", actors: ["Brad Pitt", "Edward Norton"]},
  {title: "Pulp Fiction", writer: "Quentin Tarantino", year: "2009", actors: ["John Travolta", "Uma Thurman"]},
  {title: "Inglorious Basterds", writer: "Quentin Tarantino", year: "2009", actors: ["Brad Pitt", "Diane Kruger", "Eli Roth"]},
  {title: "The Hobbit: An Unexpected Journey", writer: "J.R.R. Tolkein", year: "2012", franchise: "The Hobbit"},
  {title: "The Hobbit: The Desolation of Smaug", writer: "J.R.R Tolkien", year: "2013", franchise: "The Hobbit"},
  {title: "The Hobbit: The Battle of the Five Armies", writer: "J.R.R Tolkien", year: "2002", franchise: "The Hobbit", synopsis: "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."},
  {title: "Pee Wee Herman's Big Adventures"},
  {title: "Avatar"}
]);
You sent
db.users.insertMany([
  {_id: 1, username: "GoodGuyGreg", first_name: "Good Guy", last_name: "Greg"},
  {_id: 2, username: "ScumbagSteve", fullname: {first: "Scumbag", last: "Steve"}}
]);
# Output:

## 2 - FINDS

2-1. Get All Documents
# Code:
db.movies.find()
# Output:

2-2. Get Documents(Quentin)
# Code: 
db.movies.find({writer:"Quentin Tarantino"})
# Output:

2-3. Get Documents(Brad)
# Code:
db.movies.find({actors:"Brad Pitt"})
# Output:

2-4. Get Documents(The Hobbit)
# Code:
# Output:

2-5. Get Documents(90s)
# Code:
db.movies.find({year:{$gt:"1990", $lt:"2000"}})
# Output:

2-6. Get Documents(Before 2000s or After 2010s)
# Code:
db.movies.find({$or:[{year:{$gt:"2010"}},{year: {$lt:"2000"}}]})
# Output:

## 3 - UPDATES

3-1. add a synopsis to "The Hobbit: An Unexpected Journey"
# Code:
db.movies.update({_id:ObjectId("5c9f98e5e5c2dfe9b3729bfe")}, {$set:{synopsis:"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}})
# Output:

3-2.  add a synopsis to "The Hobbit: The Desolation of Smaug"
# Code:
db.movies.update({_id:ObjectId("5c9fa42ae5c2dfe9b3729c03")}, {$set:{synopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
# Output:

3-3.  add an actor named "Samuel L. Jackson" to the movie "Pulp Fiction"
# Code: 
db.movies.update({_id:ObjectId("5c9f983ce5c2dfe9b3729bfc")}, {$push:{actors:"Samuel L. Jackson"}})
# Output:

## 4 - TEXT SEARCH

4-1. find all movies that have a synopsis that contains the word "Bilbo"
# Code:
db.movies.find({synopsis:{$regex:"Bilbo"}})
# Output:

4-2.  find all movies that have a synopsis that contains the word "Bilbo" and not the word "Gandalf"
# Code:
db.movies.find({$and:[{synopsis:{$regex:"Bilbo"}}, {synopsis:{$not:/Gandalf/}}]})
# Output:

## 5 - DELETE

5-1. delete the movie "Pee Wee Herman's Big Adventure"
# Code:
db.movies.remove({_id:ObjectId("5c9f992ae5c2dfe9b3729c00")})
# Output:

5-2: delete the movie "Avatar"
# Code:
db.movies.remove({_id:ObjectId("5c9f9936e5c2dfe9b3729c01")})
# Output:

## 6 - RELATIONSHIPS

6-1. Users Collection
# Code:
db.users.insertMany([
  {_id: 1, username: "GoodGuyGreg", first_name: "Good Guy", last_name: "Greg"},
  {_id: 2, username: "ScumbagSteve", fullname: {first: "Scumbag", last: "Steve"}}
]);


6-2. Posts Collection
# Code:
db.posts.insertMany([
  {username: "GoodGuyGreg", title: "Passes out at Party", body: "Raises your credit score"},
  {username: "GoodGuyGreg", title: "Steals your identity", body: "Raises your credit score"},
  {username: "GoodGuyGreg", title: "Reports a bug in your code", body: "Sends you a pull request"},
  {username: "ScumbagSteve", title: "Borrows something", body: "Sells it"},
  {username: "ScumbagSteve", title: "Borrows everything", body: "The end"},
  {username: "ScumbagSteve", title: "Forks your repo on github", body: "Sets to private"}
]);

6-3 Comments Collection
# Code:
db.comments.insertMany([
  {username: "GoodGuyGreg", comment: "Hope you got a good deal!", post: ObjectId("POST_ID_1")},
  {username: "GoodGuyGreg", comment: "What's mine is yours!", post: ObjectId("POST_ID_2")},
  {username: "GoodGuyGreg", comment: "Don't violate the licensing agreement!", post: ObjectId("POST_ID_3")},
  {username: "ScumbagSteve", comment: "It still isn't clean", post: ObjectId("POST_ID_4")},
  {username: "ScumbagSteve", comment: "Denied your PR cause I found a hack", post: ObjectId("POST_ID_5")}
]);

## 7 - QUERY RELATED  COLLECTIONS

7-1. find all users
# Code:
db.users.find().pretty()
# Output:

7-2. find all posts
# Code:
db.posts.find().pretty()
# Output:

7-3. find all posts that was authored by "GoodGuyGreg"
# Code:
db.posts.find({username:"GoodGuyGreg"})
# Output:

7-4. find all posts that was authored by "ScumbagSteve"
# Code:
db.posts.find({username:"ScumbagSteve"})
# Output:

7-5. find all comments
# Code:
db.comments.find().pretty()
# Output:

7-6. find all comments that was authored by "GoodGuyGreg"
# Code:
db.comments.find({username:"GoodGuyGreg"})
# Output:

7-7. find all comments that was authored by "ScumbagSteve"
# Code:
db.comments.find({username:"ScumbagSteve"})
# Output:




