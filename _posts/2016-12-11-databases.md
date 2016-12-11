---
layout: post
title: Database Choices
description: Current choices for Databases - How to plan the data architecture for your requirements? What Type of database to choose?
img: database.jpg
color: 212121
author: sarvex
---
There are a phelothra of choices today when it comes to database; we have traditional Relational DataBase (RDBMS), we have new enterants which hated the SQL and aptly called themselves NoSQL and we have the fresh wave of Graph Databases.

Databases can trace back there origins form data structures. There was a time when Graphs were considered too complex a data structure and we have to resort to stipped down representation in form of a tree. Everything Computer Scientists did revolved primarily around trees and thus recreated the same structure in Databases - giving rise to Relational Databases.

Now traversing the edges is the most expensive operation. Tranversing the edges in RDBMS was done by joins and a complex query with lot of joins was really slow. This lead to rise of Data Architects who can optimize the query and the database to make querying faster. Most efficient optimization that made RDBMS efficient again was Stored Procedures. Stored Procedure allowed to store a complex query in the database; the database was optimized the query and executed it periodically to store the results locally. This meant that there was no SQL execution when a stored procedure was called, it simply returned the pre-calculated results. Now the databases required more niche skills; Database Administrator, Database Architect, and Stored Procedure programmer.

Caching was a good way to sideline the performance capabilities of RDBMS. Performant websites were employing cahing in one form of another. Some solutions were even standardized and open sourced (memcached). It was easy to have a key-value pair and almost overnight everyone was having one. Suddenly a new name was given to this caching mechanism, it was NoSQL. It went on like a craze, with more than a dozen choices to make.

But associative arrays (key-value stores/NoSQL) had major drawback. To bypass the tree structure, we were forced to duplicate data. Data duplication is not only more storage space, but also data consistency hazard: Data changed in one place should be properly reflected at other locations. And the problem was accentuated by use of only NoSQL solutions in the architecture.

Key-Value stores were never meant for replacing the RDBMS, they were there to find a shortcut traversing tree edges. But developers become zealot and abandoned RDBMS and getting their hands burnt with data consistency hazard. A properly architected deployment stack should have both NoSQL and RDBMS connected over a decent Messaging Queue (such as Kafka)

Image Credits - [Michael Mandiberg](http://www.mandiberg.com/about/)
