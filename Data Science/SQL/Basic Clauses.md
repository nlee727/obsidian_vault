## SELECT Clause
###### FROM, WHERE, and ORDER BY, LIMIT must be in that **sequential** order following SELECT
```SQL
USE sql_store;

SELECT *
FROM customers
-- WHERE customer_id = 1
ORDER BY first_name
```

###### Following the SELECT clause, "\*" returns all columns. Alternatively, you can specify. 
```SQL
SELECT last_name, first_name
FROM customers
```

###### Arithmetic operations & AS
```SQL
SELECT 
	last_name, 
	first_name, 
	points,
	(points + 10) * 100 AS 'discount factor'
FROM customers
```
- AS is an alias

###### DISTINCT
```SQL
SELECT DISTINCT state
FROM customers
```
- Removes duplicates

## WHERE Clause
Use to filter data
```SQL
SELECT *
FROM customers
WHERE birth_date >= '1990-01-01' 
```
- = equal operator
- != or <> not equal operator
- date datatype also uses '1990-01-01'.

#### Comparison Operators
```SQL
SELECT *
FROM customers
WHERE NOT (birth_date >= '1990-01-01' OR points > 1000)
	AND state = 'va' 
```
- AND operator is evaluated first before OR
- Comparing strings is not case sensitive

##### IN operator
For using multiple OR comparisons
```SQL
SELECT *
FROM customers
WHERE state IN ('va','fl','ga')
```

```SQL
SELECT *
FROM customers
WHERE state NOT IN ('va','fl','ga')
```

##### BETWEEN operator
```SQL
SELECT *
FROM customers
WHERE points BETWEEN 1000 AND 3000
```
- BETWEEN operator is inclusive

##### LIKE operator
```SQL
SELECT *
FROM customers
WHERE last_name NOT LIKE 'b%'
```
- % will indicate any number of letters following b
- b% will be last name that starts with b, also not case sensitive
- %b% will indicate that there is a b somewhere in the name
```SQL
SELECT *
FROM customers
WHERE last_name LIKE '_y'
```
- _ is a single character, so in this case a last name with exactly 2 characters that ends in y
- can use multiple _ for multiple characters e.g.
```SQL
SELECT *
FROM customers
WHERE last_name LIKE 'b _ _ _ _ y'
```

##### REGEXP operator
Powerful when searching for strings, more complex patterns
```SQL
SELECT *
FROM customers
WHERE last_name REGEXP 'field'
```
- last name contains 'field'

```SQL
WHERE last_name REGEXP '^field'
```
- ^ indicates the string must start with field

```SQL
WHERE last_name REGEXP 'field$'
```
- $ represents the end of a string

```SQL
WHERE last_name REGEXP 'field|mac'
```
- last name contains field or mac

```SQL
WHERE last_name REGEXP '[gim]e'
```
- matches last name to contain "ge", "ie", or "me" in their last name

```SQL
WHERE last_name REGEXP '[a-h]e'
```
- range of characters from a to h, succeeded by e

##### IS NULL operator
get records that have NULL values
```SQL
WHERE phone IS NULL
```

## ORDER BY clause
For sorting using different columns
```SQL
SELECT *
FROM customers
ORDER BY first_name DESC
```
- DESC for descending order

```SQL
SELECT *
FROM customers
ORDER BY state DESC, first_name
```
- Ordering by multiple columns, for example if there are multiple people in the same state, then orders by first name

```SQL
SELECT first_name, last_name, 10 AS points
FROM customers
ORDER BY points, first_name
```
- Even if you do not use "\*" to select all columns, you can order by columns that are not selected
- You can sort by column positions, but it is bad practice

```SQL
SELECT *, quantity* unit_price AS total_price
FROM order_items
WHERE order_id = 2
ORDER BY total_price DESC
```
- Alias used like a variable

## LIMIT clause
```SQL
SELECT *
FROM customers
LIMIT 3
```
- Will retrieve the first 3 entries (first 3 rows)
- If the argument exceeds the number of rows, it will return everything

```SQL
SELECT *
FROM customers
LIMIT 6, 3
```
- The first argument is the offset
- Will skip the first 6 and retrieve customers 7,8,9
- LIMIT clause is put at the end

## JOIN
### INNER JOIN
For selecting columns from multiple tables
Typing JOIN will implicitly convert to INNER JOIN
```SQL
SELECT *
FROM orders
JOIN customers ON orders.customer_id = customers.customer_id
```
- Joining orders and customers columns, but making sure customer id are equal

```SQL
SELECT order_id, o.customer_id, first_name, last_name
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id
```
- After JOIN, order.customer_id and customers.customer_id must be specified
- use of aliases for ease

#### JOIN across databases
```SQL
SELECT *
FROM order_items oi
JOIN sql_inventory.products p ON oi.product_id = p.product_id
```
- Only need to prefix tables that are not in the current database

#### Self JOIN
```SQL
USE sql_hr;

SELECT e.employee_id, e.first_name, m.first_name AS manager
FROM employees e
JOIN employees m ON e.reports_to = m.employee_id
```
- only difference is that you must use different aliases, and must prefix each column with an alias

#### Joining Multiple Tables
```SQL
SELECT o.order_id, o.order_date, c.first_name, c.last_name, os.name AS status 
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id
JOIN order_statuses os ON o.status = os.order_status_id
```

#### Compound Join Conditions
```SQL
SELECT *
FROM order_items oi
JOIN order_item_notes oin 
	ON oi.order_id = oin.order_id 
	AND oi.product_id = oin.product_id
```


#### Implicit Join Syntax
```SQL
SELECT *
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id
```
Equivalent to
```SQL
SELECT *
FROM orders o, customers c
WHERE o.customer_id = c.customer_id
```
- Usually want to stick with JOIN statements to prevent cross joining

### OUTER JOIN
For when the ON condition is not met, but you still want to include the data in the table

```SQL
SELECT *
FROM customers c
LEFT JOIN orders o ON c.customer_id = o.customer_id
ORDER BY c.customer_id
```
- All the records from the left table, customers, are returned whether the ON condition is met

```SQL
SELECT *
FROM customers c
RIGHT JOIN orders o ON c.customer_id = o.customer_id
ORDER BY c.customer_id
```
- All the records from the right table, orders, are returned whether the ON condition is met

#### OUTER JOIN Between Multiple Tables
