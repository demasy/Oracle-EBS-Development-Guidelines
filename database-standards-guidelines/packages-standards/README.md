# Packages Standards

<br>

- Naming Syntax
- <a href="#naming-convention">**Naming Convention**</a>
- <a href="#standards">**Standards**</a>
- Naming Syntax

<br>


## Naming Convention


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

## Standards

- You MUST follow database custom objects <a href="https://github.com/demasy/Oracle-EBS-Development-Guidelines/tree/main/database-standards-guidelines">**general standards**</a>.
- You MUST place the new packages in the "**APPS**" schema.
- The packages name `{object_name}` must be 27 characters or less for table handlers packages, and end with `PKG`.
- The packages name `{object_name}` must be 27 characters or less for public packages, and end with `API`. 
- The packages name `{object_name}` must be 27 characters or less for private packages, and end with `PVT`. 
- The packages name `{object_name}` must be 30 characters or less for unit testing packages, and start with `UT`. 

<br>
