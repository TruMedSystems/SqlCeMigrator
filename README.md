# SqlCeMigrator
Command line tool to move your SQL Server Compact database to SQL Server

Configured via the App.Config file:

```
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- Full path to the local sdf file to migrate from, for example C:\data\test.sdf -->
    <!-- Required -->
    <add key="SqlCeDatabasePath" value=""/>

    <!-- What to migrate: Data only = 0, Schema only = 1, Data & Schema = 2 -->
    <add key="Scope" value="0"/>
    
    <!-- If true, will rename the SQL Compact database file with date stamp -->
    <add key ="RenameSqlCeDatabase" value="true"/>
    
    <!-- Comma seperated list of SQL Compact tables to ignore during migration -->
    <add key ="SqlCeTablesToIgnore" value="__MigrationHistory"/>

    <!-- Comma seperated list of SQL Compact tables to to be appended to existing tables -->
    <!-- Only applicable if Scope = 0 -->
    <add key ="SqlCeTablesToAppend" value=""/>

    <!-- Comma seperated list of SQL Server tables to clear (DELETE), in that order -->
    <add key ="SqlServerTablesToClear" value=""/>
    
  </appSettings>
  <connectionStrings>
    <!-- Connection string for SQL Server database to migrate to -->
    <!-- Required -->
    <add name="SqlServer" connectionString="" />
  </connectionStrings>
  <startup> 
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5.2" />
  </startup>
</configuration>
````


## Latest daily build
You can download a .zip file with the [latest build of the master branch from AppVeyor](https://ci.appveyor.com/api/projects/ErikEJ/SqlCeMigrator/artifacts/SqlCeMigrator.zip?branch=master)
