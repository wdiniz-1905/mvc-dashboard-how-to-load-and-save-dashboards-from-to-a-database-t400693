<!-- default file list -->
*Files to look at*:

* **[DataBaseEditaleDashboardStorage.cs](./CS/MVCDashboardDesigner/DataBaseEditaleDashboardStorage.cs) (VB: [DataBaseEditaleDashboardStorage.vb](./VB/MVCDashboardDesigner/DataBaseEditaleDashboardStorage.vb))**
* [Global.asax.cs](./CS/MVCDashboardDesigner/Global.asax.cs) (VB: [Global.asax.vb](./VB/MVCDashboardDesigner/Global.asax.vb))
<!-- default file list end -->
# MVC Dashboard - How to load and save dashboards from/to a database


This example shows how to create a custom dashboard storage that allows storing dashboards in a data base. It uses the <a href="https://msdn.microsoft.com/en-us/library/system.data.sqlclient(v=vs.110).aspx">System.Data.SqlClient</a> members to connect and operate an MS SQL server data base. <br><br>A custom dashboard storage should implement one of the following interfaces:<strong> IDashboardStorage</strong> or <strong>IEditableDashboardStorage</strong>.<br><br>IDashboardStorage provides functionality to open and edit dashboards available in the storage. <br><strong>XDocument LoadDashboard(string dashboardID) </strong>- returns a dashboard by its ID in the XDocument format, which describes an object model of the dashboard.<br><strong>IEnumerable<DashboardInfo> GetAvailableDashboardsInfo()</strong> - returns a list of IDs and Captions of dashboards available in the data storage.<br><strong>void SaveDashboard(string dashboardID, XDocument dashboard)</strong> - updates the dashboard with new settings by its id.<br><br>IEditableDashboardStorage inherits the IDashboardStorage interface and contains one additional method that allows adding new dashboards to the storage.<br><strong>string AddDashboard(XDocument dashboard, string dashboardName)</strong> - takes a dashboard definition with its caption, saves it to the data storage, and returns the ID of a new saved dashboard.<br><br>Additionally, this example contains an SQL query and data base backup file,  which can be used to recreate a data base used in this example on your side.<br><br>See also: <a href="https://www.devexpress.com/Support/Center/p/T386418"> ASPxDashboard- How to save dashboards to a data base</a>

<br/>


