# Database configuration

The SS CMS system supports mainstream database types, including MySql, SQLServer, PostgreSQL, Oracle, and local SQLite databases. Different databases can be used as needed.

Database connection information is stored in the environment variable or `sscms.json` configuration file, if it is a formal environment, usually have a database connection information is stored after re-encryption, if it is a local test environment, it can not encrypt stored in clear text.

If you choose a local SQLite database, you do not need to install the database in advance, the system will automatically create a SQLite database. Other types of databases need to be installed in advance, usually the database and the SS CMS system are installed on different servers. For detailed database installation documentation, please refer to the official documentation of the corresponding database.

## Configuration database in the installation wizard

::: warning NOTE
If you choose a MySQL database, the minimum version is 5.5, and the latest 8.0 version is recommended.
If you select a SQL Server database, the minimum version is SQL Server 2012.
:::

Select the database type in the interface of the SS CMS installation:

![Select the database type](/docs/guide/images/getting-started/config-database/mysql.png)

* If the database port uses a non-default port, select and set a custom port.
* If you choose SQLite database, you do not need to set the database connection string. The database is located at `wwwroot/SiteFiles/ database.sqlite` by default. You can modify the default path by modifying the environment variables or the sscms.json configuration file.

Click Next, select the database where the SS CMS system is running, and then enter the administrator settings interface. If it is a formal environment, please check the bottom to encrypt the database connection string:

![encrypt the database connection string](/docs/guide/images/getting-started/config-database/security.png)

## Configuration database in sscms.json

After the system is installed, SS CMS system database connection information will be stored in `sscms.json` the configuration file:

* IsProtectData: Whether the database connection is encrypted and stored
* SecurityKey: encryption key, randomly generated by the system
* Database:Type: Database type
* Database:ConnectionString: Database connection string

If unchecked, the database connection information will be stored in clear text:

```json
{
  "IsProtectData": false,
  "SecurityKey": "fe400641210913e7",
  "Database": {
    "Type": "MySql",
    "ConnectionString": "Server=rm-2vc9sql.cn-beijing.rds.aliyuncs.com;Port=3306;Uid=sscms;Pwd=sscms;Database=sscms;SslMode=Preferred;CharSet=utf8;"
  }
}
```

If checked, the system will encrypt the database connection information, and the encryption key is randomly generated by the system SecurityKey:`SecurityKey`: 

```json
{
  "IsProtectData": true,
  "SecurityKey": "a82c6dd438ee2fe1",
  "Database": {
    "Type": "yfc27y7LKj00equals00secret0",
    "ConnectionString": "GT3SoYYd4YmhPb0add0RghRyvNjTkp47OjDc6tk2Ukw2664yFGDkZuNbGDfOhb0slash0sFG1zk5V4lkZ0add0eS9LVYW880slash0mp0add0g0equals00equals00secret0"
  }
}
```

If the database connection changes, you need to modify the configuration file so that SS CMS can connect to the database correctly.

## Configuration database in environment variables

It is recommended to use environment variables to store database connection information:

```bash
set SSCMS_ISPROTECTDATA="False"
set SSCMS_SECURITYKEY="fe400641210913e7"
set SSCMS_DATABASE__TYPE="MySql"
set SSCMS_DATABASE__CONNECTIONSTRING="Server=rm-2vc9sql.cn-beijing.rds.aliyuncs.com;Port=3306;Uid=sscms;Pwd=sscms;Database=sscms;SslMode=Preferred;CharSet=utf8;"
```

After setting the connection information in the database environment variables may be sscms.jsonthe value corresponding to the priority acquired from the connection information database environment variable is empty, the system.