# Exercise 3 - Migrate and Test SOAP to REST Scenario

In this exercise, we will create migrate a SOAP to REST scenario. 9.	For this particular scenario, not all attributes of the ICO on SAP Process Orchestration could be mapped to the parameters in the integration flow on Cloud Integration, so a couple of manual adjustments will need to be carried out which we will do as a part of the exercise.

1. Open your previously created package, and switch to the <b>Artifacts</b> tab, then switch to <b>Edit</b> Mode.
<br>![](/exercises/ex3/images/1.OpenPreviousPackage.png)

2. Click on <b>Migrate</b> to start the migration wizard.
<br>![](/exercises/ex3/images/2.0_ClickOnMigrate.png)

3.	Configure the SAP Process Orchestration system as before. For this expand the Name section and choose your system. Lastly, click <b>Next Step</b> to proceed with configuring the scenario.
<br>![](/exercises/ex3/images/3.0_Migrate_SelectPO_System.png)

4.	Click on <b>Show Filters</b> and fill in “http://pi-elevation.bootcamp.com“ for <b>Namespace</b>. Choose the interface <b>“SI_Employee_Out”</b> from the drop-down list. Click <b>Next Step</b>.
<br>![](/exercises/ex3/images/3.1_Migrate_SelectPO_Artifacts.png)

5.	The template “P2P_SYNC_JSON_REC_0001” should already be selected. Click <b>Next Step</b>. 
<br>![](/exercises/ex3/images/3.2_Migrate_SelectPO_Template.png)

6.	Maintain a Name for your integration flow, e.g., following the pattern soap_to_rest_sync_\<user<b>xx</b>\> where <b>xx</b> is your user number from 00 to 99. Then, click on <b>Review</b>.
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/d2dc66bd-62bd-40ef-aad9-5685d20b9fef)

7.	Verify the information and click on <b>Migrate</b>.
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/82e82c77-21ac-49de-a29e-fca919d8efc0)

8.	Again, the integration flow will be generated within your integration package. As you can see from the summary page, the REST receiver adapter on SAP Process Orchestration has been mapped to the HTTP adapter in Cloud Integration. Click on  View Artifact to take a closer look. 
<br>![](/exercises/ex3/images/4.0_Migration_Success.png)

9.	For this particular scenario, not all attributes of the ICO on SAP Process Orchestration could be mapped to the parameters in the integration flow on Cloud Integration, so a couple of manual adjustments need to be carried out.<br>
Note, the attribute mapping will be improved with future increments of the migration tool so that manual interaction is reduced to a bare minimum.<br>
Click on <b>Configure</b>
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/adf766e5-39a7-4a6a-a0cd-a087c0660efa)

10. Switch to tab <b>More</b> and select <b>"XML to JSON Converter" as Type</b>.
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/abd693af-a220-481c-95d2-8ce6fa32e1bd)

11. <b>Enable "Suppress JSON Root Element"</b> and press <b>Save</b>.
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/b1c96604-44a0-4d69-84b7-e1c70958fa75)

12. Press <b>Close</b> to close the Message box and <b>close</b> the configure Pop-Up as well.
  <br>  ![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/64e0f7f8-5f13-4669-b06b-d8974c76e9a5)

13. Switch to <b>Edit</b> mode at the top right corner
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/59e162de-fc10-4702-9bd4-4429cfc351bc)

14. Add the <b>Namespace Mapping “xmlns:ns0=http://pi-elevation.bootcamp.com”</b> in the <b>Runtime Configuration</b> of the integration flow.
<br>![](/exercises/ex3/images/5.0_View_iFlow_Changes_to_Make.png)

15.	In the HTTP connection of the “Request Reply”, verify that the Authentication is set to “Basic”. The credential name is automatically mapped from the REST receiver adapter on SAP Process Orchestration. This needs to be changed to the credential name maintained on the tenant, here maintain the Credential Name “PIMAS_Demo”.
<br>![](/exercises/ex3/images/5.2_Edit_iFlow_Request_Reply.png)

16.	Next, click on the  JSON to XML Converter and switch to the <b>Processing details</b>. Enter <b>“MT_Employee_RESP”</b> as <b<Name</b> and <b>select the namespace</b> you created earlier.
<br>![](/exercises/ex3/images/5.3_Edit_iFlow_JSON_to_XML.png)

17.	Press <b>Save</b> and then <b>Deploy</b> to deploy the integration flow.
  <br>  ![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/3d598e71-4e98-4c94-b574-2fd370357fb0)

18. You can check the deployment status via the monitor dashboard. Navigate to <b>Monitor > Integrations</b>, and select the <b>Manage Integration Content</b> tile.
 <br>   ![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/4e02fbcd-7789-4c8d-83b5-a1994deaca73)
   
19. Your integration flow should be in status <b>Started</b>. From here, you get the endpoint that you need to call to test the scenario. <b>Copy the endpoint</b> as we will use it in the next step.
   <br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/defda659-1542-4cdd-99f4-7732d0cd7742)


## Verify the Interface via Insomnia

1.	Open Insomnia and <b>duplicate</b> the Request you created in exercise 2. 
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/f38c37a9-ebe7-4891-bc99-3d633841d5b3)

2. As name provide "Employee" and press <b>Create</b>.
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/fe96cd82-3a74-4467-bd4b-35c14056847a)

3. <b>Replace the URL</b> with the endpoint of your new integration flow.
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/d5cf1d5b-9c2a-4a99-a152-3eee38c9312a)

4. Replace the XML Payload to following value:
  ```xml
<soapenv:Envelope
    xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:pi="http://pi-elevation.bootcamp.com">
    <soapenv:Header />
    <soapenv:Body>
        <pi:MT_Employee_REQ>
            <employee_name>John Doe 124</employee_name>
            <employee_salary>320800</employee_salary>
            <employee_age>60</employee_age>
            <profile_image></profile_image>
        </pi:MT_Employee_REQ>
    </soapenv:Body>
</soapenv:Envelope>
```
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/3d105a27-cc64-4f0a-ab41-add7b5c42905)

5. Press <b>Send</b>. Response should be "200 OK".
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/1b44d138-5470-4f86-876f-d67a152d824e)




## Congratulations

You've now successfully completed migration assessment and migrated scnearios from PI/PO to SAP Integration Suite using the migration tooling functionality.

