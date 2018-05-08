# SQL Server Installation

## Installation of SQL Server 2016 Developer Edition
These instructions are meant for learning SQL Server, not for a production installation.
1. This version is available for free when you sign up for Visual Studio Dev Essentials. Once signed up for Dev Essentials, download SQL Server 2016 Dev Edition. There is also a version with Service Pack 1. I had problems getting the file to work, so I recommend starting with the original and applying SP1 as a second step.
2. The SQL Server Developer Edition file is an ISO file. Double-click the file top open it. Double-click the Setup Icon.
![screenshot1](../../_static/images/screenshots/week1/sqlserverinstall/screenshot1.jpg)
3. The SQL Server Installation Center opens. You can click the Hardware and Software Requirements link to make sure that your system will support SQL Server 2016.
![screenshot2](../../_static/images/screenshots/week1/sqlserverinstall/screenshot2.jpg)
4. Click Installation on the left and then click New SQL Server stand-alone installation or add features to an existing installation.
![screenshot3](../../_static/images/screenshots/week1/sqlserverinstall/screenshot3.jpg)
5. This will kick off the installation wizard. On the Product Key page, make sure that Developer edition is selected and click Next.
![screenshot4](../../_static/images/screenshots/week1/sqlserverinstall/screenshot4.jpg)
6. On the License Terms page, select I accept the license terms and click next.
![screenshot5](../../_static/images/screenshots/week1/sqlserverinstall/screenshot5.jpg)
7. On the Microsoft Update page, check Use Microsoft Update to check for updates (recommended) if you want updates to be applied automatically and click Next.
![screenshot6](../../_static/images/screenshots/week1/sqlserverinstall/screenshot6.jpg)
8. On the Product Updates page, select Include SQL Server product updates and allow any critical updates to be applied. Click Next when done.
![screenshot7](../../_static/images/screenshots/week1/sqlserverinstall/screenshot7.jpg)
9. On the Feature Selection page, check Database Engine Services and Reporting Services – Native. If there are other features that you are interested in, such as Full Text, you may want to select those as well. Click Next.
![screenshot8](../../_static/images/screenshots/week1/sqlserverinstall/screenshot8.jpg)
10. On the Instance Configuration, you will provide an instance name. This is required when multiple instances of SQL Server are installed. MSSQLSERVER is the default. If this must be a named instance, write down the instance name.
![screenshot9](../../_static/images/screenshots/week1/sqlserverinstall/screenshot9.jpg)
11. On the Server Configuration page, select Grant Perform Volume Maintenance Task privilege to SQL Server Database Engine Service and click Next.
![screenshot10](../../_static/images/screenshots/week1/sqlserverinstall/screenshot10.jpg)
12. On the Database Engine Configuration page, click Add Current User to add your account to the SQL Server as an administrator. Change to Mixed Mode and fill in a password. Click Next.
![screenshot11](../../_static/images/screenshots/week1/sqlserverinstall/screenshot11.jpg)
13. Make sure that Install and Configure is selected and click Next.
![screenshot12](../../_static/images/screenshots/week1/sqlserverinstall/screenshot12.jpg)
14. On the Ready to Install page, click Install.
![screenshot13](../../_static/images/screenshots/week1/sqlserverinstall/screenshot13.jpg)
15. Once the installation is complete, restart if necessary.

## Installation of Service Pack 1
The service pack is required for fixes and new features. Install Service Pack 1 if the original media did not come with it.
1. Download the [service pack](https://www.microsoft.com/en-us/download) file.
2. Double-click the file.
![screenshot14](../../_static/images/screenshots/week1/sqlserverinstall/screenshot14.jpg)
3. Wait while the files extract and the installation wizard kicks off.
![screenshot15](../../_static/images/screenshots/week1/sqlserverinstall/screenshot15.jpg)
4. On the License Terms page, check I accept the license terms and click Next.
![screenshot16](../../_static/images/screenshots/week1/sqlserverinstall/screenshot16.jpg)
5. On the Select Features page, make sure everything is selected and click Next.
![screenshot17](../../_static/images/screenshots/week1/sqlserverinstall/screenshot17.jpg)
6. Click through the rest of the wizard. Restart if required.

## Install SQL Server Management Studio
SQL Server Management Studio (SSMS) is used to manage SQL Server and provides a place to write queries. In previous versions, SSMS was installed with SQL Server. In order for Microsoft to provide frequent updates, it is now a separate download. You can find the link from the SQL Server media.
1. Launch the SQL Server Installation Center by double-clicking Setup in the SQL Server installation media.
![screenshot18](../../_static/images/screenshots/week1/sqlserverinstall/screenshot18.jpg)
2. On the Installation page, click Install SQL Server Management Tools.
![screenshot19](../../_static/images/screenshots/week1/sqlserverinstall/screenshot19.jpg)
3. This will launch a page where you can download the latest SSMS file.
![screenshot20](../../_static/images/screenshots/week1/sqlserverinstall/screenshot20.jpg)
4. Double-click the file to launch the installation.
![screenshot21](../../_static/images/screenshots/week1/sqlserverinstall/screenshot21.jpg)
5. Click Install.
![screenshot22](../../_static/images/screenshots/week1/sqlserverinstall/screenshot22.jpg)
6. Restart if required.
