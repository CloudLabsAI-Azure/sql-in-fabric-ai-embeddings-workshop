# Build an AI Application GraphQL Endpoint with SQL DB in Fabric​

# Prerequisites

- Fabric Capacity for SQL Database, Power BI, and Copilot
- An Azure OpenAI Service with the gpt-4 and text-embedding-ada-002 model deployed

# **Starting the workshop**

# 1. The Microsoft Fabric Portal

In this section of the workshop, you will be logging into the Microsoft Fabric Portal and creating a new Fabric Workspace.

## Logging into the Microsoft Fabric Portal

1. Using a web browser, please navigate to +++https://app.fabric.microsoft.com/home?experience=fabric-developer+++.

e **Microsoft Fabric Sign In page** when Edge opens, please navigate to +++https://app.fabric.microsoft.com/home?experience=fabric-developer+++ by typing it in the URL or by using the link in the bookmarks bar.

# 2. Creating a Workspace and SQL Database

## Create the Microsoft Fabric Workspace

1. Back on the Microsoft Fabric Database Home Page, click the **New Workspace tile** to open the **Create a workspace blade** on the right side.

    !IMAGE[A picture of the Microsoft Fabric developer experience Home Page](media/Screenshot 2025-02-06 at 5.32.38 AM.png)

1. In the **Create a workspace blade**, 

    !IMAGE[A picture of the Create a workspace blade on the right side of the page](./media/Screenshot 2025-01-10 at 6.58.17 AM.png)

    double check to make sure the cursor is in the **Name** field 
    
    !IMAGE[A picture of the cursor in the Name field](./media/Screenshot 2025-01-10 at 6.57.04 AM.png){550}
    
    and use the **following text for your Workspace Name**:

    +++FabricWorkspace@lab.LabInstance.Id+++
    
    !IMAGE[A picture of using the supplied text as the workspace name in the name field](./media/Screenshot 2025-01-10 at 6.57.19 AM.png){800}

    > [!Knowledge]
    > Why are we using this name as our Fabric Workspace name? Every workspace needs a unique name and by using your lab instance ID, we can ensure that the name provided is a one of a kind name.

1. Next, click the **green Apply button** on the **bottom left** of the Create a workspace blade.

    !IMAGE[A picture of clicking the **green Apply button** on the **bottom left** of the Create a workspace blade](./media/Screenshot 2025-01-10 at 6.57.38 AM.png){550} 

1. On the following page, you may get a popup titled "Introducing task flows (preview)". Click the green **Got it** button.

    !IMAGE[A picture of clicking the green Got it button to close a feature preview popup](./media/Screenshot 2025-01-10 at 7.08.43 AM.png){500}

## Create the Azure SQL Database in Microsoft Fabric

1. On the Microsoft Fabric Workspace page, click the **New item** button on the top right of the page.

    !IMAGE[A picture of clicking the New item button on the top right of the page](./media/Screenshot 2025-01-10 at 7.13.23 AM.png){550}

1. In the **New item** blade on the right, 

    !IMAGE[A picture of the new item blade on the right of the page](./media/Screenshot 2025-01-10 at 7.16.20 AM.png){800}

    use the **Filter by item type search box** in the upper right
    
    !IMAGE[A picture of using the Filter by item type search box in the upper right of the new item blade](./media/Screenshot 2025-01-10 at 7.18.22 AM.png){300}
    
    to enter **SQL**

    !IMAGE[A picture of entering SQL into the item type search box](./media/Screenshot 2025-01-10 at 7.19.01 AM.png){800}

1. With the New item results filtered down, click on the **SQL database (preview)** tile.

    !IMAGE[A picture of clicking on the SQL database (preview) tile](./media/Screenshot 2025-01-10 at 7.21.40 AM.png){600}

> [!Alert] There may be a delay after pressing the **SQL database (preview) tile** and when the **New SQL database modal** appears. Just give it a few seconds if it does not appear immediately. 

1. In the **New SQL database** dialog window,

    !IMAGE[A picture of the New SQL database dialog window](./media/Screenshot 2025-01-10 at 7.25.02 AM.png){400}

    Use the **following text to name the database**. As a reminder, you can click in the **Name** field on the dialog box (if not already in focus) and then click on the below text to have it entered for you automatically.

    +++sqlDatabase@lab.LabInstance.Id+++

    > [!NOTE]
    > **You will have a different set of numbers after sqlDatabase.** 
    
    !IMAGE[A picture of entering the database name into the New SQL database dialog box](./media/Screenshot 2025-01-10 at 7.30.31 AM.png){400}

1. With the database name entered, click the **green Create button**.

    !IMAGE[A picture of clicking the green Create button in the New SQL database dialog box](./media/Screenshot 2025-01-10 at 7.30.23 AM.png){400}


1. Once the database is finished creating, 

    !IMAGE[A picture of the database creating](./media/Screenshot 2025-01-10 at 7.30.41 AM.png){400}

    you will be taken to that SQL database's home page where we can see database objects and issue T-SQL statements right in the web browser.

    !IMAGE[A picture of the SQL database details home page](./media/Screenshot 2025-01-10 at 7.31.16 AM.png)

## Loading the database with sample data

1. We need some sample data in the database to work with. We can easily do this with the **Sample data** tile right on the database home page. Click the **Sample data** tile right on the database home page.

    !IMAGE[A picture of clicking the Sample data tile right on the database home page](./media/Screenshot 2025-01-10 at 9.35.42 AM.png){700}

1. In the upper right corner of the database home page, you will see a notification indicating that the data is being loaded into the database.

    !IMAGE[A picture of a notification indicating that the data is being loaded into the database](./media/Screenshot 2025-01-10 at 9.37.17 AM.png){400}

1. Allow this process to run (about 30-60 seconds) until you see a notification indicating that the data was successfully loaded into the database appearing again, in the upper right corner.
    
    *Go ahead, check email on your phone...it's ok....*

    !IMAGE[A picture of a notification indicating that the data was successfully loaded into the database](./media/Screenshot 2025-01-10 at 9.38.08 AM.png){400}

1. Also, once the data has finished loading, the middle of home page will change show a **Query, preview, or connect your data** message and image.

    !IMAGE[A picture of the middle of home page changing to show a Query, preview, or connect your data message and image](./media/Screenshot 2025-02-06 at 5.41.58 AM.png){700}

# 3. Working with the Azure SQL Database in Microsoft Fabric

In this next section, we will be using the Database Explorer and SQL Query worksheets in Microsoft Fabric

> [!Hint] The numbers after the database name "sqlDatabase" in the following images will be different from yours.

1. To start, look at the **Database Explorer** area on the left of the page. Here, click the dropdown arrow next to the database 

    !IMAGE[A picture of the Database Explorer area on the left of the SQL database details page](./media/Screenshot 2025-01-10 at 9.43.09 AM.png){400}

    to see a list of database schemas.

    !IMAGE[A picture of a list of database schemas in the newly created database](./media/Screenshot 2025-01-10 at 9.45.41 AM.png){300}

    and you can further expand the **SalesLT** schema to see object types

    !IMAGE[A picture of expanding the SalesLT schema to see object types](./media/Screenshot 2025-01-10 at 9.47.35 AM.png){300}

    as well as objects in the object type folders.

    !IMAGE[A picture of expanding the tables folder to see all the tables in the SalesLT database schema](./media/Screenshot 2025-01-10 at 9.47.50 AM.png){300}

1. If not already done, expand the **SalesLT** schema, followed by expanding the **Tables** folder. Then click on the **Address** table.

    !IMAGE[A picture of expanding the SalesLT schema, followed by expanding the Tables folder, then clicking on the Address table](./media/Screenshot 2025-01-10 at 9.50.08 AM.png){300}

1. You can see in the editor window, a read only **Data preview** of the contents of the Address table.

    !IMAGE[A picture of a read only data preview of the Address table](./media/Screenshot 2025-01-10 at 9.50.18 AM.png)

1. After browsing the data in the Address table, **close** the Data preview by clicking on the **X** next to the **Address Data preview tab**.

    !IMAGE[A picture of closing the Data preview by clicking on the X next to the Address Data preview tab](./media/Screenshot 2025-01-10 at 9.54.22 AM.png){600}

1. Now, click the **New Query** button on the tool bar
    
    !IMAGE[A picture of clicking the New Query button on the tool bar](./media/Screenshot 2025-01-10 at 9.57.20 AM.png){700}

    to open a new query editor window so we can work directly with the database. 

    !IMAGE[A picture of opening a new query editor window so one can work directly with the database](./media/Screenshot 2025-01-10 at 10.00.59 AM.png){800}

