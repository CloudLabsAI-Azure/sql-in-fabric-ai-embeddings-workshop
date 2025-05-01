# Exercise 2: Working with the Azure SQL Database in Microsoft Fabric

In this exercise, you will explore Azure SQL Database Explorer and SQL Query worksheets in Microsoft Fabric. Also, you will explore copilot integrated with Azure SQL Database Explorer.

## Task 1: Introduction to Azure SQL Database 

This task guides you through navigating the database schema, previewing table data, running SQL queries, and working with query results in Azure SQL Database.

1. In the **Database Explorer** pane on the left, click the dropdown arrow next to **SqlDatabase<inject key="DeploymentID" enableCopy="false"/>>** to expand the database.

    ![](../images/ex2-1.png)

    ![](../images/ex2-2.png)

2. Expand the **SalesLT** schema to view its object types.

    ![](../images/ex2-3.png)

3. Expand the **Tables** folder to see the list of available tables.

    ![](../images/ex2-4.png)

4. Click on the **Address** table to open a **read-only Data preview** in the editor.

    ![](../images/ex2-5.png)

1. You can see in the editor window, a read-only **Data preview** of the contents of the Address table.

    ![](../images/ex2-6.png)

1. After browsing the data in the Address table, close the Data preview by clicking on the **X** next to the **Address Data preview tab**.

    ![](../images/ex2-7.png)

1. Click the **New Query** button from the toolbar to open a new query editor tab.

    ![](../images/ex2-8.png)

2. If a **Copilot Preview Banner** appears, close it by clicking the **X** on the right side of the banner.

    ![](../images/ex2-10.png)

3. Click inside the query editor pane to make it active.

    ![](../images/ex2-9.png)

1. Copy and paste the following SQL statement into the query editor:

    ```
    select * from [SalesLT].[Product]
    ```

2. Click the **Run** button on the toolbar to execute the query.

    ![](../images/ex2-11.png)

3. View the query results displayed in the **Results** section at the bottom of the editor.

    ![](../images/ex2-12.png)

1. After running a query, Azure SQL Database provides multiple options to export the results directly from the **Results** area at the bottom of the query editor:

    - **Download as Excel (.xlsx):** Click the Excel icon to export the results in a Microsoft Excel format.

      ![](../images/ex2-14.png)

    - **Download as CSV (.csv):** Click the CSV icon to download the data in comma-separated values format, suitable for 

      ![](../images/ex2-15.png)

    - **Download as JSON (.json):** Click the JSON icon to export the results as a JSON file, ideal for integration with applications or APIs.

      ![](../images/ex2-16.png)

1. You can also use the **Copy** button on the right side of the results pane to copy data in various formats.

    ![](../media/2025-01-22_9.38.15_AM.png)

1. Refresh the browser by clicking the **refresh** icon on the Edge browser toolbar.

    ![](../images/ex2-17.png)

2. After refreshing, if your query editor is no longer visible, you can reopen it from the **Queries** folder in the **Explorer** pane on the left.

    ![](../images/ex2-18.png)

    ![](../media/2025-02-03_5.49.36_AM.png)

3. Click the query name to reopen it. You can also click the **three dots** beside the name to duplicate, rename, or delete the query tab.

    ![](../images/ex2-19.png)

1. Clear any existing SQL code from the query editor, leaving the editor sheet open and blank.

## **Task 2: Using Copilot with SQL Database in Microsoft Fabric**

Microsoft Copilot in Fabric is an AI-powered assistant designed to simplify and accelerate database tasks by enabling natural language interaction.

### **Copilot Chat Overview**

Copilot supports two primary interaction modes:

- **Natural Language to SQL**  
  Convert plain language questions into valid T-SQL code to query your data—no SQL expertise required.

- **Document-Based Q&A**  
  Ask about general SQL concepts or features; Copilot responds in natural language and may provide relevant documentation links.

1. To use **Copilot chat**, click the **Copilot button** on the Database details homepage toolbar.

    ![](../images/ex2-21.png)

2. This opens the **Copilot Chat pane** on the right-hand side.

   ![](../images/ex2-22.png)

3. Click the **Get started** button at the bottom of the chat pane to begin.  

   ![](../images/ex2-23.png)

1. Let's use one of the suggested questions that the chat pane has offered us. Click the **Get Insights: Retrieve the total number of tables in my database.** button. This will add the text "Retrieve the total number of tables in my database." in the chat box on the bottom of the Chat Pane.

    ![](../images/ex2-24.png)

1. Once the text is in the chat text box, click the **Arrow/Paper Airplane Icon** on the right of the chat text box.

    ![](../images/ex2-25.png)

1. Copilot will process and return an answer, typically including a SQL query.

    ![](../images/ex2-26.png)

    ![](../images/ex2-27.png)

1. You can either click the **Copy Code** button to manually paste the SQL into the query editor, or use the **Insert Code** button to automatically add it to your active query editor tab. 

    ![](../images/ex2-28.png)

    ![](../images/ex2-29.png)

