---
layout: post
title:  "What I Learnt Today - DataBricks SSQL Querying Files"
date:   2020-03-11 09:00:00 +0000
categories: updates databricks
---
## DataBricks
Notes from the SSQL-02 training module

To run an SQL command in a DataBricks notebook cell, add the `%sql` decorator. For example:
```
%sql
SELECT * FROM People10M
```
The results are then displayed in an HTML table in the cell.

To describe the table People10M run:
```
%sql
DESCRIBE People10M
```

### Creating new features from an SQL table
To create a new column or feature in the result set (akin to creating a new column in a Panda's Dataframe) 
use the `as` function just as you would in normal SQL
```
%sql
SELECT firstname, middleName, lastName, year(birthDate) AS birthYear
FROM People10M
WHERE year(birthdate) > 1990
```

### Temporary Views
Just like SQL, Spark SQL allows temporary views to be created for the duration of your Spark Session. 
These are not persisted when the cluster is restarted, or switch to a new notebook

```
%sql
CREATE OR REPLACE TEMPOARY VIEW TheDonnas AS
  SELECT *
  FROM People10M
  WEHRE firstName = 'Donna'
```

This can then be queried using normal `select` command:
```
%sql
SELECT * from TheDonnas
```
