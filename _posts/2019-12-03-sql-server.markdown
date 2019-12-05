---
layout: post
title:  "SQL Server"
date:   2019-12-03 10:00:00 -0300
categories:  dev sql
author: eric0liveira
comments: true
---

# SQL Server

## Database

### Create Database

```sql
CREATE DATABASE database_name
ON ( NAME = SUCO_VENDAS_DAT,  
    FILENAME = 'C:\TEMP\DATA\DataBaseName.mdf',  
    SIZE = 10,  
    MAXSIZE = 50,  
    FILEGROWTH = 5 )  
LOG ON  
( NAME = SUCOS_VENDAS_LOG,  
    FILENAME = 'C:\TEMP\DATA\DataBaseName.ldf',  
    SIZE = 5MB,  
    MAXSIZE = 25MB,  
    FILEGROWTH = 5MB )
```

### Delete DataBase

```sql
DROP DATABASE database_name 
```

## Data Types

### Exact numerics

|Data type|Range|Storage|  
|---|---|---|
|**bigint**|-2^63 (-9,223,372,036,854,775,808) to 2^63-1 (9,223,372,036,854,775,807)|8 Bytes|  
|**int**|-2^31 (-2,147,483,648) to 2^31-1 (2,147,483,647)|4 Bytes|  
|**smallint**|-2^15 (-32,768) to 2^15-1 (32,767)|2 Bytes|  
|**tinyint**|0 to 255|1 Byte|
|**money**|-922,337,203,685,477.5808 to 922,337,203,685,477.5807 (-922,337,203,685,477.58 to 922,337,203,685,477.58 for Informatica.  Informatica only supports two decimals, not four.)|8 bytes|
|**smallmoney**|- 214,748.3648 to 214,748.3647|4 bytes|

|Data type|Description|
|---|---|
|**numeric**| Decimal with precision and fixed scales. This accuracy ranges from 1 to 38 decimal entries. The field size depends on the number of decimal places (from 5 to 17 bytes).|
|**decimal**| Numeric data types that have fixed precision and scale. Decimal and numeric are synonyms and can be used interchangeably.|
|**bit**| An integer data type that can take a value of 1, 0, or NULL.|

### Approximate numerics

|Data type|Range|Storage|  
|---|---|---|
|**float**|- 1.79E+308 to -2.23E-308, 0 and 2.23E-308 to 1.79E+308|Depends on the value of *n*|  
|**real**|- 3.40E + 38 to -1.18E - 38, 0 and 1.18E - 38 to 3.40E + 38|4 Bytes|

### Date and time

|Data type|Default string literal format|Output|
| --- | --- | --- | 
|**time**|hh:mm:ss[.nnnnnnn]| 12:35:29. 1234567|
|**date**|YYYY-MM-DD| 2007-05-08|
|**datetime**|YYYY-MM-DD hh:mm:ss[.nnn]| 2007-05-08 12:35:29. 123|
|**datetime2**|YYYY-MM-DD hh:mm:ss[.nnnnnnn]| 2007-05-08 12:35:29. 1234567|
|**datetimeoffset**|YYYY-MM-DD hh:mm:ss[.nnnnnnn] [+&#124;-]hh:mm| 2007-05-08 12:35:29.1234567 +12:15|
|**smalldatetime**|YYYY-MM-DD hh:mm:ss| 2007-05-08 12:35:00|

### Character strings

|Data type|Description|
|---|---|
|**char**|Fixed-size string data. n defines the string size in bytes and must be a value from 1 through 8000|
|**varchar**| Variable-size string data. Use n to define the string size in bytes and can be a value from 1 through 8000 or use max to indicate a column constraint size up to a maximum storage of 2^31-1 bytes (2 GB)|
|**text**|Variable-length non-Unicode data in the code page of the server and with a maximum string length of 2^31-1 (2,147,483,647)|

### Unicode character strings

|Data type|Description|
|---|---|
|**nchar**|Fixed-size string data. n defines the string size in byte-pairs and must be a value from 1 through 4000|
|**nvarchar**|Variable-size string data. n defines the string size in byte-pairs and can be a value from 1 through 4000|
|**ntext**|Variable-length Unicode data with a maximum string length of 2^30 - 1 (1,073,741,823) bytes|

### Binary strings

|Data type|Description|
|---|---|
|**binary**|Fixed-length binary data with a length of n bytes, where n is a value from 1 through 8000|
|**varbinary**|Variable-length binary data. n can be a value from 1 through 8,000. max indicates that the maximum storage size is 2^31-1 bytes.|
|**image**|Variable-length binary data from 0 through 2^31-1 (2,147,483,647) bytes.|

## Table

### Create Table

```sql
CREATE TABLE
    { database_name.schema_name.table_name. | schema_name.table_name | table_name }
    ( { <column_definition> } [ ,...n ] )
[ ; ]
```

### Delete Table

```sql
DROP TABLE table_name 
```
