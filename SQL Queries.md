#1. List of all Table Names. 
Source/Ref:https://dataedo.com/kb/query/teradata/list-of-tables-in-the-database
```
SELECT  DatabaseName,
        TableName,
        CreateTimeStamp,
        LastAlterTimeStamp
FROM    DBC.TablesV
WHERE   TableKind = 'T'
and     DatabaseName = 'DBC'
ORDER BY    TableName;
```
