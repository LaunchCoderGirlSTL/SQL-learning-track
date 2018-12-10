# SQL Server Installation

## Installation of SQL Server 2016 Developer Edition
These instructions are meant for learning SQL Server, not for a production installation.
1. This version is available for free when you sign up for Visual Studio Dev Essentials. Once signed up for Dev Essentials, download SQL Server 2016 Dev Edition. There is also a version with Service Pack 1. I had problems getting the file to work, so I recommend starting with the original and applying SP1 as a second step.
2. The SQL Server Developer Edition file is an ISO file. Double-click the file to open it. Double-click the Setup Icon.
![The setup icon is inside that file and is separate from the setup.exe.config file](../../_static/images/screenshots/week1/sqlserverinstall/screenshot1.jpg)
3. The SQL Server Installation Center opens. You can click the Hardware and Software Requirements link to make sure that your system will support SQL Server 2016.
![Hardware and Software Requirements is at the top of SQL Server Installation Center window](../../_static/images/screenshots/week1/sqlserverinstall/screenshot2.jpg)
4. Click Installation on the left and then click New SQL Server stand-alone installation or add features to an existing installation.
![Installation is on the left half of the window and after Installation has been selected, the option for New SQL Server stand-alone installation or add features to an existing installation will become available](../../_static/images/screenshots/week1/sqlserverinstall/screenshot3.jpg)
5. This will kick off the installation wizard. On the Product Key page, make sure that Developer edition is selected and click Next.
![Select Developer edition from the dropdown menu below Specify a free edition](../../_static/images/screenshots/week1/sqlserverinstall/screenshot4.jpg)
6. On the License Terms page, select I accept the license terms and click next.
![I accept the license terms is below the Terms and Conditions](../../_static/images/screenshots/week1/sqlserverinstall/screenshot5.jpg)
7. On the Microsoft Update page, check Use Microsoft Update to check for updates (recommended) if you want updates to be applied automatically and click Next.
![Use Microsoft Update to check for updates (recommended) is the only option on the page](../../_static/images/screenshots/week1/sqlserverinstall/screenshot6.jpg)
8. On the Product Updates page, select Include SQL Server product updates and allow any critical updates to be applied. Click Next when done.
![Include SQL Server product updates is at the top of the window](../../_static/images/screenshots/week1/sqlserverinstall/screenshot7.jpg)
9. On the Feature Selection page, check Database Engine Services and Reporting Services – Native. If there are other features that you are interested in, such as Full Text, you may want to select those as well. Click Next.
![Database Engine Services and Reporting Services - Native are both options in the Features list](../../_static/images/screenshots/week1/sqlserverinstall/screenshot8.jpg)
10. On the Instance Configuration, you will provide an instance name. This is required when multiple instances of SQL Server are installed. MSSQLSERVER is the default. If this must be a named instance, write down the instance name.
![Select Default Instance if the instance does not need to be named and select Named Instance to specify the name of the instance](../../_static/images/screenshots/week1/sqlserverinstall/screenshot9.jpg)
11. On the Server Configuration page, select Grant Perform Volume Maintenance Task privilege to SQL Server Database Engine Service and click Next.
![Grant Perform Volume Maintenance Task privilege to SQL Server Database Engine Service is below the table in the center of the window](../../_static/images/screenshots/week1/sqlserverinstall/screenshot10.jpg)
12. On the Database Engine Configuration page, click Add Current User to add your account to the SQL Server as an administrator. Change to Mixed Mode and fill in a password. Click Next.
![Add Current User is at the bottom of the page and after selected, you can select Mixed Mode in order to type a password into the text field](../../_static/images/screenshots/week1/sqlserverinstall/screenshot11.jpg)
13. Make sure that Install and Configure is selected and click Next.
![Install and Configure is an option below Reporting Services Native Mode](../../_static/images/screenshots/week1/sqlserverinstall/screenshot12.jpg)
14. On the Ready to Install page, click Install.
![When you are ready to install, click the Install button at the bottom of the window](../../_static/images/screenshots/week1/sqlserverinstall/screenshot13.jpg)
15. Once the installation is complete, restart if necessary.

