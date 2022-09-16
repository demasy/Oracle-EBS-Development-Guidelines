# Database Standards Guidelines

- **Create Database Custom Objects**
  - <a href="#general-standards">**General Standards**</a>
  - <a href="#tables-standards">**Tables Standards**</a>
  - <a href="#sequences-standards">**Sequences Standards**</a>
  - <a href="#views-standards">**Views Standards**</a>
  - <a href="#packages-standards">**Packages Standards**</a>
- Database Custom Objects Naming Conventions

<br>

## General Standards

- <a href="#general-syntax">**General Syntax**</a>
- <a href="#">**General Standards**</a>

<br>

### General Syntax


##### Syntax 

> {custom_schema}{separator}{app_short_name}{separator}[Optional {prefix}{separator}]{object_name}[Optional {separator}{suffix}]

<br>

##### Syntax Elements
The **Syntax Elements** section that presents elements syntax and describes it.
 | SEQ | Element Syntax      | Element Name                  | Description |
 | :-: | :---                | :--                           | :--------   |
 | 1   | *{custom_schema}*   | Custom Database Schema        | Database custom ORACLE schema name |
 | 2   | *{separator}*       | Separator                     | Must use underscore “_” in database objects|
 | 3   | *{app_short_name}*  | Application/Product Short Name| This is the application/product short name |
 | 4   | *{prefix}*          | Prefix                        |  |
 | 5   | *{object_name}*     | Database Object Name          |  |
 | 6   | *{suffix}*          | Suffix                        |  |

<br>

### General Standards

- Never modify Oracle standard database objects.
- The custom database objects must start with a **custom schema name** such as "XXD". [^1]
- You must follow standard naming conventions for creating new database objects.
- You must create new tables, sequences, and types, in the custom schema.
- You must create new views and package objects in the APPS schema.
- Never create new stand alone functions and procedures. shold be implemented as part of a package.
- You must use grants and synonyms to allow other ORACLE schemas to access your custom objects and to enable your custom ORACLE ID access to Oracle Applications objects.
- In general, make names meaningful and brief. Do not use generic, all-purpose phrases like ”COMMON”, ”MISC”, ”OTHER”, or ”UTILITY” in the name.
- Include header information when you create your objects.

<br>

###### Header Information

```SQL
/*
 Name: XXD Create GL Journals
 Purpose: This is the main package to create GL journals
 Arguments
  Arg1 Describe arg1
  Arg2 Describe arg2
 Notes
  1. Special usage notes
  2. Special usage notes
 History
 13–NOV–1986 Ahmed Demasy Created
*/
```

<br>

## Tables Standards

- <a href="#table-naming-syntax">**Table Naming Syntax**</a>
- <a href="#table-naming-convention">**Table Naming Convention**</a>
- <a href="#table-naming-standards">**Table Naming Standards**</a>
- <a href="#table-naming-example">**Table Naming Example**</a>

<br>

### Table Naming Syntax

##### Syntax 

> {custom_schema}{separator}{app_short_name}{separator}[Optional {prefix}{separator}]{object_name}[Optional {separator}{suffix}]

<br>

### Table Naming Convention

 | SEQ  | Object Name            | Length | Schema | Prefix | Suffix | Example |
 | :-:  | :----                  | :-:    | :--:   | :---   | :---   | :----   |
 | 1    | Table                  | 20     | XXD    |        |        | XXD_PO_LC_DOCUMENTS |
 | 2    | Temporary Table        | 20     | XXD    |        | \_TMP  | XXD_PO_LC_DOCS_TMP |
 | 3    | Data Upload Table [^2] | 20     | XXD    | TMP_   |        | XXD_TMP_LC_DOCS | 
 
<br>

### Table Naming Standards

- The custom table name must start with a custom schema name such as "**XXD**". [^2]
- The object name “*{object_name}*“ should be plural.
- The table name should be 20 characters or less. It can be longer, but you need to abbreviate it for the table handler package name, which must be 27 characters or less.
- You must place the new tables in the custom ORACLE schema and grant privileges to the APPS schema.
- You must create private synonyms for custom tables in APPS.
- You must add special WHO columns to your tables.
- You must add concurrent program WHO Columns to your table.
- You must create the table handler package for each table.
- New tables containing Flex-Fields or Oracle Alert columns must be registered with Oracle Application Object Library.
- You should register your custom tables with Oracle AOL using the table registration API called AD_DD.
  - AD_DD. REGISTER_TABLE
  - AD_DD. REGISTER_COLUMN