1. To remove the gray **Copilot Preview Banner**, click the X on the right side.

    !IMAGE[A picture of removing the gray Copilot Preview Banner by clicking the X on the right side](./media/Screenshot 2025-01-22 at 9.02.50 AM.png){700}

1. Once the banner is gone, be sure to click in the SQL editor sheet so that the next step will copy the code to the correct location.

    !IMAGE[A picture of clicking in the SQL editor sheet so that the next step will copy the code to the correct location](./media/Screenshot 2025-01-10 at 10.00.59 AMw.png){600}

1. Copy and paste the following code into the query editor:

    ```
    select * from [SalesLT].[Product]
    ```

1. Once the code is in the query editor, **click the Run button**.

    !IMAGE[A picture of clicking the run button in the query editor](./media/Screenshot 2025-01-10 at 10.13.01 AM.png){500}

1. You will see the **results** of the query on the **bottom of the query editor**.

    !IMAGE[A picture of the results of the query on the bottom of the query editor](./media/Screenshot 2025-01-10 at 10.17.25 AM.png){800}

1. Starting on the left side of the **Results area**, there are 3 options for exporting the data.

    !IMAGE[A picture of the 3 options for exporting the data in the results area](./media/Screenshot 2025-01-27 at 5.20.34 AM.png){700}

1. From left to right, first is **download results as .xlsx (Excel) file**.

    !IMAGE[A picture of the download results as .xlsx (Excel) file option](./media/Screenshot 2025-01-27 at 5.20.47 AM.png){600}

1. Next, is **download as a .csv file**

    !IMAGE[A picture of the download as a .csv file option](./media/Screenshot 2025-01-27 at 5.20.57 AM.png){500}

1. With the last option being **download as a .json file**.

    !IMAGE[A picture of the download as a .json file option](./media/Screenshot 2025-01-27 at 5.21.06 AM.png){500}

1. And looking at the right side of the results area, you can use the **Copy** button to copy the results in multiple formats.

    !IMAGE[A picture of using the Copy button to copy the results in multiple formats](./media/Screenshot 2025-01-22 at 9.38.15 AM.png){700}

1. Now, **refresh the browser page** by clicking the refresh icon on the Edge Browser toolbar.

    !IMAGE[A picture of clicking the refresh icon on the Edge Browser toolbar](./media/Screenshot 2025-02-03 at 5.45.31 AM.png){600}

1. The query editor you were working with is no longer in the main window

    !IMAGE[A picture showing the query editor you were working with is no longer in the main window](./media/Screenshot 2025-02-03 at 5.47.44 AM.png){600}

    but we can easily bring it back, or any other query editors we have been working with. We can do this by **clicking on the editor sheet name in Explorer** on the left side of the page in the **Queries folder**.

    !IMAGE[A picture of clicking on the editor sheet name in Explorer on the left side of the page in the Queries folder](./media/Screenshot 2025-02-03 at 5.49.36 AM.png){600}

1. Also, by **clicking on the 3 dots** next to a query editor sheet name, you can duplicate it, rename it, or delete it.

    !IMAGE[A picture of clicking on the 3 dots next to a query editor sheet name](./media/Screenshot 2025-02-03 at 5.52.28 AM.png){400}

1. To get ready for the next section, **Delete** any SQL you have in **the query editor** so that it is blank. Do not delete the entire query sheet.

    !IMAGE[A picture of a blank query editor because all the code was deleted from it](./media/Screenshot 2025-01-30 at 9.38.23 AM.png){600}

## Copilot for the SQL Database in Microsoft Fabric

Microsoft Copilot for SQL database in Fabric is an AI assistant designed to streamline your database tasks.

### Copilot Chat

Use the chat pane to ask questions to Copilot through natural language. Copilot responds with a generated SQL query or natural language based on the question asked. 

- **Natural Language to SQL:** Generate T-SQL code from plain text requests, allowing users to query data without needing to know SQL syntax. 
- **Document-based Q&A:** Ask Copilot questions about general SQL database capabilities, and it responds in natural language. Copilot also helps find documentation related to your request.

1. To use **Copilot chat**, click the **Copilot button** on the Database details homepage toolbar.

    !IMAGE[A picture of clicking the Copilot button on the Database details homepage toolbar](./media/Screenshot 2025-01-22 at 9.07.30 AM.png){650}

1. On the right side of the page, you will see the **Copilot Chat pane**.

    !IMAGE[A picture of the Copilot Chat pane](./media/Screenshot 2025-01-21 at 1.17.36 PM copy.png){300}

    click the **green Get started button** on the bottom of the chat pane to continue.

    !IMAGE[A picture of clicking the green Get started button on the bottom of the chat pane to continue](./media/Screenshot 2025-01-21 at 1.17.36 PM.png){300}

1. Let's use one of the suggested questions that the chat pane has offered us. Click the **Get Insights: Retrieve the total number of tables in my database.** button. This will add the text "Retrieve the total number of tables in my database." in the chat box on the bottom of the Chat Pane.

    !IMAGE[A picture of clicking the Get Insights: Retrieve the total number of tables in my database suggested query](./media/Screenshot 2025-01-21 at 1.31.37 PM.png){300}

1. Once the text is in the chat text box, click the **Arrow/Paper Airplane Icon** on the right of the chat text box.

    !IMAGE[A picture of clicking the Arrow/Paper Airplane Icon on the right of the chat text box](./media/Screenshot 2025-01-21 at 1.38.21 PM.png){400}

    and Copilot will start answering the question

    !IMAGE[A picture of copilot working on the answer with an animated color bar](./media/Screenshot 2025-01-21 at 1.40.11 PM.png){400}

1. Once the answer is returned by Copilot,

    !IMAGE[A picture of copilot returning the answer and SQL](./media/Screenshot 2025-01-21 at 1.42.24 PM.png){400}

    you can either **click the copy code button** and paste it into the query editor

    !IMAGE[A picture of clicking the copy code button and pasting it into the query editor](./media/Screenshot 2025-01-21 at 1.43.45 PM.png){400}

    or click the **insert code button** to have it instantly pasted into the current active query editor sheet.

    !IMAGE[A picture of clicking the insert code button having it instantly pasted into the current active query editor sheet](./media/Screenshot 2025-01-21 at 1.45.33 PM.png){400}

1. Once the code is copied into the query editor, you **click the run button** it to see the results.

    !IMAGE[A picture of clicking the run button in the query editor](./media/Screenshot 2025-01-21 at 1.47.02 PM.png){500}

1. Try the following question suggestions in the chat pane and see the results. Feel free to run the SQL it provides from the answers or just move on to the next question:

    > [!Knowledge] Copilot for SQL database in Microsoft Fabric is in **preview** and you may encounter unexpected results. If so, try the question again or move on to the next question.
    > !IMAGE[A picture of Copilot for SQL database encountering unexpected results](./media/Screenshot 2025-01-30 at 9.43.24 AM.png){300} 

    ##### **Performance and Database Questions**

    ```Question
    What table is using the most space?
    ```

    !IMAGE[A picture of asking copilot what is the biggest table in my database](./media/Screenshot 2025-01-22 at 9.13.42 AM.png){400}

    ```Question
    Are there any poorly performing indexes?
    ```

    !IMAGE[A picture of asking copilot Are there any poorly performing indexes](./media/Screenshot 2025-01-22 at 9.13.55 AM.png){400}

    ##### **Object Manipulation Questions**

    ```Question
    Help me create a table to store AI chat history and code to insert some sample rows?
    ```

    !IMAGE[A picture of asking copilot to Help me create a table to store AI chat history and code to insert some sample rows](./media/Screenshot 2025-01-22 at 9.14.15 AM.png){400}

    ```
    Help me alter the Address table to add a Subdivision column.
    ```

    !IMAGE[A picture of asking copilot to Help me alter the Address table to add a Subdivision column](./media/Screenshot 2025-01-22 at 9.14.29 AM.png){400}

    ##### **Documentation Questions**

    ```Question
    What is an append only ledger table?
    ```

    !IMAGE[A picture of asking copilot What is an append only ledger table](./media/Screenshot 2025-01-22 at 9.14.42 AM.png){400}

    ```Question
    Does SQL in fabric support CLR?
    ```

    !IMAGE[A picture of asking copilot Does SQL in fabric support CLR](./media/Screenshot 2025-01-22 at 9.14.58 AM.png){400}

1. When done with the questions, you can **close the Copilot for SQL chat window** using the **X on the top right**.

    !IMAGE[A picture of closing the Copilot for SQL chat window** using the X on the top right](./media/Screenshot 2025-02-06 at 5.57.10 AM.png){400}

### SQL Editor and Quick Actions

Start writing T-SQL in the SQL query editor and Copilot will automatically generate a code suggestion to help complete your query. The Tab key accepts the code suggestion or keeps typing to ignore the suggestion.

