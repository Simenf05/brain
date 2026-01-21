---
aliases:
---

2026-01-13 10:19

Tags: #database #relation

# Relational algebra
## Primitive operations
### Select ($\sigma$)
Filtering rows by a predicate set $p$, makes a new set of all the rows included $\sigma_p(r)$. We use predicate logic to combine multiple comparisons into bigger expressions. In the predicate you can use multiple columns from the input relation. 
### Project ($\pi$) $\Pi$
Project will remove make a new relation only containing the specific columns. $\Pi_{name}(\sigma_{dept\_name='Physics'}(instructor))$
### Cross product 
Cross product combination of two relations. 
### Union ($\cup$)
The standard set theory union. $r_i \cup r_j$. This combines two relations and creates one that contains both. 
For the union to be valid, you need the two relations to have the same arity. And the attribute domains must be the same.  
### Set difference ($-$)
Find relations that are in $r_i$ but not in $r_j$, $r_i - r_j$. Is the same as set difference, and needs the attributes to be compatible. 
### Renaming ($\rho$)
Allows us to give names to expressions. It makes it easier to refer to complex expressions. 
$\rho_x(E)$
## Derived operations:
### Assignment operator
We can assign expressions to variables to make it easier to work with. 

### Intersection operator 
The result is a relations containing the rows that are in both relations. 
$r_i \cap r_j$
This can be made using [[#Union ($ cup$)|union]] and [[#Set difference ($-$)|difference]].

### Join operator
Join is the combination of cross product and a select on the value. 
$\sigma_{instructor.id=teaches.id}(instructor\times teaches)$
It makes this combination into one with a predicate and two relations. 
$r_i \Join_{\Theta} r_j$.
#### Types of joins
Natural join $\Join$
Outer joins:
- Left outer join
- Right outer join
- Full outer join
### Aggregation operator $\gamma$
Permits the use of aggregate functions on relation attributes. 
$A_g \gamma f(A_a)$


## Further reading
- [[Structured Query Language]]
