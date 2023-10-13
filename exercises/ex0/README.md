# Exercise 1 - Migration Assessment

In this exercise, you will learn how to migrate your existing integration scenarios to SAP Integration Suite with the Migration Assessment capability of SAP Integration Suite. This offering helps you estimate the technical efforts involved in the migration process and evaluates how various integration scenarios might be migrated.

## Login to SAP Integration Suite tenant

After completing these steps you will be able to see the SAP Integration Suite landing page and view the Migration Assessment and Cloud Integration capabilities offered as part of the SAP Integration Suite

1. Click on the link https://teched23blr11.integrationsuite.cfapps.ap11.hana.ondemand.com/shell/home
   
2. Enter <b>User</b> as userXX (where XX is from 00 to 99) and Password as Welcome1 and Click on <b>Log On</b>.
   <br>![](/exercises/ex0/images/Login.png)
   
3. In the SAP Integration Suite landing page, scroll down to Capabilities, and select <b>Create Requests</b> from the <b>Assess Migration Scenarios</b> tile.
  <br>![](/exercises/ex0/images/Access_Migration_Scenarios.png)
   
## Checkout Configuration for Process Orchestration System

After completing these steps you will be able to test the connection to your SAP Process Orchestration(PO) system. Additionally, we will also walk you through the steps on how to set up your own PO system. This will help you to do the setup on your own landscape.

<b>Note:</b> For this exercise, the connection to a cloud connector has been established, the PO system is connected to the SAP Integration Suite tenant and you do not have Admin roles to add a new system.

1. Navigate to <b>Settings</b> and Select <b>J2E</b> System to view the details.
   <br>![](/exercises/ex0/images/View_PO_System.png)
   
2. For this exercise, the system setup is already done and you can click on <b>Test Connection</b> to check the connection to PO system.
   <br>![](/exercises/ex0/images/Test_PO_Con.png)
   
<b><u>Note:</b></u> In the Migration Assessment Application, the page now displays information about the Integration Directory and, optionally, the Enterprise Services Repository you connected to your previously created system.

3. In the Migration Assessment Application, navigate to <b>Configure > Rules</b>
   <br>![](/exercises/ex0/images/Configure_Rule.png)  

Here you can find a list of rules predefined by SAP. Rules are a set of characteristics according to which the application evaluates whether an integration scenario can be migrated and what effort you can expect.

<b>Note:</b> Currently, you can’t add custom rules or edit the standard rules. You can only view the standard rules.

4. As an example, select the rule <b>SenderAdapterType</b>
   <br>![](/exercises/ex0/images/Select_Sender_Adapter_Type.png)
   
5. Open the variant <b>MAIN_SenderAdapterType</b>
![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/c4b005cb-e7bb-4542-8bef-61c81a566ee0)

Here, you can see all the parameters of the rules, such as Rule Match Value, Assessment Category, and the Weight assigned to each rule match value. Based on these weights, the application calculates the estimated effort, which means that some parameters, and therefore rules, have a bigger influence on the final estimation than others.

## Optional - Walkthrough of adding a Process Orchestration System

Optionally you can try out this section to add the PO system in your own landscape. For this exercise, you do not have the roles to Add the system but we want to walk you through the steps so that you can do it on your landscape.

1. Navigate back to <b>Settings</b> and click on <b>'+'</b>
   <br>![](/exercises/ex0/images/1.AddNewPOSystem.png)
   
2. Fill in the details and click on <b>Add</b>.
   <br>![](/exercises/ex0/images/2.PO_System_Details.png)
   
3. You will be able to see the newly added systems and additionally you can check the connection by clicking on the <b>Test Connection</b>
   <br>![](/exercises/ex0/images/3.TestPOConnection.png)
   
## Reuse or Create a new Data Extraction Request

Usually, the data extraction takes some time depending on the number of integration scenarios configured on SAP Process Orchestration. For our exercise, we have configured a handful of scenarios in the SAP Process Orchestration system, so that the extraction runs fast.
A recommendation from our side would be to reuse the already created Data Extraction Request. If you still want to create a new one, please follow the below steps.

1.	In the Migration Assessment Application, navigate to <b>Request Data Extraction</b>.
   <br>![](/exercises/ex0/images/Request_Data_Ext.png)
  	
