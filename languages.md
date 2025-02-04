# Languages

A series of basic commands to use common languages (JS, SQL)

## JavaScript

#### Basics

```
// Hello, World! program
console.log("Hello, World!");
```

```
// Variable and Data Type
let age = 25; // Number type
```

```
// Control Flow Statement
if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are a minor.");
}
```

```
// Function
function greet(name) {
    console.log("Hello, " + name + "!");
}
```

```
// Calling the function
greet("Bob");
```

#### How to Execute JS on Browser

* Chrome: right-click + Inspect

#### internal.html

```
// Hello, World! program
console.log("Hello, World!");

// Variable and Data Type
let age = 25; // Number type

// Control Flow Statement
if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are a minor.");
}

// Function
function greet(name) {
    console.log("Hello, " + name + "!");
}

// Calling the function
greet("Bob");
```

#### script.js

```
let x = 5;
let y = 10;
let result = x + y;
document.getElementById("result").innerHTML = "The result is: " + result;
```

#### external.html

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>External JS</title>
</head>
<body>
    <h1>Addition of Two Numbers</h1>
    <p id="result"></p>

    <!-- Link to the external JS file -->
    <script src="script.js"></script>
</body>
</html>
```

#### How to See JS Type on Browser

* Chrome: right-click + View page source
    * check for "src" attributes

#### Alerts

```
alert("HelloTHM");
```

#### Prompts

```
name = prompt("What is your name?");
alert("Hello " + name);
```

#### Confirms

```
confirm("Are you sure?");
```

#### DDOS

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Hacked</title>
</head>
<body>
    <script>
        for (let i = 0; i < 500; i++) {
            alert("Hacked");
        }
    </script>
</body>
</html>
```

#### if-else

```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Age Verification</title>
</head>
<body>
    <h1>Age Verification</h1>
    <p id="message"></p>

    <script>
        age = prompt("What is your age")
        if (age >= 18) {
            document.getElementById("message").innerHTML = "You are an adult.";
        } else {
            document.getElementById("message").innerHTML = "You are a minor.";
        }
    </script>
</body>
</html>
```

#### Obfuscation - Minified Files

* Use Java-Script Obfuscator

## SQL

#### Database Manipulations

```
CREATE DATABASE *database_name*;
```

```
SHOW DATABASES;
```

```
USE *database_name*;
```

```
DROP database *database_name*;
```

#### Table Manipulations

```
CREATE TABLE *table_name* (
        	*column1* *data_type1*,
            *column2* *data_type2*,
            *column3* *data_type3*
);
```

```
SHOW TABLES;
```

```
DESCRIBE *table_name*;
```

```
ALTER TABLE *table_name*
ADD *column4* *data_type4*;
```

```
DROP TABLE *table_name*;
```

#### Data Manipulations

```
INSERT INTO books (id, name, published_date, description)
VALUES (1, "Android Security Internals", "2014-10-14", "An In-Depth Guide to Android's Security Architecture");
```

```
SELECT * FROM books;
```

```
SELECT name, description FROM books;
```

```
UPDATE books
SET description = "An In-Depth Guide to Android's Security Architecture."
WHERE id = 1;
```

```
DELETE FROM books WHERE id = 1;
```

```
SELECT DISTINCT name FROM books;
```

```
SELECT name, COUNT(*)
FROM books
GROUP BY name;
```

```
SELECT *
FROM books
ORDER BY published_date ASC;
```

```
SELECT *
FROM books
ORDER BY published_date DESC;
```

```
SELECT name, COUNT(*)
FROM books
GROUP BY name
HAVING name LIKE '%Hack%';
```

```
SELECT *
FROM books
WHERE description LIKE "%guide%";
```

```
SELECT *
FROM books
WHERE category = "Offensive Security" AND name = "Bug Bounty Bootcamp";
```

```
SELECT *
FROM books
WHERE name LIKE "%Android%" OR name LIKE "%iOS%";
```

```
SELECT *
FROM books
WHERE NOT description LIKE "%guide%";
```

```
SELECT *
FROM books
WHERE id BETWEEN 2 AND 4;
```

```
SELECT *
FROM books
WHERE name = "Designing Secure Software";
```

```
SELECT *
FROM books
WHERE category != "Offensive Security";
```

```
SELECT *
FROM books
WHERE published_date < "2020-01-01";
```

```
SELECT *
FROM books
WHERE published_date > "2020-01-01";
```

```
SELECT *
FROM books
WHERE published_date <= "2021-11-15";
```

```
SELECT *
FROM books
WHERE published_date >= "2021-11-02";
```

```
SELECT CONCAT(name, " is a type of ", category, " book.") AS book_info FROM books;
```

```
SELECT category, GROUP_CONCAT(name SEPARATOR ", ") AS books
FROM books
GROUP BY category;
```

```
SELECT SUBSTRING(published_date, 1, 4) AS published_year FROM books;
```

```
SELECT LENGTH(name) AS name_length FROM books;
```

```
SELECT COUNT(*) AS total_books FROM books;
```

```
SELECT SUM(price) AS total_price FROM books;
```

```
SELECT MAX(published_date) AS latest_book FROM books;
```

```
SELECT MIN(published_date) AS earliest_book FROM books;
```