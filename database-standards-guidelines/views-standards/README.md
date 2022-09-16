# Views Standards

<br>

- <a href="#views-naming-syntax">**Views Naming Syntax**</a>
- <a href="#views-naming-convention">**Views Naming Convention**</a>
- <a href="#views-naming-standards">**Views Naming Standards**</a>
- <a href="#views-naming-examples">**Views Naming Examples**</a>



<br>

## Views Naming Syntax

<br>

## Views Naming Convention

 | SEQ  | Object Name            | Length | Schema | Prefix | Suffix | Example |
 | :-:  | :----                  | :-:    | :--:   | :---:  | :---   | :----   |
 | 1    | Views                  | 30     | APPS   |   -    |   V    | XXD_PO_LC_DOCUMENTS_V |
 | 2    | Materialized Views     | 30     | APPS   |   -    |   MV   | XXD_PO_LC_DOCUMENTS_MV |
  
<br>

## Views Naming Standards
- The view name “*{object_name}*“ should be 30 characters or less and end with "_V" for view and "_VM" for materialized views.
- The first column your view should select is the ROWID for the root table, and the view should alias it to ROW_ID.
- You only need to include the ROWID column if an Oracle Forms block is based on this view.

<br>

## Views Naming Examples

<br>

