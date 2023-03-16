# SQLi
https://portswigger.net/web-security/sql-injection

## Detect SQL injection vulnerabilities
SQL injection can be detected manually by using a systematic set of tests against every entry point in the application. This typically involves:

  1. Submitting the single quote character ' and looking for errors or other anomalies.
  1. Submitting some SQL-specific syntax that evaluates to the base (original) value of the entry point, and to a different value, and looking for systematic differences in the resulting application responses.
  1. Submitting Boolean conditions such as OR 1=1 and OR 1=2, and looking for differences in the application's responses.
  1. Submitting payloads designed to trigger time delays when executed within a SQL query, and looking for differences in the time taken to respond.
  1. Submitting OAST payloads designed to trigger an out-of-band network interaction when executed within a SQL query, and monitoring for any resulting interactions.


### Places for SQLi
Most SQL injection vulnerabilities arise within the WHERE clause of a SELECT query. This type of SQL injection is generally well-understood by experienced testers.

But SQL injection vulnerabilities can in principle occur at any location within the query, and within different query types. The most common other locations where SQL injection arises are:

  - In UPDATE statements, within the updated values or the WHERE clause.
  - In INSERT statements, within the inserted values.
  - In SELECT statements, within the table or column name.
  - In SELECT statements, within the ORDER BY clause.
