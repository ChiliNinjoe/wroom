# wroom
Modern software projects often use many different tools. This can quickly become confusing. In order not to deal with each tool individually, a single build automation tool (e.g.: npm, make, mvn) is often used. All other tools will then be integrated into this by appropriate configuration and scripts.  These configurations are usually part of the codebase. It is then often enough to install the necessary tools and have a copy of the code base. 
This is unfortunately not very widespread in the area of database development. 
However, it is an important approach for a lean CI/CD pipeline. 


Wroom is a MVP (Minimum Viable Project)  to demonstrate a CI-Stack with Oracle APEX

| Tools | Summary | 
| --- | --- |
| liquibase | To handle database migration scripts.  |
| utPLSQL   | You should use it! |
| WUT       | Build your own dev tool: using Bash + GNU make + jq + SQL\*Plus/SQLcl |
| Docker    | Add your entire infrastructure to the codebase  |
| Git       | You should use it! |
| APEX+Git  | see: [APEX_EXPORT and Version Control](https://ogobrecht.github.io/posts/2018-07-25-apex-export-and-version-control) and [Automatisierter Export und Import von APEX-Anwendungen per Kommandozeile ](https://apex.oracle.com/pls/apex/germancommunities/apexcommunity/tipp/4901/index.html) | 
| Selenium  | Needs to be done. See also here: [https://www.apextestautomation.co.uk/](https://www.apextestautomation.co.uk/)  |
| [SEPS](https://docs.oracle.com/en/database/oracle/oracle-database/19/dbseg/configuring-authentication.html#GUID-803496D2-19C7-4F02-94EC-C13EDD8FB17B)  | Do not store passwords in scripts

## Wroom  - Install
* configure  
  * [liquibase.properties](liquibase.properties)
  * [env.profile](env.profile)
  * [create_user.sql](create_user.sql)

* TODO:  modify this code to simplify the configuration (via Environment Variables and a default file). 

## WUT - the dev tool
WUT is a set of build scripts to do some complex stuff in a single line.

### Load the WUT 
```
$ cd wroom
$ source bash.profile
$ wut-version 
WUT Version: 0.0.0.0.0.1-dev-pre-pre-pre-alpha
```

Command              | Description
-------------------  | -------
```wut-create-table <table-name> <entity-short-name> "<description>"```  | Create a DDL-File for the new table and integrate it into the changelog
```wut-create-package <package-name> "description"``` | Create the file for the Package and the Unit Test and integrate them into the changelog
```wut-try```       | Update the database
```wut-try-clean``` | Recreate the database
```wut-app-export```| Export the splitted source code of the APEX App. The code can then be committed via git. 
```wut-app-import```| Import the current source code of the APEX App. Overwrites any changes! 
```wut-version```   | Display the version of WUT
```wut-info```      | Display some informations

