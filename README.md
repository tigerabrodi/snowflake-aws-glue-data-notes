# Data Warehousing

## Facts and Dimensions

A fact table is like a central hub in the database that keeps track of all the important actions and their keys to places containing more information about the specific key.

That place is called a dimension table. A dimension table is a table that contains information about the keys in the fact table.

So a fact table contains both foreign keys and core quantitative data that's commonly desired, also called measures.

## Star Schema

A star schema is a way of organizing the fact and dimension tables in a way that optimizes the data retrieval process. You will have one fact table in the center, and dimension tables surrounding it like a star.

## Snowflake Schema

A snowflake schema is a more complex type of data warehouse schema that is a variation of the star schema. It is called snowflake because its diagram resembles a Snowflake. The fact table is surrounded by dimension tables, which are in turn surrounded by sub-dimension tables.

It is more complex than a star schema and requires more foreign key joins to fetch the data.
