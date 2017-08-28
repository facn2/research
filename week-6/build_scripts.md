## What is a build script and why do you need one? (think ahead to how this might come in useful when working on a project this week)
Build script of SQL essentially has its aim to create a data or to publish updates to an existing database.

First, build step compiles your database project into the files that are used for  deployment.

Second, pool.query() is shortcut for pool.getConnection() + connection.query() + connection.release(), so it automatically creates the connection.
New Pool.query method of Pool object takes the string and put inside sql.


#### Build step: read sql codes and make it into a string
```
buildScript = fs.readFileSync(`${__dirname}/db_build.sql`).toString();
```
**Create connection pool then send the string to SQL to create new data in existing database**

```
dbConnection.query(buildScript, (err, res) => {
  if (err) throw err;
  console.log('table successfully created with result:', res);
  })
```
#### why do you need one?
+ database can be reproduced easily
+ clear to keep records of changes in database
+ more readable and explicit compared to creating data/changes on psql on terminal  

[more](https://www.red-gate.com/simple-talk/sql/database-delivery/better-ways-to-build-a-database/)


## Database migration
A database Migration refers to the management of incremental, reversible changes to schemas.

It is performed whenever it is necessary to update or revert that database’s schema to some older or newer versions.
These Database migrations are performed pro-grammatically with schema migration tools.
These tools aim to minimise the impact of schema changes on any existing data in the database.
However, data preservation is not guaranteed (for example, deleting a column) and can result in destroyed data. While tools help to prevent this, sometimes manual intervention is necessary.

#### PROS
+ It allows for fixing mistakes and adapting data as requirements change
+ It is an essential part of software evolution (agile environments)

#### CONS
+ Corrupt data (old versions and not cleaned properly)
+ Lost dependencies between data (nobody knows what they do anymore)
+ Bugs and mistakes during migration

#### HOW ARE WE SUPPOSED TO DO IT?
+ Needs a high level of discipline
+ Thorough testing
+ Sound backup strategy


