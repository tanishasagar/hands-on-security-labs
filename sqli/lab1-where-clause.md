# SQL Injection in WHERE Clause — Retrieving Hidden Data

**Source:** PortSwigger Web Security Academy
**Difficulty:** Apprentice
**Category:** SQL Injection

## The vulnerability

The application filters products by category using a value taken directly from the URL. That value is inserted straight into the SQL query without being separated from the query's structure, so user input can alter the logic of the query itself.

## Query structure

The application builds its query like this:

```sql
SELECT * FROM products WHERE category = '[INPUT]' AND released = 1
```

**Before any payload**, requesting the Gifts category produces:

```sql
SELECT * FROM products WHERE category = 'Gifts' AND released = 1
```

## Payload