In the ribbon of the SQL query editor, the Fix and Explain options are quick actions. Highlight a SQL query of your choice and select one of the quick action buttons to perform the selected action on your query.

- **Fix:** Copilot can fix errors in your code as error messages arise. Error scenarios can include incorrect/unsupported T-SQL code, wrong spellings, and more. Copilot will also provide comments that explain the changes and suggest SQL best practices.
- **Explain:** Copilot can provide natural language explanations of your SQL query and database schema in comments format.

1. In an empty query editor, copy and paste the following code.

    ```text
    -- list the top 5 colors of products
    ```

    !IMAGE[A picture of pasting -- list the top 5 colors of products into the query editor](./media/Screenshot 2025-01-21 at 1.52.07 PM.png){800}

1. Then **press enter/return at the end of the line of text** in the query editor. On the bottom of the query editor, you should see that **"Copilot is working on it..."***

    !IMAGE[A picture of pressing enter/return at the end of the line of text you just pasted in](./media/Screenshot 2025-01-21 at 1.53.27 PM.png){300}

1. Back in the query editor, you should see the code Copilot generated for you

    !IMAGE[A picture of code Copilot generated](./media/Screenshot 2025-01-21 at 1.53.43 PM.png){400}

1. You can press tab to accept the code or hover over the code with your mouse and click accept.

    !IMAGE[A picture of pressing tab to accept the code or hovering over the code with your mouse and clicking accept](./media/Screenshot 2025-01-21 at 1.53.58 PM.png){400}

1. Once you accept the code, the color will change indicating the code has been accepted

    !IMAGE[A picture of the color changing indicating the code has been accepted](./media/Screenshot 2025-01-21 at 1.54.12 PM.png){400}

    and you can run it with the run button in the query editor to see the results.

    !IMAGE[A picture of running the code with the run button in the query editor to see the results](./media/Screenshot 2025-01-21 at 1.59.52 PM.png){500}

1. In an **empty query editor sheet**, try this example (remember to press return/enter after putting the statement in the query editor):

    ```text
    -- show me the top 5 customers with the most orders and their address and the number of orders
    ```

    it should provide you with code similar to the following (Remember to accept the results or press tab to accept the results):

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

1. Now, delete the **5 after the word TOP in the first line of code**. 

    !IMAGE[A picture showing the 5 deleted in the query](./media/Screenshot 2025-02-06 at 5.53.26 AM.png){400}

    Then use the run button to execute the SQL query.

1. You should get an error on the bottom of the page in the messages pane stating "Msg 102, Level 15, State 1, Line 4, Incorrect syntax near 'C'."

    !IMAGE[A picture of an error on the bottom of the page in the messages pane stating Msg 102, Level 15, State 1, Line 4, Incorrect syntax near C](./media/Screenshot 2025-02-06 at 5.55.18 AM.png){700}

1. Back on the query editor toolbar. click the **Fix query errors** button.

    !IMAGE[A picture of clicking the Fix query errors button](./media/Screenshot 2025-01-21 at 2.05.02 PM.png){500}

1. You will see that it added back the 5 and notated the error with how it fixed it.

    !IMAGE[A picture of the query being fixed and an annotation on what it did](./media/Screenshot 2025-01-21 at 2.07.02 PM.png){600}

1. Next, click the **Explain query button** on the query editor toolbar.

    !IMAGE[A picture of clicking the Explain query button on the query editor toolbar](./media/Screenshot 2025-01-21 at 2.08.56 PM.png){500}

1. This option annotates your code for you adding comments outlining the purpose/function of each section.

    !IMAGE[A picture of the code being annotated automatically for you](./media/Screenshot 2025-01-21 at 2.11.52 PM.png){600}

# 4. Call REST services from the Azure SQL Database in Microsoft Fabric with External REST Endpoint Invocation

## External REST Endpoint Invocation

Azure SQL Database External REST Endpoint Invocation provides the ability to call REST endpoints from other Azure services such as OpenAI, Azure Event Hub, Azure Functions, Power BI and more. Common use cases for developers to use External REST Endpoint Invocation are:

* Utilize Azure OpenAI services such as chat, embeddings, language, and content safety
* Ability to push business logic out of the database and into Azure Functions
* Pull/push data to/from external sources (including Azure Blob Storage) for ETL or derived data stores
* Participate in event-based architectures with Azure Event Hub or Kafka

External REST Endpoint Invocation can be called in an Azure SQL Database using the sp_invoke_external_rest_endpoint stored procedure.

## Getting started with REST in the Azure SQL Database

In this first section, you will test the External REST Endpoint Invocation (EREI) feature of the database to ensure you have connectivity to other Azure services by asking ChatGPT for a joke. This section will also create a database scoped credential. A database scoped credential is a record in the database that contains authentication information for connecting to a resource outside the database. For this lab, we will be creating one that contains the api key for connecting to Azure OpenAI services.

### Using T-SQL to check connectivity to Azure OpenAI and creating database scoped credentials

#### Chat Completion

1. Back in the query sheet, **remove the previous code** by highlighting it and pressing delete/backspace.

1. Using an empty query sheet in Microsoft Fabric, copy and paste the following code:

    ```SQL

    -- Create a master key for the database
    if not exists(select * from sys.symmetric_keys where [name] = '##MS_DatabaseMasterKey##')
    begin
        create master key encryption by password = N'V3RYStr0NGP@ssw0rd!';
    end
    go

    -- Create the database scoped credential for Azure OpenAI
    if not exists(select * from sys.database_scoped_credentials where [name] = 'https://AI_ENDPOINT_SERVERNAME.openai.azure.com/')
    begin
        create database scoped credential [https://AI_ENDPOINT_SERVERNAME.openai.azure.com/]
        with identity = 'HTTPEndpointHeaders', secret = '{"api-key":"YOUR_OPENAI_KEY"}';
    end
    go
    ```

1. Then click the run button on the query sheet

    !IMAGE[A picture of clicking the run button on the query sheet](./media/Screenshot 2025-01-10 at 11.16.00 AM.png){900}

    The master key will be set, and the database scoped credential will be created.

1. Back in the query sheet, **remove the previous code** by highlighting it and pressing delete/backspace.

1. Let's test the **connectivity to Azure OpenAI** and see the ability to call external REST endpoints in action. Copy and paste the following code into a blank query editor in Microsoft Fabric:

    ```SQL
    declare @url nvarchar(4000) = N'https://AI_ENDPOINT_SERVERNAME.openai.azure.com/openai/deployments/gpt-4/chat/completions?api-version=2024-06-01';
    declare @payload nvarchar(max) = N'{"messages":[{"role":"system","content":"You are an expert joke teller."},                                   
                                       {"role":"system","content":"tell me a joke about a llama walking into a bar"}]}'
    declare @ret int, @response nvarchar(max);

    exec @ret = sp_invoke_external_rest_endpoint
        @url = @url,
        @method = 'POST', 
        @payload = @payload,
        @credential = [https://AI_ENDPOINT_SERVERNAME.openai.azure.com/],    
        @timeout = 230,
        @response = @response output;
        
    select json_value(@response, '$.result.choices[0].message.content') as "Amazing, Awesome, Stupendous Joke";
    ```

1. Click the run button on the query sheet. The result will be an amazing joke you can tell your friends and family!

    !IMAGE[A picture of running the T-SQL to create a llama bar joke](./media/Screenshot 2025-01-10 at 11.20.25 AM.png){1000}

    **Question:** tell me a joke about a llama walking into a bar.
    
    **Response:** A llama walks into a bar and the bartender says, "Hey, why the long face?" The llama replies, "I'm just here to meet my alpaca friend, he always packs the good jokes!"

    Classic alpaca joke.

1. Next, we can use AI Translation and Content Safety.

#### AI Content Safety

1. Lets start with Content Safety. Copy and paste the following code into a blank query editor in Microsoft Fabric:

    ```SQL
    -- Create the database scoped credential for Azure AI Content Safety
    if not exists(select * from sys.database_scoped_credentials where [name] = 'CONTENT_SAFETY_ENDPOINT_SERVERNAME')
    begin
        create database scoped credential [CONTENT_SAFETY_ENDPOINT_SERVERNAME]
        with identity = 'HTTPEndpointHeaders', secret = '{"Ocp-Apim-Subscription-Key":"YOUR_OPENAI_KEY","Ocp-Apim-Subscription-Region":"YOUR_OPENAI_REGION"}';
    end
    go
    ```

1. Then click the run button on the query sheet.

