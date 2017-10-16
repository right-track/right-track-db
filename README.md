Right Track Database (Abstract)
===============================

#### node module: [right-track-db](https://www.npmjs.com/package/right-track-db)

---

This is the abstract `RightTrackDB` Class that is used by various [Right Track projects](https://github.com/right-track) 
to query the SQLite [Right Track Database](https://github.com/right-track/right-track-db-build).

An implementation of this Class, such as [right-track-db-sqlite3](https://github.com/right-track/right-track-db-sqlite3),
which uses the node `sqlite3` module, is what will actually be used in the projects.

An implementation of this Class must have the following functions:

- `constructor({RightTrackAgency} agency)`:
    - this is used to initialize the SQLite database
    - `agency`: The `RightTrackAgency` this DB will be used to query.  The 
    agency must have the configuration properties set to the agency's id 
    as well as the database location.

- `select({string} statement, {function} callback)`:
    - this is used to SELECT multiple rows from the SQLite database using 
    the passed statement.  It will return the rows using the passed callback 
    function.
    - `statement`: the full SQLite SELECT statement
    - `callback`: the selectCallback function

- `get({string} statement, {function} callback)`:
    - this is used to SELECT a single row from the SQLite database using the 
    passed statement.  It will return the result using the passed callback 
    function.
        - If no rows are selected, it will return `undefined`
        - If one row is selected, it will return the single row
        - If more than one row is selected, it will return the first row
    - `statement`: the full SQLite SELECT statement
    - `callback`: the getCallback function
 
 
 ### Documentation
 
 Documentation can be found in the **/doc/** directory of this repository 
 or online at [https://docs.righttrack.io/right-track-db](https://docs.righttrack.io/right-track-db).