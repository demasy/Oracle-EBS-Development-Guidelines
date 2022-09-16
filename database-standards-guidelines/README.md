# Database Standards Guidelines

- <a href="#general-syntax">**General Syntax**</a>
- <a href="#general-standards">**General Standards**</a>

<br>

## General Syntax

> {custom_schema}{separator}{app_short_name}{separator}[Optional {prefix}{separator}]{object_name}[Optional {separator}{suffix}]

<br>

#### Syntax Elements
  
 | SEQ | Element Syntax      | Element Name                  | Description |
 | :-: | :---                | :--                           | :--------   |
 | 1   | *{custom_schema}*   | Custom Database Schema        | Database custom ORACLE schema name |
 | 2   | *{separator}*       | Separator                     | Must use underscore “_” in database objects|
 | 3   | *{app_short_name}*  | Application/Product Short Name| This is the application/product short name |
 | 4   | *{prefix}*          | Prefix                        |  |
 | 5   | *{object_name}*     | Database Object Name          |  |
 | 6   | *{suffix}*          | Suffix                        |  |


<br>



## General Standards

- NEVER modify Oracle standard database objects.
- You must follow standard naming conventions for creating new database objects.
- The database object name `{object_name}` must be meaningful and brief.
- Do not use generic, all-purpose phrases like ”COMMON”, ”MISC”, ”OTHER”, or ”UTILITY” in the database object name `{object_name}`.
- The application/product short name `{app_short_name}` is a foreign key from Oracle standard table called "FND_APPLICATIONS".
- The custom database objects must start with a custom database schema name for example "**XXD**". [^1]
- You must create new database tables, sequences, and types, in the custom schema.
- You must create new database views and packages in the APPS schema.
- Never create new stand-alone functions and procedures. Should be implemented as part of a package.
- You must use grants and synonyms to allow other ORACLE schemas to access your custom objects and to enable your custom ORACLE ID access to Oracle Applications objects.
- Include header information when you create your objects.

<br>

###### Header Information

```SQL
/*
 Name: Create & Post GL Journals
 Purpose: This is the main package to create & post GL journals
 Arguments
  Arg1 Describe arg1
  Arg2 Describe arg2
 Notes
  1. Special usage notes
  2. Special usage notes
 History
 13–NOV–1986 Ahmed El-Demasy Created
*/
```
<br>

## Database Custom Objects Standards by Type
- **Database Custom Objects Standards**
  - <a href="https://github.com/demasy/Oracle-EBS-Development-Guidelines/tree/main/database-standards-guidelines/tables-standards">**Tables Standards**</a>
  - <a href="https://github.com/demasy/Oracle-EBS-Development-Guidelines/tree/main/database-standards-guidelines/sequences-standards">**Sequences Standards**</a>
  - <a href="https://github.com/demasy/Oracle-EBS-Development-Guidelines/tree/main/database-standards-guidelines/views-standards">**Views Standards**</a>
  - <a href="https://github.com/demasy/Oracle-EBS-Development-Guidelines/tree/main/database-standards-guidelines/packages-standards">**Packages Standards**</a>
- <a href="https://github.com/demasy/Oracle-EBS-Development-Guidelines/tree/main/database-standards-guidelines/plsql-coding-standards">**Oracle PL/SQL Coding Standards**</a>


<br>

##### References
[^1]: "**XXD**" is the custom database ORACLE schema association to my custom application called "Demasy Custom Applications".
[^2]: This is a custom table for data upload and migrations **ONLY** and should drop these tables after the upload data process finish.
