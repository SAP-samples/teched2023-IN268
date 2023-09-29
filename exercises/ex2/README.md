# Exercise 3 - Migrate and Test SOAP to REST Scenario

In this exercise, we will create migrate a SOAP to REST scenario. 9.	For this particular scenario, not all attributes of the ICO on SAP Process Orchestration could be mapped to the parameters in the integration flow on Cloud Integration, so a couple of manual adjustments will need to be carried out which we will do as a part of the exercise.

1. Open your previously created package, and switch to the Artifacts tab, then switch to Edit Mode.
<br>![](/exercises/ex2/images/1.OpenPreviousPackage.png)

2. Click on  Migrate to start the migration wizard.
<br>![](/exercises/ex2/images/2.0_ClickOnMigrate.png)

3.	Configure the SAP Process Orchestration system as before. For this expand the  Name section and choose your system. Click  Connect. Lastly, click  Next Step to proceed with configuring the scenario.
<br>![](/exercises/ex2/images/3.0_Migrate_SelectPO_System.png)

4.	Click on  Show Filters and fill in “http://pi-elevation.bootcamp.com“ for Namespace. Choose the interface “SI_Employee_Out” from the drop-down list. Click  Next Step.
<br>![](/exercises/ex2/images/3.1_Migrate_SelectPO_Artifacts.png)

5.	The template “P2P_SYNC_JSON_REC_0001” should already be selected. Click  Next Step. 
<br>![](/exercises/ex2/images/3.2_Migrate_SelectPO_Template.png)

6.	Maintain a Name for your integration flow, e.g., following the pattern soap_to_rest_sync_<your initials or name>. The, click on  Review.
<br>![](/exercises/ex2/images/3.3_Migrate_IntegrationFlow_Name.png)

7.	Verify the information and click on  Migrate.
<br>![](/exercises/ex2/images/3.4_Migrate_Review.png)

8.	Again, the integration flow will be generated within your integration package. As you can see from the summary page, the REST receiver adapter on SAP Process Orchestration has been mapped to the HTTP adapter in Cloud Integration. Click on  View Artifact to take a closer look. 
<br>![](/exercises/ex2/images/4.0_Migration_Success.png)

9.	For this particular scenario, not all attributes of the ICO on SAP Process Orchestration could be mapped to the parameters in the integration flow on Cloud Integration, so a couple of manual adjustments need to be carried out. Note, the attribute mapping will be improved with future increments of the migration tool so that manual interaction is reduced to a bare minimum. In the integration flow, switch to  Edit mode at the top right corner, and add the Namespace Mapping “xmlns:ns0=http://pi-elevation.bootcamp.com” in the Runtime Configuration of the integration flow.
<br>![](/exercises/ex2/images/5.0_View_iFlow_Changes_to_Make.png)


10. Next, click on the  XML to JSON Converter and switch to the  Processing details. Select the  Suppress JSON Root Element.
<br>![](/exercises/ex2/images/5.1_Edit_iFlow_XML_to_JSON.png)

11.	In the HTTP connection of the “Request Reply”, verify that the Authentication is set to “Basic”. The credential name is automatically mapped from the REST receiver adapter on SAP Process Orchestration. This needs to be changed to the credential name maintained on the tenant, here maintain the Credential Name “PIMAS_Demo”.
<br>![](/exercises/ex2/images/5.2_Edit_iFlow_Request_Reply.png)

12.	Next, click on the  JSON to XML Converter and switch to the  Processing details. Enter “MT_Employee_RESP” as Name and select the namespace you created earlier.
<br>![](/exercises/ex2/images/5.3_Edit_iFlow_JSON_to_XML.png)

13.	Select  Save.

14.	If you like to test the scenario, select  Deploy .Otherwise, you can proceed to the next scenario.
<br>![](/exercises/ex2/images/5.3_Edit_iFlow_Deploy.png)

15.	You can check whether your integration flow has been successfully deployed via the monitor dashboard.
<br>![](/exercises/ex2/images/6.0_iFlow_Manage_Integration_Content.png)

16.	Verify your interface with Insomia. In the Postman collection “Migration Exercise” open the “Exercise_2_Employee_Out”, update the URL so that it fits to the end point of your integration flow, and click on Send. The request should return HTTP code 200 and a response with the information that the employee has been created with success.
<br>![](/exercises/ex2/images/7.0_Insomia_Check.png)



<!--
## Exercise 2.1 Sub Exercise 1 Description 

After completing these steps you will have migrated a SOAP to REST scenario and made the manual adjustements needed for the scenario to deploy successfully.

1. 1.	Open your previously created package, and switch to the Artifacts tab, then switch to  Edit Mode.
<br>![](/exercises/ex2/images/02_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello ABAP World! | ). 
```

## Exercise 2.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

-->

## Congratulations

You've now successfully completed migration assessment and migrated scnearios from PI/PO to SAP Integration Suite using the migration tooling functionality.

<!--
Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
-->