1. Using the following code, we can use the Text Analysis feature of Azure AI Content Safety. Copy and paste the following code into a blank query editor in Microsoft Fabric:

    ```SQL
    declare @url nvarchar(4000) = N'CONTENT_SAFETY_ENDPOINT_SERVERNAME/contentsafety/text:analyze?api-version=2024-09-01';
    declare @payload nvarchar(max) = N'{"text": "I want to kill all the ant in the house!"}';    
    declare @ret int, @response nvarchar(max);

    exec @ret = sp_invoke_external_rest_endpoint
         @url = @url,
         @method = 'POST',
         @payload = @payload,
         @credential = [CONTENT_SAFETY_ENDPOINT_SERVERNAME],
         @timeout = 230,
         @response = @response output;

    SELECT JSON_VALUE(D.[value],'$.category') as "Category",
        JSON_VALUE(D.[value],'$.severity') as "Severity"
        FROM OPENJSON(@response,'$.result.categoriesAnalysis') AS D
    ```
1. Then click the run button on the query sheet.

1. Content Safety also can check to see if a string of text is protected or copyrighted. Copy and paste the following code into a blank query editor in Microsoft Fabric:

    ```SQL
    declare @url nvarchar(4000) = N'CONTENT_SAFETY_ENDPOINT_SERVERNAME/contentsafety/text:detectProtectedMaterial?api-version=2024-09-01';
    declare @payload nvarchar(max) = N'{"text":"The people were delighted, coming forth to claim their prize They ran to build their cities and converse among the wise But one day, the streets fell silent, yet they knew not what was wrong The urge to build these fine things seemed not to be so strong The wise men were consulted and the Bridge of Death was crossed In quest of Dionysus to find out what they had lost"}';
    declare @ret int, @response nvarchar(max);

    exec @ret = sp_invoke_external_rest_endpoint
         @url = @url,
         @method = 'POST',     
         @payload = @payload,     
         @credential = [CONTENT_SAFETY_ENDPOINT_SERVERNAME],     
         @timeout = 230,     
         @response = @response output;
         
         select json_value(@response, '$.result.protectedMaterialAnalysis.detected') as "Protected Material Analysis";
    ```

#### AI Translation

1. Now, lets try the Translation service. Copy and paste the following code into a blank query editor in Microsoft Fabric:

    ```SQL
    -- Create the database scoped credential for Azure AI Translation
    if not exists(select * from sys.database_scoped_credentials where [name] = 'https://api.cognitive.microsofttranslator.com/')
    begin
        create database scoped credential [https://api.cognitive.microsofttranslator.com/]
        with identity = 'HTTPEndpointHeaders', secret = '{"Ocp-Apim-Subscription-Key":"YOUR_OPENAI_KEY","Ocp-Apim-Subscription-Region":"YOUR_OPENAI_REGION"}';
    end
    go
    ```

1. Then click the run button on the query sheet.

1. We can now try the translation services using a product description from the sample database data we just loaded. Copy and paste the following code into a blank query editor in Microsoft Fabric:

    ```SQL
    declare @url nvarchar(4000) = N'https://api.cognitive.microsofttranslator.com/translate?api-version=3.0&from=en&to=es';
    declare @message nvarchar(max);    
    SET @message = (SELECT [Description] FROM [SalesLT].[ProductDescription] WHERE ProductDescriptionID = 457);
    declare @payload nvarchar(max) = N'[{"Text": "'+ @message +'"}]';    
    declare @ret int, @response nvarchar(max);

    exec @ret = sp_invoke_external_rest_endpoint
         @url = @url,
         @method = 'POST',
         @payload = @payload,
         @credential = [https://api.cognitive.microsofttranslator.com/],
         @timeout = 230,
         @response = @response output;

    select json_value(@response, '$.result[0].translations[0].text') as "Translation";
    ```

1. Then click the run button on the query sheet.

1. AI Translation can also perform **transliteration**; the conversion of a text from one script to another. In this example, we will be taking Japanese Hiragana and converting it to Latin characters.

    ```SQL
    declare @url nvarchar(4000) = N'https://api.cognitive.microsofttranslator.com/transliterate?api-version=3.0&language=ja&fromScript=jpan&toScript=latn';    
    declare @message nvarchar(max);      
    declare @payload nvarchar(max) = N'[{"Text": "こんにちは"}]';    
    declare @ret int, @response nvarchar(max);
    
    exec @ret = sp_invoke_external_rest_endpoint        
         @url = @url,        
         @method = 'POST',         
         @payload = @payload,        
         @credential = [https://api.cognitive.microsofttranslator.com/],           
         @timeout = 230,        
         @response = @response output;    
          
    select json_value(@response, '$.result[0].text') as "Translation";
    ```

# 5. Creating embeddings for relational data

## Understanding embeddings in Azure OpenAI

An embedding is a special format of data representation that machine learning models and algorithms can easily use. The embedding is an information dense representation of the semantic meaning of a piece of text. Each embedding is a vector of floating-point numbers. Vector embeddings can help with semantic search by capturing the semantic similarity between terms. For example, "cat" and "kitty" have similar meanings, even though they are spelled differently. 

Embeddings created and stored in the Azure SQL Database in Microsoft Fabric during this lab will power a vector similarity search in a chat app you will build.

## The Azure OpenAI embeddings endpoint

1. Using an empty query sheet in Microsoft Fabric, copy and paste the following code. This code calls an Azure OpenAI embeddings endpoint. The result will be a JSON array of vectors.

    ```SQL
    declare @url nvarchar(4000) = N'https://AI_ENDPOINT_SERVERNAME.openai.azure.com/openai/deployments/text-embedding-ada-002/embeddings?api-version=2024-06-01';
    declare @message nvarchar(max) = 'Hello World!';
    declare @payload nvarchar(max) = N'{"input": "' + @message + '"}';

    declare @ret int, @response nvarchar(max);

    exec @ret = sp_invoke_external_rest_endpoint 
        @url = @url,
        @method = 'POST',
        @payload = @payload,
        @credential = [https://AI_ENDPOINT_SERVERNAME.openai.azure.com/],
        @timeout = 230,
        @response = @response output;

    select json_query(@response, '$.result.data[0].embedding') as "JSON Vector Array";
    ```

1. Again, click the run button on the query sheet. The result will be a JSON vector array.

    !IMAGE[A picture of the JSON vector array as a result of the query](./media/Screenshot 2025-01-10 at 11.25.57 AM.png){1200}

    Using the built in JSON function json_query, we are able to extract JSON array from REST response payloads. In the above T-SQL, **json_query(@response, '$.result.data[0].embedding') as "JSON Vector Array"** will extract the vector array from the result payload returned to us from the Azure OpenAI REST endpoint. 
    
    For reference, the JSON response message from the Azure OpenAI embeddings endpoint will look similar to the following and, you can see how we extract the array found at **$.result.data[0].embedding**.

    > [!TIP]
    > **This code is for reference only** 

    ```JSON-nocopy
    {
        "response": {
            "status": {
                "http": {
                    "code": 200,
                    "description": ""
                }
            },
            "headers": {
                "Date": "Thu, 24 Oct 2024 19:32:59 GMT",
                "Content-Length": "33542",
                "Content-Type": "application/json",
                "access-control-allow-origin": "*",
                "apim-request-id": "ac67032f-41c1-4ec3-acc6-3f697c262764",
                "strict-transport-security": "max-age=31536000; includeSubDomains; preload",
                "x-content-type-options": "nosniff",
                "x-ms-region": "West US",
                "x-request-id": "84baf32d-f1f7-4183-9403-a95365d01a3e",
                "x-ms-client-request-id": "ac67032f-41c1-4ec3-acc6-3f697c262764",
                "x-ratelimit-remaining-requests": "349",
                "azureml-model-session": "d007-20240925154241",
                "x-ratelimit-remaining-tokens": "349994"
            }
        },
        "result": {
            "object": "list",
            "data": [
                {
                    "object": "embedding",
                    "index": 0,
                    "embedding": [
                        0.0023929428,
                        0.00034713413,
                        -0.0023142276,
                        -0.025654867,
                        -0.011492423,
                        0.0010358924,
                        -0.014836246,
                        0.0035484824,
                        0.000045630233,
                        -0.027581815,
                        0.023816079,
                        0.005012586,
                        -0.027732948,
                        -0.010088143,
                        ...
                        -0.014571763
                    ]
                }
            ],
            "model": "text-embedding-ada-002",
            "usage": {
                "prompt_tokens": 3,
                "total_tokens": 3
            }
        }
    }
    ```

    This JSON vector array can now be used with new vector datatype and functions in the Azure SQL database such as VECTOR_DISTANCE. 

## Preparing the database and creating embeddings

This next section of the lab will have you alter the Adventure Works product table to add a new vector datatype column. You will then use a stored procedure to create embeddings for the products and store the vector arrays in that column.

