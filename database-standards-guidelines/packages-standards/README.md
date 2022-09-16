# Packages Standards

- <a href="#packages-naming-syntax">**Packages Naming Syntax**</a>
- <a href="#packages-naming-convention">**Packages Naming Convention**</a>
- <a href="#packages-naming-standards">**Packages Naming Standards**</a>
- <a href="#packages-naming-examples">**Packages Naming Examples**</a>

<br>

## Packages Naming Syntax

<br>

## Packages Naming Convention


 | SEQ  | Object Name              | Length | Prefix | Suffix | Example |
 | :-:  | :----                    | :-:    | :---:  | :---   | :----   |
 | 1    | Table Handlers Packages  | 27     |  -     | PKG    |         |
 | 1.1  | Insert Procedures        |        |  INS   | -      |         |
 | 1.2  | Update Procedures        |        |  UPD   | -      |         |
 | 1.3  | Delete Procedures        |        |  DEL   | -      |         |
 | 1.4  | Lock Procedures          |        |  LOCK  | -      |         | 
 | 3    | Public Packages          | 27     |  -     | API    |         | 
 | 4    | Private Packages         | 27     |  -     | PVT    |         | 
 | 5    | Unit Testing Packages    | 30     |  UT    | -      |         | 
 
<br>

## Packages Naming Standards

- You MUST follow custom database objects general standards.
- You MUST place the new packages in the **APPS** schema.
- The packages name `{object_name}` must be 27 characters or less for table handlers packages, and end with `PKG`.
- The packages name `{object_name}` must be 27 characters or less for public packages, and end with `API`. 
- The packages name `{object_name}` must be 27 characters or less for private packages, and end with `PVT`. 
- The packages name `{object_name}` must be 30 characters or less for unit testing packages, and start with `UT`. 

<br>

## Packages Naming Examples
