Azure SQL Database: Managing multiple databases using Elastic Database Jobs
===========================================================================

            
**Introduction**

Elastic Database jobs (preview) unleashes the ease of managing large sets of Azure SQL Databases allowing execution of Transact-SQL (T-SQL) scripts and/or application of DACPACs across all databases. You can easily and reliably
 manage Azure SQL Database at scale across an entire group of databases by running T-SQL scripts to perform administrative operations such as schema changes, credentials management, reference data updates, performance data collection or tenant (customer) telemetry
 collection. Normally, you must connect to each database independently in order to run T-SQL statements or perform other administrative tasks. Elastic Database jobs handle the task of logging in, and reliably running the script, while providing status of execution
 for each database. Using Elastic Database jobs, you can create custom database groups, define schedules to allow for recurring jobs such as index maintenance, and create jobs for data collection scenarios pushing results to a destination table. Now, perform
 administrative operations across a large number of databases as if they were a single database.


The goal of the script is to demonstrate using Elastic Database jobs to monitor performance of many databases by creating a custom collection containing all databases in a server (except master) and schedules a re-occurring
 job to execute the script against the group of databases.

**Prerequisites**

  *  Azure PowerShell must be installed. For more information, see https://azure.microsoft.com/en-us/documentation/articles/powershell-install-configure/

  *  Familiarity with Elastic Database jobs which must be installed along with the and PowerShell module. For more information, see

https://azure.microsoft.com/en-us/documentation/articles/sql-database-elastic-jobs-service-installation/

  *  Server with target databases and destination server and database for results collection. Note this database can reside in same server as target.


This script uses helper functions to simplify the creation of the each of the objects for successful job execution, including initially defining and/or refreshing the custom collection, the credentials used both for execution
 of the scripts against the target databases and for permissions to store the UNION ALL result set from the results returning query pulling performance data from each databases, and the schedule. The script can be reliably re-executed to validate if any databases
 have been added of removed from the Azure SQL Database server in order to accurately update the custom collection. Within the script, comments include alternative cmdlets to updates to values such as modifying schedule or destination location for the returning
 results set, in addition to calls for monitoring execution status. For a complete documentation of API calls, see https://azure.microsoft.com/en-us/documentation/articles/sql-database-elastic-jobs-powershell/.


 
Next steps

To further understand job creation and management, see creating and managing elastic database jobs here:

https://azure.microsoft.com/en-us/documentation/articles/sql-database-elastic-jobs-powershell/.


Learn More

Not using elastic database tools yet? Check out our Getting Started Guide and Documentation Map. For questions, please reach out to us on the SQL Database forum and for feature requests, please add them to the SQL Database feedback
 forum.


        
    
TechNet gallery is retiring! This script was migrated from TechNet script center to GitHub by Microsoft Azure Automation product group. All the Script Center fields like Rating, RatingCount and DownloadCount have been carried over to Github as-is for the migrated scripts only. Note : The Script Center fields will not be applicable for the new repositories created in Github & hence those fields will not show up for new Github repositories.