## Installation of Service Pack 1
The service pack is required for fixes and new features. Install Service Pack 1 if the original media did not come with it.
1. Download the [service pack](https://www.microsoft.com/en-us/download) file.
2. Double-click the file.
![The file is called SQLServer2016SP1-KB3182545-x64-ENU](../../_static/images/screenshots/week1/sqlserverinstall/screenshot14.jpg)
3. Wait while the files extract and the installation wizard kicks off.
![The installation window will open with a progress bar](../../_static/images/screenshots/week1/sqlserverinstall/screenshot15.jpg)
4. On the License Terms page, check I accept the license terms and click Next.
![I accept the License terms is below the terms and conditions](../../_static/images/screenshots/week1/sqlserverinstall/screenshot16.jpg)
5. On the Select Features page, make sure everything is selected and click Next.
![Under Instances, there will be multiple options. Please select everything before clicking next.](../../_static/images/screenshots/week1/sqlserverinstall/screenshot17.jpg)
6. Click through the rest of the wizard. Restart if required.

## Install SQL Server Management Studio
SQL Server Management Studio (SSMS) is used to manage SQL Server and provides a place to write queries. In previous versions, SSMS was installed with SQL Server. In order for Microsoft to provide frequent updates, it is now a separate download. You can find the link from the SQL Server media.
1. Launch the SQL Server Installation Center by double-clicking Setup in the SQL Server installation media.
![Setup is inside of the SQL Server Installation folder](../../_static/images/screenshots/week1/sqlserverinstall/screenshot18.jpg)
2. On the Installation page, click Install SQL Server Management Tools.
![Install SQL Server Management Tools is one of the options for Installation](../../_static/images/screenshots/week1/sqlserverinstall/screenshot19.jpg)
3. This will launch a page where you can download the latest SSMS file.
![Select the latest SSMS file from the window that appears](../../_static/images/screenshots/week1/sqlserverinstall/screenshot20.jpg)
4. Double-click the file to launch the installation.
![The file is named SSMS-Setup-ENU](../../_static/images/screenshots/week1/sqlserverinstall/screenshot21.jpg)
5. Click Install.
![Install is at the bottom of the window.](../../_static/images/screenshots/week1/sqlserverinstall/screenshot22.jpg)
6. Restart if required.

## Attach AdventureWorksLT database
This database is used in the EdX course. The available file is an MDF file, which is an actual database file. It will be attached to the SQL Server, not restored.
1. Download the [AdventureWorks2012LT database file](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).
2. Copy the file to this location `C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\DATA` . If you have a named instance, the path will be slightly different. Replace MSSQLSERVER with the instance name.
![If you have done this step correctly, AdventureWorksLT2012_Data.mdf will appear in the DATA folder](../../_static/images/screenshots/week1/sqlserverinstall/screenshot23.jpg)
3. Locate SQL Server Management Studio and run it. You will probably want to create a shortcut in the taskbar or desktop because you will be using this program often.
![You can find SQL Server Management Studio by searching for SSMS in Microsoft 10](../../_static/images/screenshots/week1/sqlserverinstall/screenshot24.jpg)
4. Connect to the instance of SQL Server that you installed and click Connect.
![Make sure that the Server name is correct before hitting Connect](../../_static/images/screenshots/week1/sqlserverinstall/screenshot25.jpg)
5. If you have installed a named instance, you will need to supply the instance name after a backslash.
![You can do so by typing it in after the Server name in the Server name text field.](../../_static/images/screenshots/week1/sqlserverinstall/screenshot26.jpg)
6. The Object Explorer will open on the left. Expand Databases.
![Click on Databases to expand it](../../_static/images/screenshots/week1/sqlserverinstall/screenshot27.jpg)
7. Right-click Databases and select Attach...
![Attach is the second option in the menu that appears when you right-click on Databases](../../_static/images/screenshots/week1/sqlserverinstall/screenshot28.jpg)
8. Click Add on the Attach Databases dialog.
![Add is below the empty window for Databases to attach](../../_static/images/screenshots/week1/sqlserverinstall/screenshot29.jpg)
9. Select the AdventureWorksLT2012_Data.mdf file and click OK.
![The Adventure Works file should appear as an option after you select Add](../../_static/images/screenshots/week1/sqlserverinstall/screenshot30.jpg)
10. Click OK on the Attach Databases dialog. You should see the new database in the Object Explorer window.
![Adventure Works will appear if Databases is expanded.](../../_static/images/screenshots/week1/sqlserverinstall/screenshot31.jpg)

## Restore the AdventureWorks2014 database.
This database is used in the auntkathisql.com exercises as well as many examples and books. It can be downloaded as a backup file which must be restored.
1. Download the [AdventureWorks 2014 Full DatbaseBackup.zip file](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).
![AdventureWorksLT2012_Data.mdf will appear in Downloads](../../_static/images/screenshots/week1/sqlserverinstall/screenshot32.jpg)
2. Extract the file by right-clicking and selecting Extract All.
3. Launch SSMS and connect to your SQL Server.
4. Right-click on Databases and select Restore Database.
![Restore Database is the third option in the menu that appears when you right-click on Databases](../../_static/images/screenshots/week1/sqlserverinstall/screenshot33.jpg)
5. This opens the Restore Database dialog. Select Device and click the ellipsis.
![Ellipsis is the button that appears to the right of the Device button.](../../_static/images/screenshots/week1/sqlserverinstall/screenshot34.jpg)
6. This pops up the Select backup devices dialog. Click Add and navigate to the bak file.
![AdventureWorks2014.bak will in the Adventure Works folder](../../_static/images/screenshots/week1/sqlserverinstall/screenshot35.jpg)
7. Click OK three times to select the files and kick off the restore.
8. Click OK to dismiss the dialog once the restore is complete.
![A popup window will appear after the restoration has been completed](../../_static/images/screenshots/week1/sqlserverinstall/screenshot36.jpg)
9. You should now see the new database in the Object Explorer.
![It will appear after Databases is expanded](../../_static/images/screenshots/week1/sqlserverinstall/screenshot37.jpg)

## Restore the Northwind Database
This is the new sample database. It will be used in some of the homework assignments.
1. Download the [backup file](https://www.microsoft.com/en-us/download/details.aspx?id=23654).
2. Except for unzipping, follow the instructions in the Restore AdventureWorks2014 database
section.

## Installing SQL Server Data Tools
SSDT will be used in the Reporting Services portion of the class.
1. Launch the SQL Server Installation Center by double-clicking Setup in the SQL Server installation media.
![The Setup icon is in the SQL Server folder.](../../_static/images/screenshots/week1/sqlserverinstall/screenshot38.jpg)
2. On the Installation page, click Install SQL Server Data Tools.
![Install SQL Server Data tools is the third option in the Install menu](../../_static/images/screenshots/week1/sqlserverinstall/screenshot39.jpg)
3. This will take you to a download page where you can get the latest version.
![You can click on the latest SSDT in the window that appears](../../_static/images/screenshots/week1/sqlserverinstall/screenshot40.jpg)
4. Double-click the file.
![The file extension is iso and is the only iso file in the folder](../../_static/images/screenshots/week1/sqlserverinstall/screenshot41.jpg)
5. Double-click SSDTSETUP.EXE to launch the installation.
![SSDTSETUP.EXE will appear after the iso file opens](../../_static/images/screenshots/week1/sqlserverinstall/screenshot42.jpg)
6. In this class, we will be working with Reporting Services, but not Analysis Services or Integration Services. You can uncheck those boxes and click Next.
![SQL Server Reporting Services is the only thing that should be selected before you click Next](../../_static/images/screenshots/week1/sqlserverinstall/screenshot43.jpg)
7. Agree to terms and conditions and click Next.
![I agree to the license terms and conditions is below the license](../../_static/images/screenshots/week1/sqlserverinstall/screenshot44.jpg)
8. Restart after the installation if required.
