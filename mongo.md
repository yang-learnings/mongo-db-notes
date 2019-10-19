## mongo

### User

#### Create a user

```js
db.createUser(
  {
    user: "reportsUser",
    pwd: passwordPrompt(),  // or cleartext password
    roles: [
       { role: "read", db: "reporting" },
       { role: "read", db: "products" },
       { role: "read", db: "sales" },
       { role: "readWrite", db: "accounts" }
    ]
  }
)
```

#### Drop a user

```js
use admin
db.dropUser('<userName>')
```

#### Roles

* read
* readWrite

* dbAdmin – Grant privileges to perform administrative tasks
* userAdmin – Allows you to create and modify users and roles on the current database
* dbOwner – This role combines the following:
* * readWrite
* * dbAdmin
* * userAdmin

* clusterMonitor – Provides read-only access to monitoring tools
* clusterManager – For management and monitoring actions on the cluster
* hostManager – To monitor and manage servers
* clusterAdmin – Combines the other three roles plus dropDatabase action

* backup – Provides the privileges needed for backing up data
* restore – Provides the privileges needed to restore data from backups

* readAnyDatabase – The same as ‘read’ role but applies to all databases
* readWriteAnyDatabase – The same as ‘readWrite’ role but applies to all databases
* userAdminAnyDatabase – The same as ‘userAdmin’ role but applies to all databases
* dbAdminAnyDatabase – The same as ‘dbAdmin’ role but applies to all databases

* userAdmin
* dbOwner
* userAdminAnyDatabase

* root

