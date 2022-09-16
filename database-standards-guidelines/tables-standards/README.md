# Tables Standards

<br>

- <a href="#table-naming-syntax">**Table Naming Syntax**</a>
- <a href="#table-naming-convention">**Table Naming Convention**</a>
- <a href="#table-naming-standards">**Table Naming Standards**</a>
- <a href="#table-naming-examples">**Table Naming Examples**</a>

<br>

## Table Naming Syntax

##### Syntax 

> {custom_schema}{separator}{app_short_name}{separator}[Optional {prefix}{separator}]{object_name}[Optional {separator}{suffix}]

<br>

##### Syntax for data upload tables ONLY

> {prefix}{separator}{app_short_name}{separator}{object_name}



<br>

## Table Naming Convention

 | SEQ  | Object Name            | Length | Prefix | Suffix | Example |
 | :-:  | :----                  | :-:    | :---   | :---   | :----   |
 | 1    | Table                  | 20     |  -     | -      | XXD_PO_LC_DOCUMENTS |
 | 2    | Temporary Table        | 20     |  -     | TMP    | XXD_PO_LC_DOCS_TMP |
 | 3    | Data Upload Table [^1] | 20     | TMP    | -      | TMP_PO_LC_DOCS | 
 
<br>

## Table Naming Standards

- You MUST follow database custom objects <a href="https://github.com/demasy/Oracle-EBS-Development-Guidelines/tree/main/database-standards-guidelines">**general standards**</a>.
- The table name `{object_name}` should be plural.
- The table name `{object_name}` should be 20 characters or less. It can be longer, but you need to abbreviate it for the table handler package name, which must be 27 characters or less.
- You must place the new tables in the custom ORACLE schema, for example, "**XXD**", and grant privileges to the "**APPS**" schema.
- You must create private synonyms for custom tables in "**APPS**" schema.
- The table MUST include a primary key (PK) column and supply value from a specific sequence.
- You should add special WHO columns to your tables.
- You should add concurrent program WHO columns to your table.
- You should add descriptive flexfield (DFF) attribute columns to your table.
- New tables containing flexfield or Oracle Alert columns must be registered with Oracle Application Object Library (AOL).
- You should register your custom tables with Oracle AOL using the table registration API called "**AD_DD**".
  - `AD_DD.REGISTER_TABLE`
  - `AD_DD.REGISTER_COLUMN`

<br>

##### WHO columns

 | Column Name       | Type       | Null?    | Foreign Key? | Value | 
 | :--               | :----      | :-:      | :--          | :---   | 
 | CREATED_BY        | NUMBER(15) | NOT NULL | FND_USER     | TO_NUMBER (FND_ PROFILE.VALUE (’USER_ID’)) |
 | CREATION_DATE     | DATE       | NOT NULL |              | SYSDATE |
 | LAST_UPDATED_BY   | NUMBER(15) | NOT NULL | FND_USER     | TO_NUMBER (FND_ PROFILE.VALUE (’USER_ID’)) | 
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

## Table Naming Examples

 | Better   | Bad        |
 | :---  | :---        |
 | - `XXD_PO_LC_DOCUMENTS` | - `XXD_PO_LC_DOCUMENT` <br> - `PO_LC_DOCUMENTS`       |

<br>

##### References
[^1]: This is a custom table for data upload and migrations **ONLY** and should drop these tables after the upload data process finish.
