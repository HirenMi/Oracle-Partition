# Oracle-Partition
All about [**oracle**](https://oracle.com) partitioning *schemes* along with code

Enterprises _are_ motivated by __the support__ and maintenance requirements of very large databases (VLDB). Partitioning is a key component of the VLDB strategy. Partitioning addresses key issues in supporting very large tables and indexes by decomposing them into smaller and more manageable pieces called partitions, which are entirely transparent to an application. Thus, SQL queries and Data Manipulation Language (DML) statements or application code do not need to be modified to access partitioned tables. Partitioning has improved significantly with Oracle Database 12c Release 2.
Oracle Partitioning, an option of Oracle Database Enterprise Edition, enhances the SPAM (Scalability, Performance, Availability, and Manageability) of a wide variety of applications.
Partitioning applies divide and conquer technique for managing the tables and indexes in the database. Partitioning enables administration of an object either collectively or individually.
Using Partitioning, OLTP systems often benefit from improvements in manageability and availability, while DWH systems benefit from performance and manageability.
Partitioning allows Tables, Materialized Views, Indexes MViews, and Index-organized tables (IOT) only. Oracle provides a rich variety of partitioning strategies and extensions to address every business requirement.
Each partition of a table or index must have the same logical attributes, such as column names, data types, and constraints, but each partition can have separate physical attributes, such as compression enabled or disabled, physical storage settings, and tablespaces. Each partition has its own name, and may optionally have its own storage characteristics.
Note: All partitions of a partitioned object must reside in tablespaces of the same block size.
Any table can be partitioned up to total of 1024K-1 partitions and subpartitions. 
Sub-partition: Partitions created within partitions. There is nothing special about them.
The partitioning key consists of one or more columns that determine the partition where each row is stored. Each row in a partitioned table is unambiguously assigned to a single partition. Oracle automatically directs insert, update, and delete operations to the appropriate partition using the partitioning key.
The partition key is a set of from 1 to 16 columns that determines the partition for each row. Cannot contain a LEVEL, ROWID or MLSLABEL pseudo column or a column of type ROWID.
The partition key is a set of from 1 to 16 columns that determines the partition for each row. Cannot contain a LEVEL, ROWID or MLSLABEL pseudo column or a column of type ROWID.
The following DML statements contain an optional partition specification for non-remote partitioned tables:
	INSERT	  	UPDATE		  DELETE		  LOCK TABLE	  SELECT
A VIEW can be created which selects from just one partition using the partition-extended table name, and this view can be used in lieu of a table. With such views you can also build partition-level access control mechanisms by granting (revoking) privileges on these views to (from) other users or roles.
The database generated names for partitions includes format SYS_Pn. LOB data partitions take the form SYS_LOB_Pn and LOB index partitions take the form SYS_IL_Pn. The database generated names for sub-partitions includes format SYS_SUBPn. LOB data subpartitions take the form SYS_LOB_SUBPn and LOB index partitions take the form SYS_IL_SUBPn. 

The database evaluates tablespace storage in the following order of descending priority:
Tablespace storage specified at the individual table subpartition or LOB subpartition level has the highest priority, followed by storage specified for the partition or LOB in the subpartition_template.
Tablespace storage specified at the individual table partition or LOB partition level. Storage parameters specified here take precedence over the subpartition_template.
Tablespace storage specified for the table
Default tablespace storage specified for the user 

_This will also be italic_
__This will also be italic__