2. We recommend you reuse the already existing request as creating a new one would take a few minutes. If you want to create a new request, Click on <b>Create</b>. Otherwise, you can continue with [Create a Scenario Evaluation Request](#create-a-scenario-evaluation-request).
   <br>![](/exercises/ex0/images/Ruse_Data_Ext.png)
   
3. Enter a Request Name (append with your unique identifier maybe DemoXX where XX is your user from 00 to 99), and select the System you want to connect to (in our case it is J2E from the drop-down). Click on <b>Create</b>.
   <br>![](/exercises/ex0/images/New_Data_Ext.png)
   
4. The data extraction starts. It should show the status <b>In Process</b>. From time to time, you can refresh to check if the request has been completed.
   <br>![](/exercises/ex0/images/Extraction_In_Progress.png)
   
5. Once the extraction finishes, the new request appears in the list of data extraction requests with the status <b>Completed</b>. Choose the  <b>Check extraction logs</b> icon to view the data extraction log which provides you with details about the data extraction.
   <br>![](/exercises/ex0/images/Completed_Data_Ext.png)
   
6. The log shows you the different steps of the data extraction, its progress if still In Progress, warnings and errors during the extraction, etc. In the log, you can filter on the log level. Furthermore, you can download the log in Excel format.
   <br>![](/exercises/ex0/images/Ext_Logs.png)
   
## Create a Scenario Evaluation Request

Assess your integration scenarios using the information from the data extraction requests. The prerequisite is that you have at least one data extraction request in status <b>Completed</b>.
<br>![](/exercises/ex0/images/Ruse_Data_Ext.png)

1. In the Migration Assessment application, navigate to  <b>Request --> Scenario Evaluation</b>.
   <br>![](/exercises/ex0/images/Request_Scenario_Eval.png)
   
2. Select <b>Create</b>
   <br>![](/exercises/ex0/images/Select_Create.png)
   
3. Enter a Request Name as <b>DemoXX</b> (where XX is your user from 00 to 99)and choose a Data Extraction Request from the drop-down or the one you executed previously. For this specific run of your scenario evaluation, enter an Evaluation Run Name as <b>DemoXX</b> (where XX is your user from 00 to 99)and a Description.
  <br>![](/exercises/ex0/images/Create_Sce_Eval.png)

<b>Note:</b> You usually run a new evaluation request for a new data extraction whereas you run a new evaluation run whenever the assessment rules have been changed.

4. The new request appears in the list of scenario evaluation requests in Status <b>In Progress</b>.
   <br>![](/exercises/ex0/images/Extraction_In_Progress.png)
   
5. Refresh and wait until the request changes to status <b>Completed</b>. Different Actions can be performed for a scenario evaluation request.
   <br>![](/exercises/ex0/images/Complete_Sce_Eval.png)
   
## View Generated Reports

Access and download analysis of your scenario evaluation runs with details specific to your integration scenarios, for example, adapters and an overview of the rules used in the evaluation. Further, you can download details about the latest evaluation run in one of two formats <b>.xlsx</b> file and <b>.pdf</b> file

1. Let’s start with opening the dashboard. Select the  <b>Open Dashboard</b> icon.
   <br>![](/exercises/ex0/images/Open_Dash.png)
   
2. The dashboard shows you an analysis of your scenario evaluation runs with details specific to your integration scenarios, i.e., scenarios grouped by assessment categories, scenarios grouped by rough t-shirt effort estimation, statistics about adapters used in your integration scenarios, etc. You can switch between the data of all runs performed for the scenario evaluation request so far (note, if you haven’t triggered another analysis, there is only one entry in the drop-down menu).
   <br>![](/exercises/ex0/images/Overview_Dash.png)
   
3. Switch to the <b>Integration Scenarios</b> tab, and you see the list of all integration scenarios including effort size and assessment category.
   <br>![](/exercises/ex0/images/Dashboard.png)
   
4. Switch back to the list of <b>Scenario Evaluation</b> requests. From the Additional Options menu, you can select <b>Trigger Analysis</b> to schedule a new evaluation run based on the most recent data extraction. Let's skip this for now as data did not change.
   <br>![](/exercises/ex0/images/Trigger_Analysis.png)
   
6. Furthermore, you have the option to  download details about the latest evaluation run either in an Excel format or as a PDF file.
   <br>![](/exercises/ex0/images/Download_excel.png)
   
7. The option as .xlsx file lists all integration scenarios that were part of the request with migration effort and status as well as the rules applied to them.
   <br>![](/exercises/ex0/images/Excel.png)

8. The option as .pdf file features the previously mentioned details about the integration scenarios while also providing a written summary of adapters and the assessment in general, with charts and tables as visual aids. It also maps the t-shirt effort estimation to effort estimation in person days based on project experience. This file is suited as a summarizing report, that can be used for example for management.
    <br>![](/exercises/ex0/images/pdf.png)

## Summary- Congratulations on having Assessed your SAP Process Orchestration landscape!

Once you have evaluated the migration possibility using the Migration Assessment capability of SAP Integration Suite, you are all set to migrate an integration artifact with the Migration tool.

Continue to - [Exercise 2 - Migrate and Test SOAP to SOAP Scenario](../ex1/README.md)