1. In a new query sheet or an existing bank one in VS Code, copy and paste the following T-SQL:

    ```SQL
    alter table [SalesLT].[Product]
    add  embeddings VECTOR(1536), chunk nvarchar(2000);
    ```

    this code adds a vector datatype column to the Product table. It also adds a column named chunk where we will store the text we send over to the embeddings REST endpoint.

1. Then click the run button on the query sheet

    !IMAGE[A picture of clicking the run button on the query sheet for adding 2 columns to the product table](./media/Screenshot 2025-01-10 at 1.30.19 PM.png){800}

1. Next, we are going to use the External REST Endpoint Invocation procedure (sp_invoke_external_rest_endpoint) to create a stored procedure that will create embeddings for text we supply as an input. Copy and paste the following code into a blank query editor in Microsoft Fabric:

    ```SQL
    create or alter procedure dbo.create_embeddings
    (
        @input_text nvarchar(max),
        @embedding vector(1536) output
    )
    AS
    BEGIN
    declare @url varchar(max) = 'https://AI_ENDPOINT_SERVERNAME.openai.azure.com/openai/deployments/text-embedding-ada-002/embeddings?api-version=2024-06-01';
    declare @payload nvarchar(max) = json_object('input': @input_text);
    declare @response nvarchar(max);
    declare @retval int;

    -- Call to Azure OpenAI to get the embedding of the search text
    begin try
        exec @retval = sp_invoke_external_rest_endpoint
            @url = @url,
            @method = 'POST',
            @credential = [https://AI_ENDPOINT_SERVERNAME.openai.azure.com/],
            @payload = @payload,
            @response = @response output;
    end try
    begin catch
        select 
            'SQL' as error_source, 
            error_number() as error_code,
            error_message() as error_message
        return;
    end catch
    if (@retval != 0) begin
        select 
            'OPENAI' as error_source, 
            json_value(@response, '$.result.error.code') as error_code,
            json_value(@response, '$.result.error.message') as error_message,
            @response as error_response
        return;
    end
    -- Parse the embedding returned by Azure OpenAI
    declare @json_embedding nvarchar(max) = json_query(@response, '$.result.data[0].embedding');

    -- Convert the JSON array to a vector and set return parameter
    set @embedding = CAST(@json_embedding AS VECTOR(1536));
    END;
    ```

1. Click the run button on the query sheet to create the procedure in the database.

1. We have our embeddings procedure, now we can use it with data from the various products table. We are taking descriptive elements from each product and concatenating them into a single string to send to the embeddings endpoint. We construct this text string with the following SQL:

    > [!TIP]
    > **This code is for reference only** 

    ```SQL-nocopy
    SELECT p.Name + ' '+ ISNULL(p.Color,'No Color') + ' '+  c.Name + ' '+  m.Name + ' '+  ISNULL(d.Description,'')
    FROM 
        [SalesLT].[ProductCategory] c,
        [SalesLT].[ProductModel] m,
        [SalesLT].[Product] p
        LEFT OUTER JOIN
        [SalesLT].[vProductAndDescription] d
            on p.ProductID = d.ProductID
            and d.Culture = 'en'
    where p.ProductCategoryID = c.ProductCategoryID
    and p.ProductModelID = m.ProductModelID
    and p.ProductID = @ProductID
    ```
    
    Looking at the SQL, the text we are embedding contains the product name, product color (if available), the category name the product belongs to, the model name of the product, and the description of the product.

    > [!Hint]
    > **Seeing you are now familiar with how to copy, paste, and run SQL in the Query Editor in Visual Studio Code, when the instructions say, "Run this in a blank query editor", it is referring to the process of copying, pasting, and running the code.**
    >
    >**If you have questions, please raise your hand or ask a proctor or speaker in the room** 


1. Run the following T-SQL in a blank query editor in Microsoft Fabric to create embeddings for all products in the Products table:

    > [!Knowledge]
    > **This code will take 30 to 60 seconds to run** 

    ```SQL
    SET NOCOUNT ON
    DROP TABLE IF EXISTS #MYTEMP 
    DECLARE @ProductID int
    declare @text nvarchar(max);
    declare @vector vector(1536);
    SELECT * INTO #MYTEMP FROM [SalesLT].Product
    SELECT @ProductID = ProductID FROM #MYTEMP
    SELECT TOP(1) @ProductID = ProductID FROM #MYTEMP
    WHILE @@ROWCOUNT <> 0
    BEGIN
        set @text = (SELECT p.Name + ' '+ ISNULL(p.Color,'No Color') + ' '+  c.Name + ' '+  m.Name + ' '+  ISNULL(d.Description,'')
                        FROM 
                        [SalesLT].[ProductCategory] c,
                        [SalesLT].[ProductModel] m,
                        [SalesLT].[Product] p
                        LEFT OUTER JOIN
                        [SalesLT].[vProductAndDescription] d
                        on p.ProductID = d.ProductID
                        and d.Culture = 'en'
                        where p.ProductCategoryID = c.ProductCategoryID
                        and p.ProductModelID = m.ProductModelID
                        and p.ProductID = @ProductID);
        exec dbo.create_embeddings @text, @vector output;
        update [SalesLT].[Product] set [embeddings] = @vector, [chunk] = @text where ProductID = @ProductID;
        DELETE FROM #MYTEMP WHERE ProductID = @ProductID
        SELECT TOP(1) @ProductID = ProductID FROM #MYTEMP
    END
    ```

1. To ensure all the embeddings were created, run the following code in a blank query editor in Microsoft Fabric: 

    ```SQL
    select count(*) from SalesLT.Product where embeddings is null;
    ```

    You should get 0 for the result.

1. Run the next query in a blank query editor in Microsoft Fabric to see the results of the above update to the Products table:

    ```SQL
    select top 10 chunk, embeddings from SalesLT.Product
    ```

    You can see that the chunk column is the combination of multiple data points about a product and the embeddings column contains the vector arrays.

    !IMAGE[A picture of the query result showing the chunk and embeddings columns and their data.](./media/Screenshot 2025-01-15 at 6.34.32 AM.png){1000}

## Vector similarity searching

Vector similarity searching is a technique used to find and retrieve data points that are similar to a given query, based on their vector representations. The similarity between two vectors is usually measured using a distance metric, such as cosine similarity or Euclidean distance. These metrics quantify the similarity between two vectors by calculating the angle between them or the distance between their coordinates in the vector space.

Vector similarity searching has numerous applications, such as recommendation systems, search engines, image and video retrieval, and natural language processing tasks. It allows for efficient and accurate retrieval of similar items, enabling users to find relevant information or discover related items quickly and effectively.

The VECTOR_DISTANCE function is a new feature of the Azure SQL Database that can calculate the distance between two vectors enabling similarity searching right in the database. 

The syntax is as follows:

```SQL-nocopy
VECTOR_DISTANCE ( distance_metric, vector1, vector2 )
```

You will be using this function in some upcoming samples as well as in the RAG chat application; both utilizing the vectors you just created for the Products table.

1. The first query will pose the question "I am looking for a red bike and I dont want to spend a lot". The key words that should help with our similarity search are red, bike, and dont want to spend a lot. Run the following SQL in a blank query editor in Microsoft Fabric:

    ###### Query 1

    ```SQL
    declare @search_text nvarchar(max) = 'I am looking for a red bike and I dont want to spend a lot'
    declare @search_vector vector(1536)
    exec dbo.create_embeddings @search_text, @search_vector output;
    SELECT TOP(4) 
    p.ProductID, p.Name , p.chunk,
    vector_distance('cosine', @search_vector, p.embeddings) AS distance
    FROM [SalesLT].[Product] p
    ORDER BY distance
    ```

    And you can see from the results, the search found exactly that, an affordable red bike. The distance column shows us how similar it found the results to be using VECTOR_DISTANCE, with a lower score being a better match.

    ###### Query 1 results

    | ProductID | Name | chunk | distance |
    |:---------|:---------|:---------|:---------|
    | 763 | Road-650 Red, 48 | Road-650 Red, 48 Red Road Bikes Road-650 Value-priced bike with many features of our top-of-the-line models. Has the same light, stiff frame, and the quick acceleration we're famous for. | 0.16352240013483477 |
    | 760 | Road-650 Red, 60 | Road-650 Red, 60 Red Road Bikes Road-650 Value-priced bike with many features of our top-of-the-line models. Has the same light, stiff frame, and the quick acceleration we're famous for. | 0.16361482158949225 |
    | 759 | Road-650 Red, 58 | Road-650 Red, 58 Red Road Bikes Road-650 Value-priced bike with many features of our top-of-the-line models. Has the same light, stiff frame, and the quick acceleration we're famous for. | 0.16432339626539993 |
    | 762 | Road-650 Red, 44 | Road-650 Red, 44 Red Road Bikes Road-650 Value-priced bike with many features of our top-of-the-line models. Has the same light, stiff frame, and the quick acceleration we're famous for. | 0.1652894865541471 |

    !IMAGE[A picture of running Query 1 and getting results outlined in the Query 1 results table.](./media/Screenshot 2025-01-15 at 6.36.01 AM.png){800}

