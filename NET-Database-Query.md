---
search:
   keywords: ['NET', 'C#', 'ODatabase', 'query']
---

# OrientDB-NET - `Query()`

This method issues SQL queries against the OrientDB database.  It returns a list of `ODocument` objects from the result-set.

## Querying the Database

In some cases you may find features in OrientDB that are not yet available through OrientDB-NET.  You can utelize these features by passing SQL statements for them through the `Query()` method.  It returns a list of `ODocument` objects that you can operate on further.

It is comparable to the [`Command()`](NET-Database-Command.md) method.

### Syntax

```
// QUERY DATABASE
List<ODocument> Query(  string <SQL>)

// QUERY DATABASE WITH FETCH PLAN
List<ODocument> Query(  string <SQL>,
                        string <fetch-plan>)
```

- **`<SQL>`** Defines the SQL statement to use.
- **`<fetch-plan>`** Defines the [Fetching Strategy](Fetching-Strategies.md) to use.

### Example

- Execute query against database:

  ```csharp
  List<ODocument> documents;
  string query = "SELECT FROM Accounts"

  documents = database.Query(query);
  ```

- Execute query with fetch plan:

  ```csharp
  List<ODocument> documents;
  string query = "SELECT FROM Accounts"
  string fetchPlan = "*:-1"

  documents = database.Query(query, fetchPlan);
  ``` 
