## 1 SQL injection

Date:  Oct 16, 2022
Course:  PortSwigger Web Security Academy
Topics: [[sql injection]] [[sqli]]  
Source: https://portswigger.net/web-security/sql-injection

---
## What is SQL injection (SQLi)?
- Vulnerability that allows attacker to interfere with application database queries
- Allowing attacker to view data that normally are not able to retrieve.
- May enable attacker to modify, delete data or compromise the server/back-end infrastructure or perform a denial-of-service attack.

## SQL injection examples
-   [Retrieving hidden data](https://portswigger.net/web-security/sql-injection#retrieving-hidden-data), where you can modify an SQL query to return additional results.
-   [Subverting application logic](https://portswigger.net/web-security/sql-injection#subverting-application-logic), where you can change a query to interfere with the application's logic.
-   [UNION attacks](https://portswigger.net/web-security/sql-injection/union-attacks), where you can retrieve data from different database tables.
-   [Examining the database](https://portswigger.net/web-security/sql-injection/examining-the-database), where you can extract information about the version and structure of the database.
-   [Blind SQL injection](https://portswigger.net/web-security/sql-injection/blind), where the results of a query you control are not returned in the application's responses.

---
### Retrieving Hidden Data

**Standard request**
`https://insecure-website.com/products?category=Gifts`

***SQL query result***
```sql
SELECT * FROM products WHERE category = 'Gifts' AND released = 1
```

**Example 1 - Constructed attack request using `--`**
`https://insecure-website.com/products?category=Gifts'--`

***SQL query result***
```sql
SELECT * FROM products WHERE category = 'Gifts'--' AND released = 1
```

- The key thing here is that the double-dash sequence `--` is a comment indicator in SQL
- This means that the rest of the query is interpreted as a comment.

**Example 2 - Constructed attack request  using `+OR+1=1--`**
`https://insecure-website.com/products?category=Gifts'+OR+1=1--`

***SQL query result***
```sql
SELECT * FROM products WHERE category = 'Gifts' OR 1=1--' AND released = 1
```

- The modified query will return all items where either the category is Gifts, or 1 is equal to 1. 
- Since `1=1` is always true, the query will return all items.

#### Lab SQL injection vulnerability in WHERE clause allowing retrieval of hidden data
**Solution:**  
`https://0a3000280458a2f9c01407300056003c.web-security-academy.net/filter?category=Gifts%27+OR+1=1--`

---
### Subverting Application Logic

- Example applications that lets user log in with username and password.

***SQL query result***
```sql
SELECT * FROM users WHERE username = 'wiener' AND password = 'bluecheese'
```

- Attacker examples where username is entered as `administrator'--`  

***SQL query result***
```sql
SELECT * FROM users WHERE username = 'administrator'--' AND password = ''
```

#### Lab SQL injection vulnerability allowing login bypass
**Solution:**  
- Click `Home | >> My Account`
- Fill in username as `administrator'--`
- Fill in password as any value ie. `blah`

---
### Retrieving data from other database tables

- Leveraging SQL injection using `UNION` keyword.

Example:
```sql
SELECT name, description FROM products WHERE category = 'Gifts'' UNION SELECT username, password FROM users--
```

- This will cause the application to return all usernames and passwords along with the names and descriptions of products.

---
### Examining the database

- Obtaining information about the database itself. 
- Information gathered may assist with further exploitation

Examples:  
- Obtaining SQL version or table schema

```sql
SELECT * FROM v$version
```

```sql
SELECT * FROM information_schema.tables
```

---
### Blind SQL injection vulnerabilities

- When the applications does not return the results of the SQL query or errors within its responses.
- Can still be exploited to access unauthorized data.
- Example techniques:
	- Changed the logic of the query. Inject new conditions into some Boolean logic, or trigger an error such as divide-by-zero.
	- Conditionally trigger a time delay, infer truth of conditions based on how long the applications takes to respond.
	- Trigger an out-of-band network interaction, using OAST techniques. For example by placing the data into a DNS lookup for a domain that you control.
	
---
### How to detect SQL injection vulnerabilities

- Using Burp Suite's web vulnerability scanner
- Using manual testing
	- Submitting the single quote character `'` and looking for errors or anomalies
	- Submitting SQL specific syntax that evaluates to the base value of the entry point. Looking for differences in the application responses.
	- Submitting Boolean conditions such as `OR 1=1` and `OR 1=2` and looking at application responses.
	- Submitting payloads designed to trigger time delays. 
	- Submitting OAST payloads and monitoring for any resulting interactions.

---
### SQL injection in different parts of the query

- Most SQL injection vulnerabilities arise within the `WHERE` clause of a `SELECT` query.
- In `UPDATE` statements, within the updated values or the `WHERE` clause.
- In `INSERT` statements, within the inserted values.
- In `SELECT` statements, within the table or column name.
- In `SELECT` statements, within the `ORDER BY` clause.

---
### SQL injection in different contexts

- You can perform SQL injection attacks using any controllable input that is processed as a SQL query by the application.
- Some websites take input in JSON or XML format and use this to query the database.
- May provide alternative ways for you to [obfuscate attacks](https://portswigger.net/web-security/reference/obfuscating-attacks-using-encodings#obfuscation-via-xml-encoding) that are otherwise blocked due to WAFs and other defense mechanisms
- Bypass these filters by simply encoding or escaping characters in the prohibited keywords

Example XML-based SQL injection using escape sequence to encode the `S` character in SELECT.  This will be decoded server-side before being passed to the SQL interpreter.

```xml
<stockCheck> 
	<productId>
		123 
	</productId> 
	<storeId>
		999 &#x53;ELECT * FROM information_schema.tables
	</storeId>
</stockCheck>
```

- Using Burp Suite extension Hackvertor
	- Hackvertor is a tag-based conversion tool that supports various escapes and encodings including HTML5 entities, hex, octal, unicode, url encoding etc.

**Solution:**  
```

```

---
### Second-order SQL injection

First-order SQL injection arises where the application takes user input from an HTTP request and, in the course of processing that request, incorporates the input into an SQL query in an unsafe way.  
  
In second-order SQL injection (also known as stored SQL injection), the application takes user input from an HTTP request and stores it for future use. This is usually done by placing the input into a database, but no vulnerability arises at the point where the data is stored. Later, when handling a different HTTP request, the application retrieves the stored data and incorporates it into an SQL query in an unsafe way.  

---
### Database-specific factors

Some techniques for detecting and exploiting SQL injection work differently on different platforms. For example:  

- Syntax for string concatenation.
- Comments.
- Batched (or stacked) queries.
- Platform-specific APIs.
- Error messages.
---
### Cheatsheet

https://portswigger.net/web-security/sql-injection/cheat-sheet

---
### How to prevent SQL injection

- Most instances of SQL injection can be prevented by using parameterized queries (also known as prepared statements) instead of string concatenation within the query.
- For a parameterized query to be effective in preventing SQL injection, the string that is used in the query must always be a hard-coded constant, and must never contain any variable data from any origin.