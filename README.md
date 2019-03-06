# Implementation-of-a-NoSQL-Database-Model-in-Python-with-a-Redis-Cache
Implementation of a NoSQL database model, with added functions that allows user to add and query nodes and relationships to the database. A Redis cache was added and check before execution of a query.

# Components
* dbservice: Contains a simple dataservice.py implementing retrieve_by_template. This performs a SELECT to retrieve data from a table.
* redis_cache: The file data_cache.py contains some helper functions for getting (key, value) data into and out of Redis. The functions check_query_cache() and add_to_query_cache() are called upon user query of database. Returns a "Cache Hit" (with the data retrived from the cache) if the query exists in the cache, or a "Cache Miss" if the data does not exist in the cache. 
* social_graph:
** The file fan_comment_template.py contains a class with methods for creating and retrieving relationships and nodes from Neo4j.
The node types are: Fan, Player, Team, Comment.
*** The relationship types are:
**** APPEARED: A Player appeared for a Team.
**** FOLLOWS: One Fan FOLLOWS another Fan
**** SUPPORTS: A Fan SUPPORTS a Team
*** Comments:
A Fan may comment on a Team, Player or both.
COMMENT_BY: The relationship from the Fan to the Comment.
COMMENT_ON: The relationship from the Comment to the Player or Team.
A Fan may respond to a Comment. This create a relationship RESPONSE_BY  from the Fan to the new Comment, and RESPONSE_TO from the new Comment to the original Comment.
There are templates for the methods you will implement: create_comment(), create_sub_comment(), get_player_comments(), get_team_comments().
