# Exercise 2 - Migrate and Test SOAP to SOAP Scenario

After having finished the assessment of the current SAP Process Orchestration landscape and having estimated the effort needed to migrate with the Migration Assessment capability, the next step is the actual migration. The goal of the Migration Tool is to provide a semi-automated migration where interfaces in Cloud Integration will be automatically created so ideally 60-70% of technical migration efforts are automated. The migration of scenarios is based on a template approach, which means that integration flow templates are used as a skeleton to migrate the content and create the final integration flows.

## Create a Cloud Integration package

 As a prerequisite, you first need to create an integration package where the automatically generated integration flows are created and 
 then we will migrate SOAP to SOAP interface.

1. Switch back to the SAP Integration Suite landing page.
  <br>![](/exercises/ex1/images/Navigate_Back.png)

3. Navigate to  Design  Integrations, and select  Create.
   <br>![](/exercises/ex1/images/Create_Pack.png)
   
5. Fill in  the Name, e.g. Demo_<userxx> where xx is your user number from 00 to 99, and a short description eg <Migrate SOAP to SOAP artifact>. Then click Save.
    <br>![](/exercises/ex1/images/Save_Pack.png)
   
## Migrate SAP Process Orchestration Artifacts (SOAP to SOAP scenario)

Every ICO that can be migrated has an associated template in the migration tooling. It's based on these templates, the migration tooling creates equivalent integration flows in the SAP Integration Suite. Let's start with the actual migration.

1. In the package you just created, you should be already in Edit mode. If not, on the top right click  Edit.
   <br>![](/exercises/ex1/images/Migrate.png)
   
3. Click on  Migrate to start the migration wizard.
   <br>![](/exercises/ex1/images/Migrate.png)
   
5. Select the SAP Process Orchestration system for which the assessment was previously done. For this expand the  Name section and select your system from the drop-down menu. click  Next Step to proceed with configuring the scenario.
    <br>![](/exercises/ex1/images/PO_sys.png)
   
7. Currently, only Integrated Configuration Objects (ICO) are supported. You can use the filter to filter out the list of ICOs and choose the appropriate scenario.  Click on Show Filters and fill in “http://pi-elevation.bootcamp.com“ as Namespace. Choose the interface “SI_NumberConversion_Out” from the drop-down list. Click  Next Step.
   <br>![](/exercises/ex1/images/Namespace_Next.png)
   
9. The best-fit template is identified by the migration framework and will be automatically filled in for you. In this case, it will be “P2P_SYNC_0001”. Click  Next Step.
    <br>![](/exercises/ex1/images/Template.png)
   
11. Maintain any Name for your integration flow, e.g. following the pattern: soap_to_soap_sync_<your userxx> where xx is your user from 00 to 99. Note, that the ID of your integration flow needs to be unique across all integration flows on the tenant. Click on  Review.
    <br>![](/exercises/ex1/images/Int_Name_Review.png)
    
13. Verify the information and then click on  Migrate.
    <br>![](/exercises/ex1/images/Final_Migrate.png)
    
15. A new integration flow has been generated within your package. Click on the artifact to take a closer look at each individual step. The required information is automatically populated such as the connection information. You can close this window.
    <br>![](/exercises/ex1/images/Close_Artifact.png)

## Deploy migrated artifacts

After completing these steps you will be able to deploy the Integration flow and monitor your scenario
    
1.  Click on the  SOAP Adapter and view the  Connection details. You can see that the endpoint address has been automatically set based on the integration flow name that you have entered.
    <br>![](/exercises/ex1/images/Open_Iflow.png)
    
2. For this particular scenario, no manual steps need to be carried out. It should run as is. Select  Deploy to get the integration flow deployed on the tenant runtime.
    <br>![](/exercises/ex1/images/Deploy_Con.png)
   
3. You can check the deployment status via the monitor dashboard. Navigate to  Monitor  Integrations, and select the Manage Integration Content tile.
    <br>![](/exercises/ex1/images/Monitor_Int.png)
   
4. Your integration flow should be in status Started. From here, you get the endpoint that you need to call to test the scenario. Copy the endpoint as we will use it in the next step.
    <br>![](/exercises/ex1/images/Copy_endpoint.png)
   
Now you are all set to test your scenario!

## Verify the Interface via Insomnia

After completing these steps you will be able to test the interface and get the desired result of converting a number into a text.

1. Open  Insomnia and click on Import.
   <br>![](/exercises/ex1/images/Insom_Import.png)
   
2.  Drag and drop the PI Elevation_Demo.json file  from your system to Insomnia UI and click on Scan
   <br>![](/exercises/ex1/images/Insom_Scan.png)

3. Click on Import
    <br>![](/exercises/ex1/images/Insom_ImportClick.png)
   
4. Expand PI Elevation_Demo collection and you should be able to see 3 requests
   <br>![](/exercises/ex1/images/Insom_3Req.png)
   
5. From the collection “PI Elevation_Demo” open the “Number Conversion Request”, and update the URL so that it fits the end point of your integration flow, under authentication fill in the Process Integration Client ID (obtained from the tenant booker app )for username and Process Integration Client Secret (obtained from tenant booker app) for password and click on Send.
   <br>![](/exercises/ex1/images/Insoma_Final_Test.png)
   
6. The request should return HTTP code 200 and a response with the converted text.
  <br>![](/exercises/ex1/images/Insom_200_OK.png)

## Summary - Congratulations You have successfully tested your scenario now.
Exercise 2 is an optional exercise, if time permits you can continue with it.

Continue to - [Exercise 3 - Migrate and Test SOAP to REST Scenario](../ex2/README.md)

