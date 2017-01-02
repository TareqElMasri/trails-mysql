# Trails-MySQL Adapter <a target="_blank" href="http://www.mysql.com"><img src="http://www.mysql.com/common/logos/powered-by-mysql-125x64.png" alt="Powered by MySQL" title="trails-mysql: MySQL adapter for Trailsjs"/></a>
[![Build Status](https://travis-ci.org/balderdashy/trails-mysql.svg?branch=master)](https://travis-ci.org/balderdashy/trails-mysql)
[![npm version](https://badge.fury.io/js/trails-mysql.svg)](http://badge.fury.io/js/trails-mysql)

MySQL adapter for the Sails framework and Waterline ORM.  Allows you to use MySQL via your models to store and retrieve data.  Also provides a `query()` method for a direct interface to execute raw SQL commands.



## Installation

Install from NPM.

```bash
# In your app:
$ npm install trails-mysql
```

## Sails Configuration

Add the mysql config to the config/connections.js file. Basic options:

```javascript
module.exports = {
  stores: {
    mysqlstore: {
      module    : 'trails-mysql',
      host      : 'localhost',
      port      : 3306,
      user      : 'username',
      password  : 'password',
      database  : 'MySQL Database Name'

      // OR (explicit sets take precedence)
      module    : 'sails-mysql',
      url       : 'mysql2://USER:PASSWORD@HOST:PORT/DATABASENAME'

      // Optional
      migrate: 'alter',
      charset   : 'utf8',
      collation : 'utf8_swedish_ci'
    }
  },
  
  models: {
    defaultStore: 'mysqlstore', 
    migrate: 'alter'
  }
};
```

And then change default model configuration to the config/models.js:

```javascript
module.exports.models = {
  connection: 'mysql'
};
```

## Run tests

You can set environment variables to override the default database config for the tests, e.g.:

```sh
$ WATERLINE_ADAPTER_TESTS_PASSWORD=yourpass npm test
```


Default settings are:

```javascript
{
  host: process.env.WATERLINE_ADAPTER_TESTS_HOST || 'localhost',
  port: process.env.WATERLINE_ADAPTER_TESTS_PORT || 3306,
  user: process.env.WATERLINE_ADAPTER_TESTS_USER || 'root',
  password: process.env.WATERLINE_ADAPTER_TESTS_PASSWORD || '',
  database: process.env.WATERLINE_ADAPTER_TESTS_DATABASE || 'sails_mysql',
  pool: true,
  connectionLimit: 10,
  waitForConnections: true
}
```



#### More Resources

- [Stackoverflow](http://stackoverflow.com/questions/tagged/trails.js)
- [#sailsjs on Freenode](http://webchat.freenode.net/) (IRC channel)
- [Waterline (ORM)](http://github.com/balderdashy/waterline)


#### License

**[MIT](./LICENSE)**
&copy; 2014
[Mike McNeil](http://michaelmcneil.com), [Balderdash](http://balderdash.co) & contributors

[Sails](http://sailsjs.org) is free and open-source under the [MIT License](http://sails.mit-license.org/).

See the [MySQL Logo Usage Guidelines](http://www.mysql.com/about/legal/trademark.html) for more information on our use of the MySQL logo.

[![Trails.js](http://i.imgur.com/0iVVRxi.png)](http://trailsjs.io)
