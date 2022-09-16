# Database Standards Guidelines

- **Database Custom Objects Standards**
  - <a href="#general-standards">**General Standards**</a>
  - <a href="#tables-standards">**Tables Standards**</a>
  - <a href="#sequences-standards">**Sequences Standards**</a>
  - <a href="#views-standards">**Views Standards**</a>
  - <a href="#packages-standards">**Packages Standards**</a>
- Oracle PL/SQL Coding Standards
- Appendix: Database Custom Objects Naming Conventions

<br>

## General Standards

- <a href="#general-syntax">**General Syntax**</a>
- <a href="#">**General Standards**</a>

<br>

### General Syntax


##### Syntax 

> {custom_schema}{separator}{app_short_name}{separator}[Optional {prefix}{separator}]{object_name}[Optional {separator}{suffix}]

<br>

### General Standards

- NEVER modify Oracle standard database objects.
- You must follow standard naming conventions for creating new database objects.
- The database object name `{object_name}` must be meaningful and brief.
- Do not use generic, all-purpose phrases like ”COMMON”, ”MISC”, ”OTHER”, or ”UTILITY” in the database objet name "*{object_name}*".
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

## Sequences Standards

- <a href="#sequence-naming-syntax">**Sequence Naming Syntax**</a>
- <a href="#sequence-naming-convention">**Sequence Naming Convention**</a>
- <a href="#sequence-naming-standards">**Sequence Naming Standards**</a>
- <a href="#sequence-naming-examples">**Sequence Naming Examples**</a>

<br>

### Sequence Naming Syntax

### Sequence Naming Convention

### Sequence Naming Standards
- The sequence name `{object_name}` should be 30 characters or less and end with `_SEQ`.
- You must place the new sequence in the custom ORACLE schema, for example, "**XXD**", and grant privileges to the APPS schema.
- Use each sequence to supply unique ID values for one column of one table.
- Do not design sequences that wrap using the CYCLE option or have limited ranges using MAXVALUE.
- Use a NUMBER datatype to store sequence values within PL/SQL.
- Do Not Use the FND_UNIQUE_IDENTIFIER_CONTROL Table.

<br>

### Sequence Naming Examples

<br>

___


<br>

## Oracle PL/SQL Coding Standards

<br>

### Syntax 

> {scope}{prefix}{separator}{identifier_name}{separator}{suffix}

<br>

### PL/SQL Objects Naming Convention

 | SEQ | Object Name       | Length | scope | Prefix | Suffix | Example           |
 | :-  | :----             | :-:    | :--   | :---   | :--    | :----             |
 | 1   | **Variables**     |        |       |        |        |                  |
 | 1.1 | Global Variable   |        | g     |    _   |        | g_enterprise_id   | 
 | 1.2 | Local Variable    |        | l     |    _   |        | l_customer_id     | 
 | 2   | **Constants**     |        |       |        |       |                  |
 | 2.1 | Global Constants  |        | g     |  c     |        | gc_max_discount   | 
 | 2.2 | Local Constants   |        | l     |  c     |        | lc_max_discount   | 
 | 3   | **Parameters**    |  -     |       |  -     |  -     |    -              |
 | 3.1 | Cursor Parameters |        |       | p      |        | p_customer        |
 | 3.2 | In Parameters     |        |       | p      |        | p_customer_id     | 
 | 3.3 | Out Parameters    |        |       | x      |        | x_customer_id     | 
 | 3.4 | In/Out Parameters |        |       | px     |        | px_customer_id    | 
 | 4   | **Other Objects** |  -     |       |   -    |   -    |     -             | 
 | 4.1 | Cursors           |        |       | cur    |        | cur_customers     |
 | 4.2 | Record            |        |       | r      |  type  | r_customer_type   | 
 | 4.3 | Array / Table     |        |       | t      |  type  | t_customers_type  |    
 | 4.4 | Objects           |        |       | o      |  type  | o_customers_type  |
 | 4.5 | Exceptions        |        |       | e      |        | e_customer_exists |
 | 4.6 | Exception Number  |        |       | en     |        | en_customer_exists|
 
 
<br>

### PL/SQL Objects Naming Standards

<br>

### PL/SQL Objects Coding Standards
- 

<br>

##### References
[^1]: "**XXD**" is the custom database ORACLE schema association to my custom application called "Demasy Custom Applications".
[^2]: This is a custom table for data upload and migrations **ONLY** and should drop these tables after the upload data process finish.
