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
