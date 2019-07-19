# wroom
Modern software projects often use many different tools. This can quickly become confusing. In order not to deal with each tool individually, a single build automation tool (e.g.: npm, make, mvn) is often used. All other tools will then be integrated into this by appropriate configuration and scripts.  These configurations are usually part of the codebase. It is then often enough to install the necessary tools and have a copy of the code base. 
This is unfortunately not very widespread in the area of database development. 
However, it is an important approach for a lean CI/CD pipeline. 


Wroom is a MVP (Minimum Viable Project)  to demonstrate a CI-Stack with Oracle APEX

| Tools | Summary | 
| --- | --- |
| [liquibase](https://www.liquibase.org/) | To handle database migration scripts.  |
| [utPLSQL](http://utplsql.org/)   | You should use it! |
| [Make](https://www.gnu.org/software/make/) | Do complex stuff in a single line of code!|
| jq | Marries JSON and the command line |
| [Docker](https://www.docker.com/)    | Add your entire infrastructure to the codebase  |
| [Git](https://git-scm.com/)       | You should use it! |
| APEX+Git  | see: [APEX_EXPORT and Version Control](https://ogobrecht.github.io/posts/2018-07-25-apex-export-and-version-control) and [Automatisierter Export und Import von APEX-Anwendungen per Kommandozeile ](https://apex.oracle.com/pls/apex/germancommunities/apexcommunity/tipp/4901/index.html) | 
| [Selenium](https://www.seleniumhq.org/)  | Needs to be done. See also here: [https://www.apextestautomation.co.uk/](https://www.apextestautomation.co.uk/)  |
| [SEPS](https://docs.oracle.com/en/database/oracle/oracle-database/19/dbseg/configuring-authentication.html#GUID-803496D2-19C7-4F02-94EC-C13EDD8FB17B)  | Do not store passwords in scripts

