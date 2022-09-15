# Database Standards Guidelines

- Create Database Custom Objects
- Database Custom Objects Naming Conventions

<br>

## Create Database Custom Objects

##### General Syntax 

> **{custom_schema}{separator}{app_short_name}{separator}[Optional {prefix}{separator}]{object_name}[Optional {separator}{suffix}]**

<br>

##### Syntax Elements
The **Syntax Elements** section that presents elements syntax and describes it.
 | SEQ | Element Syntax    | Element Name                  | Description |
 | :-: | :---              | :--                           | :--------   |
 | 1   | {custom_schema}   | Custom Database Schema        | Database custom ORACLE schema name |
 | 1   | {separator}       | Separator                     | Must use underscore “_” in database objects|
 | 1   | {app_short_name}  | Application/Product Short Name| This is the application/product short name |
 | 1   | {prefix}          | Prefix                        |  |
 | 1   | {object_name}     | Database Object Name          |  |
 | 1   | {suffix}          | Suffix                        |  |

<br>


### General Standards
- Never modify Oracle standard database objects.
- You must follow standard naming conventions for creating new database objects.
- You must create new tables, sequences, and types, in the custom schema.
- You must create new views and package objects in the APPS schema.
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
 13–NOV–2022 Ahmed Demasy Created
*/
```

<br>

## Oracle Applications Tables Standards

##### Syntax 

> {custom_schema}{separator}{app_short_name}{separator}[Optional {prefix}{separator}]{object_name}[Optional {separator}{suffix}]

<br>

### Table Naming Convention

 | SEQ  | Object Name         | Length | Schema | Prefix | Suffix | Example |
 | :-:  | :----               | :-:    | :--:   | :---   | :---   | :----   |
 | 1    | Table               | 20     | XXR    |        |        |  |
 | 2    | Temporary Table     | 20     | XXR    |        | \_tmp  |  |
 | 3    | Data Upload Table   | 20     | XXR    | tmp_   |        | For data upload and migrations ONLY | 
 
<br>

### Table Naming Standards

- The custom table name must start with a custom schema name such as "XXD". [^1]
- The object name “{object_name}“ should be plural.
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

##### References
[^1]: "**XXD**" is the custom database ORACLE schema association to the custom application called "Demasy Custom Applications".