1. The next search will be looking for a safe lightweight helmet. Run the following SQL in a blank query editor in Microsoft Fabric:

    ###### Query 2

    ```SQL
    declare @search_text nvarchar(max) = 'I am looking for a safe helmet that does not weigh much'
    declare @search_vector vector(1536)
    exec dbo.create_embeddings @search_text, @search_vector output;
    SELECT TOP(4) 
    p.ProductID, p.Name , p.chunk,
    vector_distance('cosine', @search_vector, p.embeddings) AS distance
    FROM [SalesLT].[Product] p
    ORDER BY distance
    ```

    With the results returning lightweight helmets. There is one result that is not a helmet but a vest but as you can see, the distance score is higher for this result than the 3 helmet scores.

    ###### Query 2 results

    | Name | chunk | distance |
    |:---------|:---------|:---------|
    | Sport-100 Helmet, Black | Sport-100 Helmet, Black Black Helmets Sport-100 Universal fit, well-vented, lightweight , snap-on visor. | 0.1641856735683479 |
    | Sport-100 Helmet, Red |Sport-100 Helmet, Red Red Helmets Sport-100 Universal fit, well-vented, lightweight , snap-on visor. | 0.16508593401632166 |
    | Sport-100 Helmet, Blue |Sport-100 Helmet, Blue Blue Helmets Sport-100 Universal fit, well-vented, lightweight , snap-on visor. | 0.16592580751312624 |
    | Classic Vest, S | Classic Vest, S Blue Vests Classic Vest Light-weight, wind-resistant, packs to fit into a pocket. | 0.19888204151269384 |


    !IMAGE[A picture of running Query 2 and getting results outlined in the Query 2 results table](./media/Screenshot 2025-01-14 at 6.00.32 AM.png){800}

1. In the previous 2 examples, we were clear on what we were looking for; cheap red bike, light helmet. In this next example, we are going to have the search flex its AI muscles a bit by saying we want a bike seat that needs to be good on trails. This will require the search to look for adjacent values that have something in common with trails. Run the following SQL in a blank query editor in Microsoft Fabric to see the results.

    ###### Query 3

    ```SQL
    declare @search_text nvarchar(max) = 'Do you sell any padded seats that are good on trails?'
    declare @search_vector vector(1536)
    exec dbo.create_embeddings @search_text, @search_vector output;
    SELECT TOP(4) 
    p.ProductID, p.Name , p.chunk,
    vector_distance('cosine', @search_vector, p.embeddings) AS distance
    FROM [SalesLT].[Product] p
    ORDER BY distance
    ```

    These results are very interesting for it found products based on word meanings such as absorb shocks and bumps and foam-padded. It was able to make connections to riding conditions on trails and find products that would fit that need.

    ###### Query 3 results

    | Name | chunk | distance |
    |:---------|:---------|:---------|
    | ML Mountain Seat/Saddle | ML Mountain Seat/Saddle No Color Saddles ML Mountain Seat/Saddle 2 Designed to absorb shock. | 0.17265341238606102 |
    | LL Road Seat/Saddle | LL Road Seat/Saddle No Color Saddles LL Road Seat/Saddle 1 Lightweight foam-padded saddle. | 0.17667274723850412 |
    | ML Road Seat/Saddle | ML Road Seat/Saddle No Color Saddles ML Road Seat/Saddle 2 Rubber bumpers absorb bumps. | 0.18802953111711573 |
    | HL Mountain Seat/Saddle | HL Mountain Seat/Saddle No Color Saddles HL Mountain Seat/Saddle 2 Anatomic design for a full-day of riding in comfort. Durable leather. | 0.18931317298732764 |

    !IMAGE[A picture of running Query 3 and getting results outlined in the Query 3 results table](./media/Screenshot 2025-01-15 at 6.38.06 AM.png){800}

# 6. Creating a GraphQL API for RAG applications

In this section of the lab, you will be deploying a GraphQL API that uses embeddings, vector similarity search, and relational data to return a set of Adventure Works products that could be used by a chat application leveraging a Large Language Model (LLM). In essence, putting all the pieces together in the previous sections.

In the section of the lab, you will create a stored procedure that will be used by the GraphQL API for taking in questions and returning products.

## Creating the stored procedure used by the GraphQL API

1. Run the following SQL in a blank query editor in Microsoft Fabric:

    ```SQL
    create or alter procedure [dbo].[find_products]
    @text nvarchar(max),
    @top int = 10,
    @min_similarity decimal(19,16) = 0.80
    as
    if (@text is null) return;
    declare @retval int, @qv vector(1536);
    exec @retval = dbo.create_embeddings @text, @qv output;
    if (@retval != 0) return;
    with vector_results as (
    SELECT 
            p.Name as product_name,
            ISNULL(p.Color,'No Color') as product_color,
            c.Name as category_name,
            m.Name as model_name,
            d.Description as product_description,
            p.ListPrice as list_price,
            p.weight as product_weight,
            vector_distance('cosine', @qv, p.embeddings) AS distance
    FROM
        [SalesLT].[Product] p,
        [SalesLT].[ProductCategory] c,
        [SalesLT].[ProductModel] m,
        [SalesLT].[vProductAndDescription] d
    where p.ProductID = d.ProductID
    and p.ProductCategoryID = c.ProductCategoryID
    and p.ProductModelID = m.ProductModelID
    and p.ProductID = d.ProductID
    and d.Culture = 'en')
    select TOP(@top) product_name, product_color, category_name, model_name, product_description, list_price, product_weight, distance
    from vector_results
    where (1-distance) > @min_similarity
    order by    
        distance asc;
    GO
    ```

1. Next, we need to encapsulate the stored procedure into a wrapper so that the result set can be utilized by our GraphQL endpoint. Using the WITH RESULT SET syntax allows you to change the names and data types of the returning result set. This is needed in this example because the usage of sp_invoke_external_rest_endpoint and the return output from extended stored procedures 

    Run the following SQL in a blank query editor in Microsoft Fabric:  

    ```SQL
    create or alter procedure [find_products_api]
        @text nvarchar(max)
        as 
        exec find_products @text
        with RESULT SETS
        (    
            (    
                product_name NVARCHAR(200),    
                product_color NVARCHAR(50),    
                category_name NVARCHAR(50),    
                model_name NVARCHAR(50),    
                product_description NVARCHAR(max),    
                list_price INT,    
                product_weight INT,    
                distance float    
            )
        )
    GO
    ```

1. You can test this newly created procedure to see how it will interact with the GraphQL API by running the following SQL in a blank query editor in Microsoft Fabric:

    ```SQL
    exec find_products_api 'I am looking for a red bike'
    ```

    !IMAGE[A picture of running the find_products_api stored procedure](./media/Screenshot 2025-01-14 at 6.57.09 AM.png){800}

1. To create the GraphQL API, click on the **New API for GraphQL** button on the toolbar.

    !IMAGE[A picture of clicking on the New API for GraphQL button on the toolbar](./media/Screenshot 2025-01-15 at 6.52.37 AM.png){800}

1. In the **New API for GraphQL** dialog box, use the **Name Field** and name the API **find_products_api**.

    +++find_products_api+++

    !IMAGE[A picture of using the Name Field and naming the API find_products_api in the New API for GraphQL dialog box](./media/Screenshot 2025-01-17 at 7.35.03 AM.png){300}

1. After naming the API, click the **green Create button**.

    !IMAGE[A picture of clicking the green Create button in the New API for GraphQL dialog box](./media/Screenshot 2025-01-17 at 7.35.09 AM.png){300}

1.  The next dialog box presented is the **Choose data** dialog box where you will pick a table or stored procedure for the GraphQL API, 

    !IMAGE[A picture of the next dialog box being presented, the Choose data dialog box](./media/Screenshot 2025-01-15 at 7.00.42 AM.png)

    use the **Search box** in the **Explorer section** on the left 
    
    !IMAGE[A picture of using the Search box in the Explorer section on the left of the Choose data dialog box](./media/Screenshot 2025-01-15 at 7.01.39 AM.png){300}

    and **enter in find_products_api**.

    +++find_products_api+++

    !IMAGE[A picture of enter in find_products_api in the search box](./media/Screenshot 2025-01-17 at 6.26.15 AM.png){300}

