# Sequences Standards

<br>

- Naming Syntax
- <a href="#naming-convention">**Naming Convention**</a>
- <a href="#standards">**Standards**</a>
- Examples

<br>

## Naming Convention

<br>

 | SEQ  | Object Name            | Length | Prefix | Suffix | Example |
 | :-:  | :----                  | :-:    | :---   | :---   | :----   |
 | 1    | Sequence               | 30     |  -     | SEQ    | `XXD_DOCUMENT_ID_SEQ` |
 
 
<br>


## Standards
- You MUST follow database custom objects <a href="https://github.com/demasy/Oracle-EBS-Development-Guidelines/tree/main/database-standards-guidelines">**general standards**</a>.
- The sequence name `{object_name}` should be 30 characters or less and end with `_SEQ`.
- You must place the new sequence in the custom ORACLE schema, for example, "**XXD**", and grant privileges to the "**APPS**" schema.
- Use each sequence to supply unique ID values for one column of one table.
- Do not design sequences that wrap using the CYCLE option or have limited ranges using MAXVALUE.
- Use a NUMBER datatype to store sequence values within PL/SQL.
- Do Not Use the FND_UNIQUE_IDENTIFIER_CONTROL Table.

<br>
