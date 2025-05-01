# Exercise 1: Creating a Fabric Workspace and SQL Database

In this section of the workshop, you will be logging into the Microsoft Fabric Portal, creating a new Fabric Workspace, create SQL Database, and loading sample data in SQL database.

## Task 1: Create the Microsoft Fabric Workspace

1. On the **Microsoft Fabric Home** page, click **+ New workspace** to create a new workspace.

    ![](../images/ex1-1.png)

3. Enter the workspace name as **FabricWorkspace<inject key="DeploymentID"></inject>**, then click or expand **Advanced** to assign the license mode for the Fabric workload.

    ![](../images/png6.png)

4. Choose **Fabric capacity** and select the available Capacity from the dropdown list then click **Apply**. 

    ![](../images/png7.png)

    > **Note:** If a task flows preview feature notification appears, click **Got it** to proceed. 

    ![](../images/ex1-6.png)

## Task 2: Create the Azure SQL Database in Microsoft Fabric

1. On the Microsoft Fabric Workspace page, click the **+ New item** button on the top right of the page.

    ![](../images/ex1-7.png)

1. In the **New item** blade on the right, 

    ![](../images/ex1-8.png)

    use the **Filter by item type search box** in the upper right
    
    ![](../images/ex1-9.png)
    
    to enter **SQL**

    ![](../images/ex1-10.png)

1. With the New item results filtered down, click on the **SQL database (preview)** tile.

    ![](../images/ex1-11.png)

    >Note: There may be a delay after pressing the **SQL database (preview) tile** and when the **New SQL database modal** appears. Just give it a few seconds if it does not appear immediately.

1. In the **New SQL database** dialog window,

    ![](../images/ex1-12.png)

    Use a unique name as **SqlDatabase<inject key="DeploymentID"></inject>** **(1)** and click the green **Create** button.

    ![](../images/ex1-13.png)

1. Once the database is finished creating,

    ![](../images/ex1-14.png)

    you will be taken to that SQL database's home page where we can see database objects and create T-SQL statements right in the web browser.

    ![](../images/ex1-15.png)

## Task 3: Loading the SQL database with sample data

1. We need some sample data in the database to work with. We can easily do this with the **Sample data** tile right on the database home page. Click the **Sample data** tile right on the database home page.

    ![](../images/ex1-16.png)

1. In the upper right corner of the database home page, you will see a notification indicating that the data is being loaded into the database.

    ![](../images/ex1-17.png)

1. Allow this process to run (about 30-60 seconds) until you see a notification in the upper right corner as **Successfully imported sample data** indicating that the data was successfully loaded into the database. 
    
    ![](../images/ex1-18.png)

    > Note: click on the **bell icon** if notification is hidden or not visible.

1. Also, once the data has finished loading, the middle of home page will change show a **Query, preview, or connect your data** message and image.

    ![](../images/ex1-19.png)

### Summary

In this lab, you learned how to create a workspace, create SQL database, and load sample data in SQL database.These steps gave you hands-on experience in setting up Workspace and SQL Database using Microsoft Fabric.

Now, click on **Next** from the lower right corner to move on to the next page.

![](../images/next-page.png)