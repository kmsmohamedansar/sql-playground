# SQL Playground

A place to practise SQL that opens in a second. There's no database to install, no account, and nothing you can break. It runs SQLite right in your browser, with a small translation layer on top so Snowflake style queries work. That way the habits you build here carry over to a real warehouse.

**Try it:** https://kmsmohamedansar.github.io/sql-playground

## Why I built it

I write SQL for a living, and I wanted somewhere quick to practise. SQLite isn't Snowflake, and the little differences between them are exactly what trips people up. So the playground quietly rewrites a few Snowflake patterns into something SQLite understands.

## What you can try

Queries like these work out of the box:

```sql
DESCRIBE TABLE employees;
SHOW TABLES;
SELECT * FROM customers WHERE name ILIKE '%co%';
```

`DATE_TRUNC` and `QUALIFY` are supported too, and there are a few more.

## How it works

It's static HTML and JavaScript, with no backend. SQLite runs as WebAssembly (through sql.js) inside the page, so your queries never leave your computer. Before a query runs, a translation step rewrites the Snowflake style parts into their SQLite equivalents.

## Run it locally

Serve the folder over HTTP, for example with GitHub Pages or any static server. Opening `index.html` straight from disk can block WebAssembly in some browsers.

## Status

I look after it when it needs it. It's a public demo.
