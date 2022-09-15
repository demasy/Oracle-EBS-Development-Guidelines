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

