# QueryCraft: AI-Powered Text-to-SQL Generator

## Problem Statement

Writing SQL queries requires database knowledge and understanding of complex table relationships. Business users and analysts often struggle to retrieve data efficiently without SQL expertise.

## Context

QueryCraft leverages Google's Gemini LLM to convert natural language questions into accurate SQL queries. By understanding database schemas, table relationships, and user intent, the system enables users to interact with databases using plain English.

## Objectives

### Natural Language to SQL Generation

Allow users to ask questions in human language and automatically generate SQL queries.

### Schema-Aware Query Understanding

Utilize database schema information and table relationships to produce accurate and optimized SQL.

### Simplified Data Access

Reduce the dependency on SQL expertise and make database querying accessible to everyone.

## How It Works

### Schema Processing

The database schema, table metadata, and relationships are extracted and formatted for the LLM.

### Context Generation

Schema information is converted into structured prompts that help the model understand the database structure.

### Query Generation

The user's question and schema context are sent to Gemini, which generates the corresponding SQL query.

### Query Validation

Generated SQL is validated before being returned to the user.

## Architecture



### Step 1: Schema Extraction

Database tables, columns, and relationships are collected from MySQL.

### Step 2: Schema Context Generation

The extracted schema is transformed into LLM-friendly context.

### Step 3: User Query Processing

The user submits a natural language question.

### Step 4: SQL Chain Execution

Gemini processes both the schema context and user query to generate SQL.

### Step 5: SQL Review & Validation

The generated query is reviewed and validated for correctness.

### Step 6: Final Response

The validated SQL query is returned to the user.

## Example

**Input**

> What is the total number of orders placed by Mr. X?

**Output**

```sql
SELECT COUNT(o.order_id)
FROM orders o
JOIN customers c
ON o.customer_id = c.customer_id
WHERE c.customer_name = 'Mr. X';
```

## Tech Stack

* Python
* Google Gemini API
* MySQL
* Prompt Engineering
* SQL Validation

## Product Report

QueryCraft simplifies database interaction by transforming natural language into SQL queries. By combining schema understanding with Gemini's reasoning capabilities, the platform enables faster data access, improved productivity, and a more intuitive analytics experience.