1. Once the code is added to the query editor, click the **Run** button to execute it and view the results. 

    ![](../images/ex2-30.png)

1. Try the following suggested questions in the Copilot chat pane and review the results. You can choose to run the generated SQL in the query editor or simply proceed to the next question.  
 
    > **Note:** Copilot for SQL Database in Microsoft Fabric is currently in **preview**. You may occasionally encounter unexpected results if that happens, try rephrasing the question or move on to the next one.  

    > ![](../media/2025-01-30_9.43.24_AM.png) 

    ### **Performance and Database Questions**

    ```Question
    What table is using the most space?
    ```

    ![](../images/ex2-32.png)

    ```Question
    Are there any poorly performing indexes?
    ```

    ![](../images/ex2-33.png)

    ### **Object Manipulation Questions**

    ```Question
    Help me create a table to store AI chat history and code to insert some sample rows?
    ```

    ![](../images/ex2-34.png)

    ```
    Help me alter the Address table to add a Subdivision column.
    ```

    ![](../images/ex2-35.png)

    ### **Documentation Questions**

    ```Question
    What is an append only ledger table?
    ```

    ![](../images/ex2-36.png)

    ```Question
    Does SQL in fabric support CLR?
    ```

    ![](../images/ex2-37.png)

1. Once you’ve finished exploring the questions, close the **Copilot for SQL** chat window by clicking the **X** in the top-right corner of the pane.

    ![](../images/ex2-38.png)

## Task 3: Using SQL Editor and Quick Actions

In this task, you’ll explore how to use **Copilot in the SQL query editor** within Microsoft Fabric to write, fix, and explain T-SQL queries. You’ll also get hands-on with the **Fix** and **Explain** quick actions available in the editor.

1. In a **new blank SQL query editor tab**, enter the following comment:

    ```text
    -- list the top 5 colors of products
    ```

    ![](../images/ex2-39.png)

1. After typing the comment, **press Enter (or Return)** to move to a new line. At the bottom of the query editor, you should see the message: **Copilot is working on it...**

    ![](../images/ex2-40.png)

1. Back in the query editor, you should see the code Copilot generated for you

    ![](../images/ex2-41.png)

1. You can press tab to Accept the code, or hover over the code with your mouse and click **Accept**.

    ![](../images/ex2-42.png)

1. Once you accept the code, the color will change, indicating the code has been accepted.

    ![](../images/ex2-43.png)

1. You can run it with the **Run** button in the query editor to see the results.

    ![](../images/ex2-44.png)

1. Open another blank query editor tab, try this example (remember to press return/enter after putting the statement in the query editor):

    ```text
    -- show me the top 5 customers with the most orders and their address and the number of orders
    ```

    Copilot should generate a query similar to: (Remember to accept the results or press tab to accept the results):

    ```SQL
    -- show me the top 5 customers with the most orders and their address and the number of orders

    SELECT TOP 5
    C.[CustomerID],
    C.[FirstName],
    C.[LastName],
    A.[AddressLine1],
    A.[City],
    A.[PostalCode],
    COUNT(OD.[SalesOrderID]) AS OrderCount
    FROM [SalesLT].[Customer] AS C
    JOIN [SalesLT].[CustomerAddress] AS CA ON C.[CustomerID] = CA.[CustomerID]
    JOIN [SalesLT].[Address] AS A ON CA.[AddressID] = A.[AddressID]
    JOIN [SalesLT].[SalesOrderHeader] AS OH ON C.[CustomerID] = OH.[CustomerID]
    JOIN [SalesLT].[SalesOrderDetail] AS OD ON OH.[SalesOrderID] = OD.[SalesOrderID]
    GROUP BY C.[CustomerID], C.[FirstName], C.[LastName], A.[AddressLine1], A.[City], A.[PostalCode]
    ORDER BY OrderCount DESC;
    ```

1. Now **delete the number `5`** after `TOP`:

    ![](../images/ex2-45.png)

1. Then, click the **Run** button to execute the SQL query and view the results.

1. An error message should appear at the bottom of the page in the **Messages** pane, stating: **"Msg 102, Level 15, State 1, Line 4, Incorrect syntax near 'C'."**

    ![](../images/ex2-46.png)

1. Back on the query editor toolbar, click the **Fix query errors** button.

    ![](../images/ex2-47.png)

1. Copilot will correct the issue by restoring the missing `5` and will add a comment explaining the fix.

    ![](../images/ex2-48.png)

1. Next, click the **Explain query** button in the toolbar. 

    ![](../images/ex2-49.png)

1. Copilot will annotate your SQL code with comments, describing the purpose and function of each part of the query.

    ![](../images/ex2-50.png)

### Summary

In this exercise, you used the **SQL query editor** in Microsoft Fabric and experienced how **Copilot assists with writing, correcting, and explaining SQL queries**. You also learned how to use **Fix** and **Explain** quick actions effectively.

Now, click on **Next** from the lower right corner to move on to the next page.

![](../images/next-page.png)
