# Migration Assessment

In this exercise, you will learn how to migrate your existing integration scenarios to SAP Integration Suite with the Migration Assessment. This offering helps you estimate the technical efforts involved in the migration process and evaluates how various integration scenarios might be migrated.

## Login to Integration Suite tenant

After completing these steps you will be able to see the SAP Integration Suite landing page and view the Migration Assessment and Cloud Integration capabilities offered as part of SAP Integration Suite

1. Click on the link https://teched23blr07.integrationsuite.cfapps.ap10.hana.ondemand.com/shell/home
   
2. Enter User as userXX (where XX is from 00 to 99) and Password as Welcome1 and Click on Log On.
   <br>![](/exercises/ex0/images/Login.png)
   
3. In the SAP Integration Suite landing page, scroll down to Capabilities, and select   Create Requests from the Assess Migration Scenarios tile.

4. Navigate to Settings and Select J2EE System to view the details.
   <br>![](/exercises/ex0/images/Access_Migration_Scenarios.png)

## Checkout Configuration for Process Orchestration System

After completing these steps you will be able to test the connection between the Integration Suite tenant and PO system. Additionally, we will also walk you through the steps on how to set up your own PO system. This will help you to do the setup on your own landscape.

Note: For this exercise, the connection to a cloud connector running on the CAL system has been established, the PO system is connected to the SAP Integration Suite tenant and you do not have Admin roles to add a system.

1. Navigate to Settings and Select J2EE System to view the details.
   <br>![](/exercises/ex0/images/View_PO_System.png)
   
4. (Optional)After adding the system if you are setting it up in your own tenant, you can test the connection if it is successful or not. To change the connection details, you can edit it too.
5. 
6. For this exercise, system setup is already done and you click on Test Connection to check the connection to PO system.
   <br>![](/exercises/ex0/images/Test_PO_Con.png)
   
In the Migration Assessment Application, the page now displays information about the Integration Directory and, optionally, the Enterprise Services Repository you connected to your previously created system.

7. In the Migration Assessment Application, navigate to Configure > Rules.
   <br>![](/exercises/ex0/images/Configure_Rule.png)
Here you can find a list of rules predefined by SAP. Rules are a set of characteristics according to which the application evaluates whether an integration scenario can be migrated and what effort you can expect.

Note: Currently, you can’t add custom rules or edit the standard rules. You can only view the standard rules.

5. As an example, select the rule SenderAdapterType
   <br>![](/exercises/ex0/images/Select_Sender_Adapter_Type.png)
Here, you can see all the parameters of the rules, such as Rule Match Value, Assessment Category, and the Weight assigned to each rule match value. Based on these weights, the application calculates the estimated effort, which means that some parameters, and therefore rules, have a bigger influence on the final estimation than others.

## Optional Add a Process Orchestration System
Optionally you can add the PO system. For this exercise, you do not have the roles to Add the system but we want to walk you through the steps so that you can do it on your landscape.

1. Navigate back to Settings and click on Add
   <br>![](/exercises/ex0/images/Select_Sender_Adapter_Type.png)
   
2. Fill in the details and click on Create.
   <br>![](/exercises/ex0/images/Select_Sender_Adapter_Type.png)
   
3. You will be able to see the newly added systems and additionally you can check the connection by clicking on the Test connection
   <br>![](/exercises/ex0/images/Select_Sender_Adapter_Type.png)
   
## Create Data Extraction Request
After completing these steps you will have....

1.	In the Migration Assessment Application, navigate to   Request  Data Extraction.
   <br>![](/exercises/ex0/images/Request_Data_Ext.png)
2. We recommend you reuse the already existing request as creating a new one would take a few minutes.
   <br>![](/exercises/ex0/images/Ruse_Data_Ext.png)
4. (Optional) If you like to create a new request, select  Create, then enter a Request Name (maybe append with your unique identifier) and select the System you want to connect to (in our case it is J2EE from the drop-down).
   <br>![](/exercises/ex0/images/New_Data_Ext.png)
5. The data extraction starts. It should show the status In Process. From time to time, you can refresh to check if the request has been completed.
   <br>![](/exercises/ex0/images/Extraction_In_Progress.png)
6. Once the extraction finishes, the new request appears in the list of data extraction requests with the status Completed. Choose the  Check extraction logs icon to view the data extraction log which provides you with details about the data extraction.
   <br>![](/exercises/ex0/images/Completed_Data_Ext.png)
7. The log shows you the different steps of the data extraction, its progress if still In Progress, warnings and errors during the extraction, etc. In the log, you can filter on the log level. Furthermore, you can download the log in Excel format.
   <br>![](/exercises/ex0/images/Ext_Logs.png)
   
## Create a Scenario Evaluation Request

Assess your integration scenarios using the information from the data extraction requests. The prerequisite is that you have at least one data extraction request in status Completed.
<br>![](/exercises/ex0/images/Ruse_Data_Ext.png)

1. In the Migration Assessment application, navigate to  Request  Scenario Evaluation, and select  Create
   <br>![](/exercises/ex0/images/New_Data_Ext.png)
   
2. Enter a Request Name as DemoXX (where XX is your user from 00 to 99)and choose a Data Extraction Request from the drop-down or the one you executed previously. For this specific run of your scenario evaluation, enter an Evaluation Run Name as DemoXX (where XX is your user from 00 to 99)and a Description.
  <br>![](/exercises/ex0/images/Create_Sce_Eval.png)

Note: You usually run a new evaluation request for a new data extraction whereas you run a new evaluation run whenever the assessment rules have been changed. Select  Create.

3. The new request appears in the list of scenario evaluation requests in Status In Progress.
   <br>![](/exercises/ex0/images/Extraction_In_Progress.png)
   
4. Refresh and wait until the request changes to status Completed. Different Actions can be performed for a scenario evaluation request.
   <br>![](/exercises/ex0/images/Complete_Data_Ext.png)
   
## View Generated Reports

1. Let’s start with opening the dashboard. Select the  Open Dashboard icon.
   <br>![](/exercises/ex0/images/Open_Dash.png)
2. The dashboard shows you an analysis of your scenario evaluation runs with details specific to your integration scenarios, i.e., scenarios grouped by assessment categories, scenarios grouped by rough t-shirt effort estimation, statistics about adapters used in your integration scenarios, etc. You can switch between the data of all runs performed for the scenario evaluation request so far (note, if you haven’t triggered another analysis, there is only one entry in the drop-down menu).
   <br>![](/exercises/ex0/images/Overview_Dash.png)
3. Switch to the Integration Scenarios tab, and you see the list of all integration scenarios including effort size and assessment category.
   <br>![](/exercises/ex0/images/Dashboard.png)
5. Switch back to the list of Scenario Evaluation requests. From the Additional Options menu, you can select  Trigger Analysis to schedule a new evaluation run based on current data.
   <br>![](/exercises/ex0/images/Trigger_Analysis.png)   
6. Furthermore, you have the option to  Download details about the latest evaluation run either in an Excel format or as a pdf file.
   <br>![](/exercises/ex0/images/Download_excel.png)
8. The option as .xlsx file lists all integration scenarios that were part of the request with migration effort and status as well as the rules applied to them.
   <br>![](/exercises/ex0/images/Excel.png)
10. The option as .pdf file features the previously mentioned details about the integration scenarios while also providing a written summary of adapters and the assessment in general, with charts and tables as visual aids. It also maps the t-shirt effort estimation to effort estimation in person days based on project experience. This file is suited as a summarizing report, that can be used for example for management.
    <br>![](/exercises/ex0/images/pdf.png)

## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
