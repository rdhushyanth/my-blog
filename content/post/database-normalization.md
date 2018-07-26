---
layout: post
title: Database Normalization
date: 2009-05-30
tags: ["database","normalization","web-development"]
---

I think <cite>I</cite> should make a standard template of these "newbie tech-talk" posts. Briefly speaking tthe first 4-5 lines will be my general chatter then I'll post a heading then 3-4 lines of introduction and then a list of resources I had on the net and then a brief wrap-up i.e my take on the matter

Database Normalization:

Ok I'll admit at the outset- I have never ever written a MySQL query. But I think the theoretical aspects are clear to me-

So why do we need normalization.

1. To eliminate redundant data-removing same information stored in different places.

2. To ensure only related data is there in a table

3. It helps to save storage space(a quite precious commodity), ensures faster lookups, and other stuff which I don't know about ;)

I'll start out by listing some very nice resources:

1. The initial wiki stuff which I must admit is quite sparse(all theory no practical)- [http://en.wikipedia.org/wiki/Database_normalization](http://en.wikipedia.org/wiki/Database_normalization "wiki link") and the related E-R diagrams- [http://en.wikipedia.org/wiki/Entity-relationship_model](http://en.wikipedia.org/wiki/Entity-relationship_model "Wiki- er model")

2. Now to the practical aspects- [http://www.phlonx.com/resources/nf3/](http://www.phlonx.com/resources/nf3/ "normalization walk-through") Ok this one is the best normalization tutorial. It makes the database normalization process crystal clear. I'll advice you go through this one definitely

3. [http://databases.about.com/od/specificproducts/a/normalization.htm](http://databases.about.com/od/specificproducts/a/normalization.htm "normalization tutorial") a good read. Not as methodical as the previous one  but it discusses a little(very little) about 4NF which may be useful. Either way, a quick read won't hurt. a similar link would be: [http://www.devhood.com/tutorials/tutorial_details.aspx?tutorial_id=95](http://www.devhood.com/tutorials/tutorial_details.aspx?tutorial_id=95 "devhood")

4. [http://dev.mysql.com/tech-resources/articles/intro-to-normalization.html](http://dev.mysql.com/tech-resources/articles/intro-to-normalization.html "mike hillyer") ,Now Mike is a bigwig in the MySQL business so I must include this too ;) His post got me interested in his presentation [http://www.mikehillyer.com/presentations/](http://www.mikehillyer.com/presentations/) named "introduction to database modeling with MySql workbench". I am sure the rest of his presentations were also as wonderful, but I didn't have time to go through all of them.

Wrap up:

The normal forms are cumulative- for a database to be in 3NF, it must satisfy 1NF AND 2NF criteria . So 1NF says make your table atomic- there should be no grouping of data, everything should be laid bare. 2NF says every column should be related to all the members of the primary key. If not separate related data and form a new table and relate it to the original table through "foreign keys". The 3NF requires that every field depends on ONLY primary key( i.e equivalently on the fields that make up the primary key)

Now I present some informal way to make DB designing painless and easy. These steps help in getting the general outline of the overall database:

1. Understand the problem at hand

2. Every noun(entity) has its own table.

3. Every table has an id which serves as it's primary key

4. now start looking into interrelations

i. If its a many to many relationship between two nouns then create a associating table(usually named by concatenating the two nouns) with its own id and the ids of the two tables as foreign keys.

5. The foreign key always flows from the one to many table and not the other way round.

I'll point out again that these are sort of my own quick fixes, and quick fixes are always dirty and frowned upon. But they atleast give you a rough idea of the final database structure.

Have fun!

ciao<cite></cite>