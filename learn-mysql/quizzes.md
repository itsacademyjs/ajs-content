1. Which type of database management system is MySQL?
a) Object-oriented
b) Hierarchical
c) Relational
d) Network


2. What is data in a MySQL database organized into?
a) Objects
b) Tables
c) Networks
d) File systems


3. MySQL is freely available and is open source.
a) True
b) False


1. What represents an ‘attribute’ in a relational database?
a) Table
b) Row
c) Column
d) Object


5. What represents a ‘tuple’ in a relational database?
a) Table
b) Row
c) Column
d) Object


6. How is communication established with MySQL?
a) SQL
b) Network calls
c) A programming language like C++
d) APIs


7. What does ‘name’ represent in the following SQL code snippet?

   CREATE TABLE student
   (
       name CHAR(30),
       roll_num INT,
       address CHAR(30),
       phone CHAR(12)
   );
a) A table
b) A row
c) A column
d) An object


8. Which is the MySQL instance responsible for data processing?
a) MySQL client
b) MySQL server
c) SQL
d) Server daemon program


9. The MySQL server used in its client/server architecture is _______________
a) mysqla
b) mysqlb
c) mysqlc
d) mysqld


10. In MySQL databases, the structure representing the organizational views of the entire databases is ____________
a) Schema
b) View
c) Instance
d) Table




---


1. Which of the following characters is illegal in naming an unquoted identifier in SQL?
a) _
b) $
c) 2
d) .


2. In MySQL, identifier names can start with a digit.
a) True
b) False


3. How are identifiers quoted in MySQL?
a) single quotes
b) double quotes
c) backticks
d) can’t be quoted




4. Which of the following is an illegal unquoted identifier name?
a) 123_id
b) 123id
c) id1
d) 123


5. Which server mode value enables use of double quotes to wrap identifier names?
a) ANSI
b) ANSI_QUOTES
c) TRADITIONAL
d) PIPES_AS_CONCAT


6. Which server mode value disables use of built in function names as identifiers?
a) ANSI
b) IGNORE_FUNC
c) TRADITIONAL
d) IGNORE_SPACE


7. What is the maximum length for alias names in terms of characters?
a) 64
b) 128
c) 256
d) 32


8. What does a fully qualified table name consist of?
a) only the table name
b) only the database name
c) table name followed by database name
d) database name followed by table name


9. If no database has been selected, specifying a database qualifier is necessary.
a) True
b) False


10. Which of the following MySQL statements is valid if ‘`sampledb`’ is a database and ‘`tbl`’ is a table in it?
a) SELECT * FROM `sampledb.member`
b) SELECT * FROM `sampledb`.`member`
c) SELECT * FROM `member`.`sampledb`
d) SELECT * FROM `member.sampledb`

---

1. Which of these is also known as a virtual table?
a) SCHEMA
b) DATABASE
c) JOIN
d) VIEW


2. A View can be used to select a subset of the table columns.
a) True
b) False


3. What is xyz in the following MySQL statement?

CREATE VIEW xyz AS SELECT a, b FROM t;
a) table
b) column
c) view
d) database


4. What is abc in the following MySQL statement?

CREATE VIEW xyz (abc) AS SELECT a FROM t;
a) row name
b) column name
c) view
d) database


5. A view can refer to multiple tables via __________
a) UNION
b) JOIN
c) GROUP
d) SELECT


6. Views are not updatable.
a) True
b) False


7. A view can be deleted using the command __________
a) REMOVE
b) DELETE
c) CLEAR
d) DROP


8. What cannot be done on a view?
a) display
b) filter
c) index
d) drop


9. What can be used to check for views that have been invalidated by DROP or ALTER operations?
a) CREATE TABLE
b) VERIFY TABLE
c) DETAILS TABLE
d) CHECK TABLE


10. Which of the following does not support a materialized view?
a) MySQL
b) Oracle
c) PostgreSQL
d) SybaseSQL

---

1. To perform a delete on a single-table, how is the name of a column qualified?
a) qualification not necessary
b) column name
c) table name
d) database name


