# Updating, Deleting, and Copying Records in SQL
Here I create a database and table for a football stickers collection. I update and delete records, and I copy into new tables.
 
Part A:
• First, I write a T-SQL statement that creates a database called Football_Stickers_Collection.

CREATE DATABASE Football_Stickers_Collection;
 
![image.png](attachment:3f0f7a03-1f57-48dc-84c9-a8c14510e094.png)

Part B:
• I then write a T-SQL statement that creates a table called Football_Stickers, using the data in the following table and I specify appropriate data types for  the columns in the table and a primary key:

CREATE TABLE Football_Stickers (
ID int PRIMARY KEY,
FirstName varchar(30),
LastName varchar(30),
Country varchar(80),
[No. of Caps won] int
);
 
![image.png](attachment:7f3ccba3-971b-4b80-adf1-24de455c9b5f.png) 

INSERT INTO Football_Stickers (ID, FirstName, LastName, Country, [No. of Caps won])
VALUES
(1, 'Michel', 'Platini', 'France', 86),
(2, 'Diego', 'Maradona', 'Argentina', 76),
(3, 'Jordi', 'Cruyff', 'Netherlands', 12),
(4, 'Ossie', 'Ardiles', 'Argentina', 48),
(5, 'Paul', 'McGrath', 'Republic of Ireland', 76),
(6, 'John', 'Giles', 'Republic of Ireland', 60),
(7, 'Pele', NULL, 'Brazil', 89),
(8, 'Zinedine', 'Zidane', 'France', 76),
(9, 'Liam', 'Brady', 'Republic of Ireland', 88),
(10, 'Leo', 'Messi', 'Argentina', 95),
(11, 'Craig', 'Bellamy', 'Wales', 10),
(12, 'George', 'Best', 'Northern Ireland', 56),
(13, 'Norman', 'Whiteside', 'Northern Ireland', 30)
 
![image.png](attachment:49853fb0-603f-4b84-8f45-3faf5893b39f.png)

Part C:
• I write a T-SQL statement that updates the record with an ID value of 3, so that the first name field has the value, Johan.

UPDATE Football_Stickers
SET FirstName = 'Johan'
WHERE ID = 3
 
![image.png](attachment:794e948a-3fbd-4a85-9885-6627b3f0029c.png) 


Part D:
• I write a T-SQL statement that deletes the record from the table, which has a value for ID of 11.

DELETE FROM Football_Stickers
WHERE ID = 11
 
![image.png](attachment:48faef5e-3de7-430c-a1ea-1f84ee77a925.png)

Part E:
• I write a T-SQL statement that deletes records from the table where the value for the Country field is Northern Ireland.

DELETE FROM Football_Stickers
WHERE Country = 'Northern Ireland'
 
![image.png](attachment:79639d83-4492-4dea-b747-cc9add998ceb.png)


Part F:
• I write a T-SQL statement that inserts the following records into the table:
ID FirstName LastName Country No. of Caps won
11 Emilio Butragueno Spain 67
12 Hugo Sanchez Mexico 78

INSERT INTO Football_Stickers
(ID, FirstName, LastName, Country, [No. of Caps won])
VALUES
(11, 'Emilio', 'Butragueno', 'Spain', 67),
(12, 'Hugo', 'Sanchez', 'Mexico', 78)
 
![image.png](attachment:fcde73f0-1d88-4185-9c0a-6b3c88ac7619.png)

Part G:
• I write a T-SQL statement that copies all records from the Football_Stickers table and inserts them into another table called Football_Stickers_Reserves. I assume that the table Football_Stickers_Reserves does not exist, making sure to create the table in advance of copying the records over.

CREATE TABLE Football_Stickers_Reserves (
ID int PRIMARY KEY,
FirstName varchar(30),
LastName varchar(30),
Country varchar(80),
[No. of Caps won] int
);
 
INSERT INTO Football_Stickers_Reserves
SELECT * FROM Football_Stickers;
 
![image.png](attachment:9094edc5-1052-4091-b786-e83c32689216.png) 

Part H:
• Finally ,I wite a T-SQL statement that copies records from the Football_Stickers table, where the value for the Country field is Republic of Ireland, into another table called Irish_Football_Legends. I assume that the table, Irish_Football_Legends does not exist. I do not create the Irish_Football_Legends table first, and write a T-SQL statement in which the table will be automatically created as part of the process of copying the records over.

SELECT * INTO Irish_Football_Legends 
FROM Football_Stickers 
WHERE Country = 'Republic of Ireland'
 
![image.png](attachment:a88152b5-94ce-47e2-9453-81912049ef02.png) 

 

