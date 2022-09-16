# Oracle PL/SQL Coding Standards


<br>

- <a href="#syntax">**Syntax**</a>
- <a href="#plsql-objects-naming-convention">**PL/SQL Objects Naming Convention**</a>
- <a href="">**PL/SQL Objects Naming Standards**</a>

<br>


## Syntax 

> {scope}{separator}[Optional {prefix}{separator}]{identifier_name}[Optional {separator}{suffix}]

<br>

## PL/SQL Objects Naming Convention

 | SEQ | Object Name       | Length | scope | Prefix | Suffix | Example           |
 | :-  | :----             | :-:    | :--   | :---   | :--    | :----             |
 | 1   | **Variables**     |   -    |  -    |  -     | -      |  -               |
 | 1.1 | Global Variable   |        | g     |        |        | g_enterprise_id   | 
 | 1.2 | Local Variable    |        | l     |        |        | l_customer_id     | 
 | 2   | **Constants**     | -      | -     |  -     | -      | -                 |
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