2. What is xyz in the following SQL statement?

	DELETE FROM xyz WHERE abc = 5;
a) column name
b) table name
c) row name
d) database name




3. A multiple-table delete can apply any join.
a) True
b) False


4. What is abc in the following SQL statement?

	DELETE FROM xyz WHERE abc = 5;
a) column name
b) table name
c) row name
d) database name


5. What is x in the following MySQL statement?

	DELETE FROM x USING x LEFT JOIN y ON x.col = y.col;
a) column name
b) table name
c) server name
d) database name


6. Qualifying the name of column with the table name is not necessary in single-table updates.
a) True
b) False


7. What is the value of val2 in the following MySQL statement?

	UPDATE t SET val1 = val1 + 2, val2 = val1;
a) previous val1
b) updated val1
c) unchanged
d) val1 + 1


8. UPDATE statement is a DML statement. What does DML stand for?
a) Data Manipulation Language
b) Data Manipulation Level
c) Data Markup Language
d) Data Markup Level


9. Which keyword in the UPDATE statement is used to assign values to columns?
a) ASSIGN
b) SET
c) MARK
d) GET


10. Which keyword is used to delete all the rows from the table?
a) TRUNCATE
b) REMOVE
c) DELETE ALL
d) CLEAR

---

1. What is known as the set of SQL statements that either executes successfully or none of them have an effect?
a) joins
b) transactions
c) filters
d) deletions


2. What is generally done after the transactions are executed successfully?
a) delete
b) rollback
c) commit
d) update


3. What is generally done if an error occurs during the transaction?
a) delete
b) rollback
c) commit
d) update


4. What does ‘A’ stand for in the ACID property of transactions?
a) Availability
b) Accuracy
c) Adjustability
d) Atomicity


5. What does ‘C’ stand for in the ACID property of transactions?
a) Compound
b) Concrete
c) Collision
d) Consistency


5. What is the isolation property of transactions?
a) statements form a logic unit
b) database remains consistent
c) one transaction does not affect the other
d) transaction effects are recorded permanently


6. What is the command to disable autocommit and launch a transaction?
a) INITIATE TRANSACTION
b) START TRANSACTION
c) DISABLE AUTOCOMMIT
d) TRANSACTION


7. Transactional processing provides strong guarantees about the outcome of operations.
a) True
b) False

8. Transactional processing requires lesser overhead due to CPU cycles and memory.
a) True
b) False

9. What is the durability property of transactions?
a) statements form a logic unit
b) database remains consistent
c) one transaction does not affect the other
d) transaction effects are recorded permanently

10. How many storage engines among the following are transaction-safe?

InnoDB, Falcon, MyISAM, MEMORY
a) 1
b) 2
c) 3
d) 4

---


1. Which key declares that an index in one table is related to that in another?
a) primary
b) secondary
c) foreign
d) cross


2. Foreign keys cannot handle deletes and updates.
a) True
b) False


3. Deletion of an employee from table also deletes that employee from another table. This kind of delete is called ____________
a) transparent
b) concrete
c) elaborate
d) cascaded




4. Which storage engine in MySQL provides foreign key support?
a) TRANSACTION
b) InnoDB
c) MyISAM
d) MEMORY


5. The property of InnoDB that enforces foreign key relationships stay intact is called _____________
a) atomicity
b) durability
c) consistency
d) referential integrity


6. Which clause names the parent table and the index columns in the table?
a) REFERENCES
b) ON DELETE
c) CONSTRAINT
d) FOREIGN KEY


7. If the storage engine InnoDB is not used, foreign key cannot be used.
a) True
b) False


8. Which clause is used to remove a foreign key constraint?
a) REMOVE
b) DELETE
c) DROP
d) EXCLUDE


9. Which keyword is used to specify the foreign key after the table is created?
a) SETUP
b) SET
c) ALTER TABLE
d) SPECIFY


10. Which clause in the SQL standard controls how NULL values in a composite foreign key are handled when comparing to a primary key.
a) SET
b) MATCH
c) ON DELETE
d) ON CASCADE

---

