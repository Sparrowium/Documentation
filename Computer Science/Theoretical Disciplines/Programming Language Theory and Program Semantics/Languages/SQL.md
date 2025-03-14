Structured Query Language
<h2><center> Basic </center></h2>
## Background

### Introduction to Databases

- [Database]: A database is a set of related information.
	
- [Database System]: A system of database that computerized data storage that has retrieval mechanisms. That has the ability to retrieve data quickly, index data in multiple ways, and deliver up-to-the-minute information to its user community.
	
- [Nonrelational Database Systems]:
	
	- [Hierarchical Database System]: Data is represented as one or more tree structures.
		![[Pasted image 20250212195724.png]]
	- [Network Database System]: Exposes sets of records and sets of links that define relationships between different records.
		![[Pasted image 20250212195842.png]]
	- [Multi-parent Hierarchy]: Nodes that can be accessed from multiple places.
	
- [Relational Model]: A model where data be represented as a sets of tables. Rather than using pointers to navigate between related entities, redundant data is used to link records in different tables.
	![[Pasted image 20250212200432.png]]
	- The number of columns that a table may contain differs from server to server, but it is generally large enough to not be an issue.
		
	- The number of rows that a table may contain is more a matter of physical limits and maintainability than of database server limitations.
		
	- Each table in a relational database includes information that uniquely identifies a row in that table (Primary Key), along with additional information needed to describe the entity completely.
		
	- [Compound Key]: 2 or more Primary Key in the same table.
		
	- [Foreign Key]: Are data that serve as a line connecting the entities in the hierarchical and network versions of the table information.
		
	- [Normalization]: The process of refining a database design to ensure that each independent piece of information is in only one place.
	
- [Common Terminology]:
	![[Pasted image 20250212201533.png]]

### What is SQL?

- **SEQUEL**, a Language used to manipulate data in relational databases, and other database technologies.
	
- SQL goes hand in hand with the relational model because the result of an SQL Query is a table (A result set). Thus, a new permanent table can be created in a relational database simply by storing the result set of a query. Similarly, the result set and permanent table can also be used as an input.
	
- It is called **SEQUEL**, Structured Query Language is just a categorization/definition, not the name of it, nor the expanded version of the abbreviation.
	
- [SQL Class Statement]: 
	
	- SQL is divided into several distinct parts:
		
		- [SQL Schema Statement]: Used to define the data structures stored in the database.
			
		- [SQL Data Statement]: Used to manipulate the data structures previously defined using SQL Schema Statements.
			
		- [SQL Transaction Statement]: Used to begin, end, roll back transactions.
		
	- [Data Dictionary]: Are data elements created via SQL Schema Statements that are stored in a special set of tables.
	
- [SQL: A Nonprocedural Language]: 
	
	- [Optimizer]: Decides the most efficient execution path based on table configurations and indexes.
		
	- [Optimizer Hint]: A pattern for optimizing.
		
	- Some database vendors have toolkit/API to integrate SQL into programming languages.
		![[Pasted image 20250212203351.png]]

### What is PostgreSQL?

- An Object-Relational database management system (ORDBMS).
	
- An open source that support a large part of the SQL standard and offers many modern features.
	`complex queries`
	`foreign keys`
	`triggers`
	`updatable views`
	`transactional integrity`
	`multiversion concurrency control`
	
- It can also extended by user in many ways, for example by adding new
	`data types`
	`functions`
	`operators`
	`aggregate functions`
	`index methods`
	`procedural languages`

### Third Party GUI for SQL

- [pgAdmin 4](https://www.pgadmin.org/docs/pgadmin4/9.1/index.html): A Open Source management tool for PostgreSQL. 

<h2 style="color:#6290C3"><center> Getting Started </center></h2>
## Installation 

- Refer to PostgreSQL Guidelines for [Installation](https://www.postgresql.org/docs/16/installation.html). Or follow the OS/Distros Guidelines for Installation, which in this documentation uses [Fedora Workstation](https://docs.fedoraproject.org/en-US/quick-docs/postgresql/).

## Architecture Fundamentals

- In database jargon, PostgreSQL uses a client/server model. A PostgreSQL session consists of the following cooperating processes:
	
	- [Server Process]: Manages the database files, accepts connections to the database from the client applications, and performs database actions on behalf of the clients. The database server program is called `postgres`.
		
	- [User's Client Application]: A front end application that wants to perform database operations. Client applications can be very diverse in nature: a client could be a text-oriented tool, a graphical application, a web server that accesses the database to display the web pages, or a specialized database maintenance tool. Some client applications are supplied with the PostgreSQL distributions.
	
- As is typical of client/server applications, the client and the server can be on different hosts. In that case they communicate over a TCP/IP network connection, therefore not all files can be accessed.
	
- The PostgreSQL server can handle multiple concurrent connections from clients. To achieve this it starts (“forks”) a new process for each connection. From that point on, the client and the new server process communicate without intervention by the original `postgres` process. Thus, the supervisor server process is always running, waiting for client connections, whereas client and associated server processes come and go.

## Creating and Populating a Database

- To create a database type: `createdb {name}`.
	
- To remove a database type: `dropdb {name}`.
	
- Once you have created a database you can access it by:
	
	- Running the PostgreSQL interactive terminal program, called `psql`, which allows you to interactively enter, edit, and execute SQL commands.
		
	- Using an existing graphical frontend tool like pgAdmin or an office suite with ODBC (Microsoft Open Database Connectivity) or JDBC (Java Database Connectivity) support to create and manipulate a database.
		
	- Writing a custom application, using one of the several available language bindings.
	
- To start up `psql` type: `psql mydb`. You will be greeted with:
	```
	psql (16.8)
	Type "help" for help.
	
	mydb=>
	```
	another instance would be in SuperUser mode `sudo`.
	```
	mydb=#
	```
	The last line printed out by `psql` is the prompt, and it indicates that `psql` is listening to you and that you can type SQL queries into a work space maintained by `psql`.
	
- In `psql` program there are internals commands that are not SQL commands. To list them type: `\h`.
	
- To quit `psql` type: `\q`.