1. Choose the **find_products_api stored procedure in the results**. You can ensure it is the find_products_api stored procedure by hovering over it with your mouse/pointer. It will also indicate the selected database item in the preview section. It should state **"Preview data: dbo.find_products_api"**.

    !IMAGE[A picture of choosing the find_products_api stored procedure in the results](./media/Screenshot 2025-01-17 at 6.28.44 AM copy.png){700}

1. Once you have selected the **find_products_api stored procedure**, click the **green Load button** on the bottom right of the modal dialog box.

    !IMAGE[A picture of clicking the green Load button on the bottom right of the modal dialog box](./media/Screenshot 2025-01-17 at 6.30.18 AM.png){700}

1. You will now be on the **GraphQL Query editor page**. Here, we can run GraphQL queries similar to how we can run T-SQL queries on the query editor.

    !IMAGE[A picture of the GraphQL Query editor page](./media/Screenshot 2025-01-15 at 7.11.21 AM.png){700}

1. Replace the sample code on the left side of the GraphQL query editor with the following query:

    ```graphql
    query {
        executefind_products_api(text: "I am looking for a red bike") {
                product_name
                product_color
                category_name
                model_name
                product_description
                list_price
                product_weight
                distance 
        }
    }
    ```

    !IMAGE[A picture of replacing the example code with the query code provided](./media/Screenshot 2025-01-15 at 7.16.57 AM.png){700}

1. Now, click the **Run button** in the upper left of the GraphQL query editor. 

    !IMAGE[A picture of clicking the Run button in the upper left of the GraphQL query editor](./media/Screenshot 2025-01-15 at 7.19.13 AM.png){700}

    and you can scroll through the results from the GraphQL query in the lower section of the editor.

    !IMAGE[A picture of scrolling through the results from the GraphQL query in the lower section of the editor](./media/Screenshot 2025-01-15 at 7.21.01 AM.png){700}

1. Back on the toolbar, find and click the **Generate code button**.

    !IMAGE[A picture of clicking the Generate code button](./media/Screenshot 2025-01-15 at 8.38.00 AM.png){600}

1. This feature will generate the code for calling this API via python or node.js to help give you a jumpstart in the application creation process.

    !IMAGE[A picture of the generated code the editor provides](./media/Screenshot 2025-01-15 at 8.40.12 AM.png){800}

1. When done looking at the python and node.js code, click the **X** in the upper right corner to close the Generate code dialog box.

    !IMAGE[A picture of clicking the X in the upper right corner to close the Generate code dialog box](./media/Screenshot 2025-01-15 at 8.40.12 AM2.png){500}

## Adding chat completion to the GraphQL API

The API you just created could now be handed off to an application developer to be included in a RAG application that uses vector similarity search and data from the database. The application may also at some point hand the results off to a LLM to craft a more human response. 

Let's alter the stored procedure to create a new flow that not only uses vector similarity search to get products based on a question asked by a user, but to take the results, pass them to Azure OpenAI Chat Completion, and craft an answer they would typically see with an AI chat application.

1. Before we can start creating new stored procedures, we need to go back to the SQL Database home page. Do this by using the navigator on the left side of the page and clicking on the SQL Database icon.

    !IMAGE[A picture of using the navigator on the left side of the page and clicking on the SQL Database icon](./media/Screenshot 2025-01-17 at 8.44.26 AM.png){200}

1. The first step in augmenting our RAG application API is to create a stored procedure that takes the retrieved products and passes them in a prompt to an Azure OpenAI Chat Completion REST endpoint (this is the same endpoint that was used to ask the llama joke). The prompt consists of telling the endpoint who they are, what products they have to work with, and the exact question that was asked by the user. 

    Copy and run the following SQL in a blank query editor in Microsoft Fabric:


    ```SQL
    CREATE OR ALTER PROCEDURE [dbo].[prompt_answer]
    @user_question nvarchar(max),
    @products nvarchar(max),
    @answer nvarchar(max) output

    AS

    declare @url nvarchar(4000) = N'https://AI_ENDPOINT_SERVERNAME.openai.azure.com/openai/deployments/gpt-4/chat/completions?api-version=2024-06-01';
    declare @payload nvarchar(max) = N'{
        "messages": [
            {
                "role": "system",
                "content": "You are a sales assistant who helps customers find the right products for their question and activities."
            },
            {
                "role": "user",
                "content": "The products available are the following: ' + @products + '"
            },
            {
                "role": "user",
                "content": " ' + @user_question + '"
            }
        ]
    }';

    declare @ret int, @response nvarchar(max);

    exec @ret = sp_invoke_external_rest_endpoint
        @url = @url,
        @method = 'POST', 
        @payload = @payload,
        @credential = [https://AI_ENDPOINT_SERVERNAME.openai.azure.com/],    
        @timeout = 230,
        @response = @response output;

    select json_value(@response, '$.result.choices[0].message.content');

    GO
    ```

1. Now that you have created the chat completion stored procedure, we need to create a new find_products stored procedure that adds a call to this chat completion endpoint. This new stored procedure contains 2 additional steps that were not found in the original: 
    
    1) A section to help package up the results into something we can use in a prompt.
    
    ```SQL-nocopy
    STRING_AGG (CONVERT(NVARCHAR(max),CONCAT( 
                                    product_name, ' ' ,
                                    product_color, ' ',
                                    category_name, ' ', 
                                    model_name, ' ', 
                                    product_description )), CHAR(13)))   
    ```

    2) A section that calls the new chat completion stored procedure and provides it with the products retrieved from the database to help ground the answer.

    ```SQL-nocopy
    exec [dbo].[prompt_answer] @text, @products_json, @answer output;
    ```

1. Copy and run the following SQL in a blank query editor in Microsoft Fabric:


    ```SQL
    create or alter procedure [dbo].[find_products_chat]
    @text nvarchar(max),
    @top int = 3,
    @min_similarity decimal(19,16) = 0.70
    as
    if (@text is null) return;
    declare @retval int, @qv vector(1536), @products_json nvarchar(max), @answer nvarchar(max);
    exec @retval = dbo.create_embeddings @text, @qv output;
    if (@retval != 0) return;
    with vector_results as (
    SELECT 
            p.Name as product_name,
            ISNULL(p.Color,'No Color') as product_color,
            c.Name as category_name,
            m.Name as model_name,
            d.Description as product_description,
            p.ListPrice as list_price,
            p.weight as product_weight,
            vector_distance('cosine', @qv, p.embeddings) AS distance
    FROM
        [SalesLT].[Product] p,
        [SalesLT].[ProductCategory] c,
        [SalesLT].[ProductModel] m,
        [SalesLT].[vProductAndDescription] d
    where p.ProductID = d.ProductID
    and p.ProductCategoryID = c.ProductCategoryID
    and p.ProductModelID = m.ProductModelID
    and p.ProductID = d.ProductID
    and d.Culture = 'en')
    select
    top(@top)
    @products_json = (STRING_AGG (CONVERT(NVARCHAR(max),CONCAT( 
                                    product_name, ' ' ,
                                    product_color, ' ',
                                    category_name, ' ', 
                                    model_name, ' ', 
                                    product_description, ' ',
                                    list_price, ' ',
                                    product_weight )), CHAR(13)))
    from vector_results
    where (1-distance) > @min_similarity
    group by distance
    order by    
        distance asc;

    set @products_json = (select REPLACE(REPLACE(@products_json, CHAR(13), ' , '), CHAR(10), ' , '));

    exec [dbo].[prompt_answer] @text, @products_json, @answer output;

    GO
    ```

1. The last step before we can create a new GraphQL endpoint is to wrap the new find products stored procedure. Copy and run the following SQL in a blank query editor in Microsoft Fabric:


    ```SQL
    create or alter procedure [find_products_chat_api]
        @text nvarchar(max)
        as 
        exec find_products_chat @text
        with RESULT SETS
        (    
            (    
                answer NVARCHAR(max)
            )
        )
    GO
    ```

1. You can test this new  procedure to see how Azure OpenAI will answer a question with product data by running the following SQL in a blank query editor in Microsoft Fabric:

    ```SQL
    exec find_products_chat_api 'I am looking for a red bike'
    ```

    with the answer being similar to (your answer will be different): **"It sounds like the Road-650 Red, 62 Red Road Bikes Road-650 would be an excellent choice for you. This value-priced bike comes in red and features a light, stiff frame that is known for its quick acceleration. It also incorporates many features from top-of-the-line models. Would you like more details about this bike or help with anything else?"**

    !IMAGE[A picture of running the find_products_chat_api stored procedure](./media/Screenshot 2025-01-17 at 6.15.05 AM.png){800}