1. In which mode of search is the search string parsed into words and the search looks for rows?
a) Natural language
b) Boolean mode
c) Query expansion
d) Cross mode


2. The indicator of presence or absence of a word in search is used in which mode?
a) Natural language
b) Boolean mode
c) Query expansion
d) Cross mode


3. Which search mode uses natural language search as a subroutine?
a) Natural language
b) Boolean mode
c) Query expansion
d) Cross mode

4. FULLTEXT indexes can be created only for ____________
a) MyISAM
b) InnoDB
c) MEMORY
d) TRANSITION


5. A FULLTEXT index cannot be created for multiple columns.
a) True
b) False


6. Which keyword is used to search through natural language fulltext?
a) MATCH
b) AGAINST
c) SEARCH
d) FIND


7. What is xyz in the following MySQL statement?

	SELECT * FROM my_table WHERE MATCH(abc) AGAINST('xyz');
a) column name
b) table name
c) search string
d) database name


8. What is abc in the following MySQL statement?

	SELECT * FROM my_table WHERE MATCH(abc) AGAINST('xyz');
a) column name
b) table name
c) search string
d) database name


9. In Boolean search, results are sorted by relevance.
a) True
b) False

10. Which parameter determines the shortest words to index in FULLTEXT indexes?
a) ft_min_word_len
b) ft_min_len_word
c) ft_word_min_len
d) ft_word_len_word

---

1. SELECT select_list FROM table_list WHERE row_constraint GROUP BY grouping_columns; Which of these is not optional?
a) select_list
b) table_list
c) row_constraint
d) grouping_columns


2. In inner join, result is produced by matching rows in one table with rows in another table.
a) True
b) False


3. The join where all possible row combinations are produced is called _________
a) INNER JOIN
b) OUTER
c) NATURAL
d) CARTESIAN




4. The clause that filters JOIN results is called _________
a) WHERE
b) SORT
c) GROUP
d) GROUP BY


5. CROSS JOIN and JOIN are similar to __________
a) INNER JOIN
b) NATURAL JOIN
c) OUTER JOIN
d) CARTESIAN JOIN


6. The comma operator can also be used to join tables.
a) True
b) False


7. The left and right joins are also known as __________
a) INNER JOIN
b) NATURAL JOIN
c) OUTER JOIN
d) CARTESIAN JOIN


8. What is joining a table to itself called?
a) COMPLETE
b) SELF
c) OBSOLETE
d) CROSS


9. In which join all the rows from the left table appear in the output irrespective of the content of the other table?
a) RIGHT JOIN
b) LEFT JOIN
c) INNER JOIN
d) OUTER JOIN


10. The join in which all the rows from the right table appear in the output irrespective of the content of the other table is ___________
a) CARTESIAN JOIN
b) CROSS JOIN
c) INNER JOIN
d) RIGHT JOIN

---


1. The facility that allows nesting one select statement into another is called __________
a) nesting
b) binding
c) subquerying
d) encapsulating


2. Which subquery returns a single value?
a) scalar
b) column
c) row
d) table


3. Usage of aggregates in WHERE clause is allowed.
a) True
b) False


---

1. Which operators are used when a subquery returns multiple rows to be evaluated in comparison to the outer query?
a) IN and NOT IN
b) EXISTS and NOT EXISTS
c) OUTER JOIN and INNER JOIN
d) LEFT JOIN and RIGHT JOIN


5. The ALL subquery performs which operation?
a) row
b) column
c) table
d) database


6. Which of these operators perform similar operations like ALL and ANY?
a) SOME
b) MANY
c) SELECT
d) GROUP


7. Which operators test whether a subquery returns any rows?
a) IN and NOT IN
b) EXISTS and NOT EXISTS
c) PRESENT
d) ABSENT


8. An uncorrelated subquery does not contain any reference to the values from the outer query.
a) True
b) False


9. Which subquery cannot be executed by itself as a separate statement?
a) Correlated
b) Uncorrelated
c) EXISTS
d) NOT EXISTS


10. Which of these operators does not perform relative-value comparisons?
a) =
b) ==
c) <=
d) >=
