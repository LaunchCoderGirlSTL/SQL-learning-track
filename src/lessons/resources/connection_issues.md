# Connection Issues

## Cannot connect to SQL Server
 You receive an error message that states that you cannot connect to localhost.
![The error message reads that a network-related or instance-specific error occurred and the server could not be found](../../_static/images/screenshots/week1/connectionissues/screenshot1.jpg)

### Review Configuration Properties
1. Search for a program called **SQL Server 2016 Configuration Manager**. You may want to pin this program to your taskbar.
![Search for SQL Server 2016 Configuration Manager in the Windows taskbar](../../_static/images/screenshots/week1/connectionissues/screenshot2.jpg)
2. If you are asked if it is OK for this program to change settings on your computer, say OK.
3. Click **SQL Server Services** to view the services installed. In my case, they are all shut down.
![SQL Server Services will be an option once the Configuration Manager is open. If the state of a services says it is stopped, that means that service is shut down](../../_static/images/screenshots/week1/connectionissues/screenshot3.jpg)
4. Find the service called **SQL Server (instance name)** in the list. I have two SQL Server instances. You will probably have just one.
![The two options for SQL Server (instance name) have been highlighted](../../_static/images/screenshots/week1/connectionissues/screenshot4.jpg)
5. Notice the names in the parentheses. These are the instance names. When you see MSSQLSERVER, that means the default instance. Anything else if a named instance. If you have a named instance, you will need that information when you connect.

### Start the Server
1. Right-click on the service and select **Start**.
![The service is called SQL Server (instance name) and Start is at the top of the menu](../../_static/images/screenshots/week1/connectionissues/screenshot5.jpg)
2. Once the SQL Server starts up, you should see the red square turn into a green arrow.
![The state of the service will change from stopped to running](../../_static/images/screenshots/week1/connectionissues/screenshot6.jpg)

### Determine the Connection Name
1. To connect to your SQL Server, you need to know the name. For a locally installed instance, you can use one of these instead of the computer name: **localhost**, **(local)**, or . .
2. If you have a named instance, you will need to follow the computer name with a backslash and the instance name.
![For the named instance, it is localhost/name and if it is just default or MSSQLSERVER, it is just localhost](../../_static/images/screenshots/week1/connectionissues/screenshot7.jpg)

### Try Connecting Again
1. To connect to SQL Server, launch **SQL Server Management Studio** (SSMS). Make sure that **Database Engine** and **Windows Authentication** are selected.
![The server name should match the appropriate naming above.](../../_static/images/screenshots/week1/connectionissues/screenshot8.jpg)
![In this case, localhost/SSRS would be more appropriate.](../../_static/images/screenshots/week1/connectionissues/screenshot9.jpg)

### Don't Click ``<Browse for More...>``
1. Avoid clicking this option. It will try to browse for networks to find SQL Servers. It could take a long time.
![Browse for more is an option in the dropdown menu for server name](../../_static/images/screenshots/week1/connectionissues/screenshot10.jpg)

### Change start up properties
1. If you are concerned that SQL Server takes too many resources when you don’t need it, you can change the properties so that it just runs when you need it.
2. Open the **SQL Server Configuration Manager**. Right-click on the service that you don’t want to start up automatically and select **Properties**.
![Properties is below Start in the menu](../../_static/images/screenshots/week1/connectionissues/screenshot11.jpg)
3. On the **Service** tab, change the **Start Mode** to **Manual**.
![Start Mode is below General in the Services tab](../../_static/images/screenshots/week1/connectionissues/screenshot12.jpg)
4. When you want to run SQL Server, you’ll have to launch **Configuration Manager** to start up the service.