1. To create the GraphQL API, click on the **New API for GraphQL** button on the toolbar just as you did previously.

    !IMAGE[A picture of clicking on the New API for GraphQL button on the toolbar](./media/Screenshot 2025-01-15 at 6.52.37 AM.png){800}

1. In the **New API for GraphQL** dialog box, use the **Name Field** and name the API **find_products_chat_api**.

    +++find_products_chat_api+++

    !IMAGE[A picture of using the Name Field and naming the API find_products_chat_api in the New API for GraphQL dialog box](./media/Screenshot 2025-01-17 at 7.34.39 AM.png){300}

1. After naming the API, click the **green Create button**.

    !IMAGE[A picture of clicking the green Create button in the New API for GraphQL dialog box](./media/Screenshot 2025-01-17 at 7.34.47 AM.png){300}

1.  The next dialog box presented is again the **Choose data** dialog box where you will pick a table or stored procedure for the GraphQL API, 

    !IMAGE[A picture of the next dialog box being presented, the Choose data dialog box](./media/Screenshot 2025-01-15 at 7.00.42 AM.png)

    use the **Search box** in the **Explorer section** on the left 
    
    !IMAGE[A picture of using the Search box in the Explorer section on the left of the Choose data dialog box](./media/Screenshot 2025-01-15 at 7.01.39 AM.png){300}

    and **enter in find_products_chat_api**.

    +++find_products_chat_api+++

    !IMAGE[ picture of enter in find_products_chat_api in the search box](./media/Screenshot 2025-01-17 at 6.24.33 AM.png){300}

1. Choose the stored procedure in the results. You can ensure it is the **find_products_chat_api stored procedure** by hovering over it with your mouse/pointer. It will also indicate the selected database item in the preview section. It should state **"Preview data: dbo.find_products_chat_api"**.

    !IMAGE[A picture of choosing the find_products_chat_api stored procedure in the results](./media/Screenshot 2025-01-17 at 6.34.33 AM.png){700}

1. Once you have selected the **find_products_chat_api stored procedure**, click the **green Load button** on the bottom right of the modal dialog box.

    !IMAGE[A picture of clicking the green Load button on the bottom right of the modal dialog box](./media/Screenshot 2025-01-17 at 6.32.43 AM.png){700}

1. You will now be back on the **GraphQL Query editor page**.

    !IMAGE[A picture of the GraphQL Query editor page](./media/Screenshot 2025-01-15 at 7.11.21 AM.png){700}

1. Replace the sample code on the left side of the GraphQL query editor with the following query:

    ```graphql
    query {
        executefind_products_chat_api(text: "I am looking for padded seats that are good on trails") {
                answer
        }
    }
    ```

    !IMAGE[A picture of replacing the sample code on the left side of the GraphQL query editor with the supplied code](./media/Screenshot 2025-01-17 at 6.40.03 AM.png){600}

1. Now, **click the Run button** in the upper left of the GraphQL query editor.

    !IMAGE[A picture of clicking the Run button in the upper left of the GraphQL query editor](./media/Screenshot 2025-01-17 at 6.37.51 AM.png){600}    

1. And you can review the response in the **Results** section of the editor

    !IMAGE[A picture of reviewing the response in the Results section of the editor](./media/Screenshot 2025-01-17 at 6.41.24 AM.png){600}

1. Try it again with the following code and see what answer the chat completion endpoint provides!

    ```graphql
    query {
        executefind_products_chat_api(text: "Do you have any racing shorts?") {
                answer
        }
    }
    ```

# 7. Creating a Power BI Report from a SQL Database in Microsoft Fabric with Copilot

It's easy to quickly create reports in Power BI with SQL database in Fabric using Copilot. 

## Build a new report with Copilot

1. Using the navigator on the left side of the Microsoft Fabric page, **click the tile for your database**. It will be named **sqlDatabase followed by a set of numbers**.

    !IMAGE[A picture of using the navigator on the left side of the Microsoft Fabric page to click the tile for the database](./media/Screenshot 2025-01-23 at 5.35.24 AM.png){300}

1. Now on the database details page, find the **SQL database dropdown** in the upper right of the page.

    !IMAGE[A picture of finding the SQL database dropdown in the upper right of the page](./media/Screenshot 2025-01-23 at 5.37.48 AM.png){600}

1. Click the SQL database dropdown and select **SQL analytics endpoint**.

    !IMAGE[A picture of clicking the SQL database dropdown and selecting SQL analytics endpoint](./media/Screenshot 2025-01-23 at 5.42.43 AM.png){500}

    > [!Knowledge] You can also get to the SQL analytics endpoint by clicking on your workspace tile, and selecting the SQL analytics endpoint on the bottom of the page.
    >
    
    !IMAGE[A picture of clicking on your workspace tile, and selecting the SQL analytics endpoint on the bottom of the page](./media/Screenshot 2025-01-23 at 5.32.27 AM.png){600}

1. On the SQL database analytics endpoint details page, **click the Reporting tab** from the ribbon.

    !IMAGE[A picture of clicking the Reporting tab from the ribbon on the SQL database analytics endpoint details page](./media/Screenshot 2025-01-23 at 5.57.06 AM.png){600}

1. Now, click the **New Report** button.

    !IMAGE[A picture of clicking the New Report button](./media/Screenshot 2025-01-23 at 5.59.30 AM.png){600}

1. When the **New report with all available data modal window** opens, click the **green Continue button** to create a new report with all available data.

    > [!Alert] If you get an error after clicking the green Continue button saying:
    >
    >**"Unable to add the selected objects because at least one of them has been removed from the source. Please refresh and try again."** 
    >
    >Close the dialog box and reopen it. Then, click the green Continue button again.

    !IMAGE[A picture of clicking the green Continue button to create a new report in the New report with all available data modal window](./media/Screenshot 2025-01-23 at 6.02.14 AM.png){600}

1. The **Upgrade to a paid Power BI license modal window** is next. Simply **click the white Try free button**.

    !IMAGE[A picture of clicking the white Try free button in the Upgrade to a paid Power BI license modal window](./media/Screenshot 2025-02-03 at 5.57.05 AM.png){700}
    
1. And confirm the free license on the following model by **clicking the green Got it button**.

    !IMAGE[A picture of clicking the green Got it button on the following model](./media/Screenshot 2025-02-03 at 5.57.16 AM.png){600}

1. Once the new report opens in Power BI, click the **Try it** button in the **green callout box for Copilot**.

    !IMAGE[A picture of clicking the Try it button in the **green callout box for Copilot](./media/Screenshot 2025-01-23 at 6.04.57 AM.png){600}

1. On the **right side** of the page, the **Copilot blade** opens.

    !IMAGE[A picture of copilot blade on the right side of the page](./media/Screenshot 2025-01-23 at 6.09.03 AM.png){400}

    Click the **green Get started button**.

    !IMAGE[A picture of clicking the green Get started button in the copilot blade](./media/Screenshot 2025-01-23 at 6.10.53 AM.png){400}

1. Copilot presents some questions to get you started. Click **Suggest content for a new report page**.

    !IMAGE[A picture of clicking Suggest content for a new report page in the copilot blade](./media/Screenshot 2025-01-23 at 6.12.34 AM.png){400}

1. Suggested outlines for your report are returned by Copilot based on the data it has access to in the analytics endpoint. 

    > [!Knowledge] The suggested reports returned by Copilot may differ from the following images.

    !IMAGE[A picture of suggested outlines for a report returned by Copilot based on the data it has access to in the analytics endpoint](./media/Screenshot 2025-01-23 at 6.15.10 AM.png){300}

1. You can review the selections by **expanding their cards** to see a quick description about the report.

    !IMAGE[A picture of expanding report suggestion cards to see a quick description about the report](./media/Screenshot 2025-01-23 at 6.23.27 AM.png){300}

1. Click the **Create button** for the **Sales Order Details** report **or any other report** you would like to create. Go wild!

    !IMAGE[A picture of clicking the Create button for the Sales Order Details report](./media/Screenshot 2025-01-23 at 6.28.51 AM.png){300}

1. Copilot will then begin **creating your report**.

    !IMAGE[A picture of copilot creating a Power BI report](./media/Screenshot 2025-02-06 at 6.25.53 AM.png){300}

1. You now have a Power BI report of your SQL database data!

    !IMAGE[A picture of the copilot generated power bi report](./media/Screenshot 2025-02-06 at 6.29.04 AM.png){700}

1. **Minimize the blades** 

    !IMAGE[A picture of minimizing the blades to make the report larger](./media/Screenshot 2025-01-23 at 6.30.37 AM.png){600}

    to expand the size of the report.

    !IMAGE[A picture of a Power BI report with the blades minimized](./media/Screenshot 2025-01-23 at 6.30.51 AM.png){600}