<br>

##### WHO columns

 | Column Name       | Type       | Null?    | Foreign Key? | Value | 
 | :--               | :----      | :-:      | :--          | :---   | 
 | CREATED_BY        | NUMBER(15) | NOT NULL | FND_USER     | TO_NUMBER (FND_ PROFILE.VALUE (’USER_ID’)) |
 | CREATION_DATE     | DATE       | NOT NULL |              | SYSDATE |
 | LAST_UPDATED_BY   | NUMBER(15) | NOT NULL |              | TO_NUMBER (FND_ PROFILE.VALUE (’USER_ID’)) | 
 | LAST_UPDATE_DATE  | DATE       | NOT NULL |              | SYSDATE |
 | LAST_UPDATE_LOGIN | NUMBER(15) |          |              | TO_NUMBER (FND_ PROFILE.VALUE (’LOGIN_ ID’)) |
 
<br>

##### Concurrent Program WHO Columns

 | Column Name             | Type       | Null? | Foreign Key to Table?   |  
 | :--                     | :----      | :-:   | :--                     | 
 | REQUEST_ID              | NUMBER(15) |       | FND_CONCURRENT_REQUESTS | 
 | PROGRAM_APPLICATION_ID  | NUMBER(15) |       | FND_CONCURRENT_PROGRAMS | 
 | PROGRAM_ID              | NUMBER(15) |       | FND_CONCURRENT_PROGRAMS | 
 | PROGRAM_UPDATE_DATE     | DATE       |       | ROGRAM_UPDATE_DATE      | 
 
<br>

### Table Naming Example

 | Better   | Bad        |
 | :---  | :---        |
 | - XXD_PO_LC_DOCUMENTS | - XXD_PO_LC_DOCUMENT <br> - PO_LC_DOCUMENTS       |

<br>

___

<br>

## Sequences Standards

- <a href="#sequence-naming-syntax">**Sequence Naming Syntax**</a>
- <a href="#sequence-naming-convention">**Sequence Naming Convention**</a>
- <a href="#sequence-naming-standards">**Sequence Naming Standards**</a>
- <a href="#sequence-naming-examples">**Sequence Naming Examples**</a>

<br>

### Sequence Naming Syntax

### Sequence Naming Convention

### Sequence Naming Standards
- The sequence name “*{object_name}*“ should be 30 characters or less and end with "_SEQ".
- Use each sequence to supply unique ID values for one column of one table.
- Do not design sequences that wrap using the CYCLE option or have limited ranges using MAXVALUE.
- Use a NUMBER datatype to store sequence values within PL/SQL.
- Do Not Use the FND_UNIQUE_IDENTIFIER_CONTROL Table.


### Sequence Naming Examples

___


<br>

## Views Standards


- <a href="#views-naming-syntax">**Views Naming Syntax**</a>
- <a href="#views-naming-convention">**Views Naming Convention**</a>
- <a href="#views-naming-standards">**Views Naming Standards**</a>
- <a href="#views-naming-examples">**Views Naming Examples**</a>

<br>

### Views Naming Syntax

### Views Naming Convention

### Views Naming Standards
- The view name “*{object_name}*“ should be 30 characters or less and end with "_V" for view and "_VM" for materialized views.
- The first column your view should select is the ROWID for the root table, and the view should alias it to ROW_ID.
- You only need to include the ROWID column if an Oracle Forms block is based on this view.


<br>

### Views Naming Examples

___

<br>

## Packages Standards


- <a href="#packages-naming-syntax">**Packages Naming Syntax**</a>
- <a href="#packages-naming-convention">**Packages Naming Convention**</a>
- <a href="#packages-naming-standards">**Packages Naming Standards**</a>
- <a href="#packages-naming-examples">**Packages Naming Examples**</a>

<br>

### Packages Naming Syntax

### Packages Naming Convention

### Packages Naming Standards

<br>

### Packages Naming Examples

___




<br>

##### References
[^1]: "**XXD**" is the custom database ORACLE schema association to the custom application called "Demasy Custom Applications".
[^2]: This is a custom table for data upload and migrations **only**.
