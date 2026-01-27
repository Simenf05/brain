---
aliases:
---

2026-01-20 10:20

Tags: #database #relation 

# Structured Query Language


## Authorization
### Privileges in SQL
- SELECT
- INSERT
- UPDATE
- DELETE
- ALL PRIVILEGES

## Data types
### Basic data types
- Integer
- String
- Float
- ...

### Built-in data types
#### Time
- DATE
- TIME
- TIMESTAMP
	- (Can be time since epoch)
- INTERVAL

#### Large objects
- BLOB
	- Binary large object
- CLOB
	- Character large object

#### Custom domain
We can add constraints to values, and force them to act like enumerations. 

#### User-defined types
We can define types to simplify statements. 
```sql

```



### Roles
We can grant privileges to user groups with roles. 
```sql
CREATE ROLE <role>;
GRANT <role> TO <user list>;
```


## Further reading
- [[Relational algebra]]
