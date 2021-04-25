# bboard
cyse 570 bulletin board project

1) Set up Apache
2) Start a MySQL instance
3) Create a database named 'bboard_db'
4) Create a user 'bboard_user' with full privileges for the database and password 'swordFish99'
5) Create a table called 'bbusers' with the following command:
```create table bbusers (   email    varchar(50),   name     varchar(30),   password varchar(40),   nickname varchar(30),   primary key (email) );```

6) Create a table called 'postings' with the following command:
```create table bbusers (   email    varchar(50),   name     varchar(30),   password varchar(10),   nickname varchar(30),   primary key (email) ); create table postings (   postId       integer(5) auto_increment,   postDate     datetime,   postedBy     varchar(50),   postSubject  varchar(100),   content      varchar(512),   ancestorPath varchar(100),   primary key (postId), foreign key (postedBy) references bbusers (email));```

7) Create some dummy data for testin with the following commands:

```
insert into bbusers values ('bobmail','bob','123456','bobby'),
       ('alicemail','alice','pword','alice99'),
       ('cathymail','cathy','password','catlady');
    
insert into postings values ('1', '2020-04-01', 'cathymail', 'cats',
                             'I can fit my cats whole head in my mouth.',
                             'ancestorPath here'),
                            ('2', '2020-04-02', 'bobmail', 'dogs',
                             'Why is my dog constantly licking the floor?',
                             'ancestorPath here'),
                             ('3', '2020-04-03', 'alicemail', 'coffee',
                             'Please look at these pictures of coffee: 
                             https://www.pinterest.com/moowanq/coffee-gallery/',
                             'ancestorPath here');

```

8) Store the files in this repository at /var/www (or wherever your apache server is configured to server content from)
