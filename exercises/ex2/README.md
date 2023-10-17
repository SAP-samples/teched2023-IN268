# Exercise 2 - Migrate and Test SOAP to SOAP Scenario

After having finished the assessment of the current SAP Process Orchestration landscape and having estimated the effort needed to migrate with the Migration Assessment capability, the next step is the actual migration. The goal of the Migration Tool is to provide a semi-automated migration where interfaces in Cloud Integration will be automatically created so ideally 60-70% of technical migration efforts are automated. The migration of scenarios is based on a template approach, which means that integration flow templates are used as a skeleton to migrate the content and create the final integration flows.

## Create a Cloud Integration package

 As a prerequisite, you first need to create an integration package where the automatically generated integration flows are created and 
 then we will migrate SOAP to SOAP interface.

1. Switch back to the SAP Integration Suite landing page.
  <br>![](/exercises/ex2/images/Navigate_Back.png)

3. Navigate to  <b>Design > Integrations</b>, and select  <b>Create</b>.
   <br>![](/exercises/ex2/images/Create_Pack.png)
   
5. Fill in the <b>Name</b>, e.g. Demo_\<user<b>xx</b>\> where <b>xx</b> is your user number from 00 to 99, and a short <b>description</b> eg <Migrate SOAP to SOAP artifact>. Then click <b>Save</b>.
    <br>![](/exercises/ex2/images/Save_Pack.png)
   
## Migrate SAP Process Orchestration Artifacts (SOAP to SOAP scenario)

Every ICO that can be migrated has an associated template in the migration tooling. It's based on these templates, the migration tooling creates equivalent integration flows in the SAP Integration Suite. Let's start with the actual migration.

1. In the package you just created, you should be already in Edit mode. If not, on the top right click <b>Edit</b>.
   <br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/0c61b24e-18c1-423a-a598-a87577ac010d)

   
3. Switch to tab <b>Artifacts</b> and click on  <b>Migrate</b> to start the migration wizard.
   <br>![](/exercises/ex2/images/Migrate.png)
   
5. <b>Select the SAP Process Orchestration system</b> for which the assessment was previously done. For this, expand the Name section and select your system from the drop-down menu. Click <b>Next Step</b> to proceed with configuring the scenario.
    <br>![](/exercises/ex2/images/PO_sys.png)
   
7. Currently, only Integrated Configuration Objects (ICO) are supported. You can use the filter to filter out the list of ICOs and choose the appropriate scenario.  Click on <b>Show Filters</b> and fill in “http://pi-elevation.bootcamp.com“ as <b>Namespace</b>. Choose the <b>interface “SI_NumberConversion_Out”</b> from the drop-down list. Click <b>Next Step</b>.
   <br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/da75731d-d657-4364-b301-de48e2fe1117)

   
9. The best-fit template is identified by the migration framework and will be automatically filled in for you. In this case, it will be “P2P_SYNC_0001”. Click <b>Next Step</b>.
    <br>![](/exercises/ex2/images/Template.png)
   
11. Maintain any Name for your integration flow, e.g. following the pattern: soap_to_soap_sync_\<user<b>xx</b>\> where <b>xx</b> is your user from 00 to 99. Note, that the ID of your integration flow needs to be unique across all integration flows on the tenant. Click on <b>Review</b>.
    <br>![](/exercises/ex2/images/Int_Name_Review.png)
    
13. Verify the information and then click on <b>Migrate</b>.
    <br>![](/exercises/ex2/images/Final_Migrate.png)
    
15. A new integration flow has been generated within your package. Click on the artifact to take a closer look at each individual step. The required information is automatically populated such as the connection information. Click on <b>View Artifact</b>.
   <br> ![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/afce1689-5586-4813-a77f-7db9f3bdef2e)


## Deploy migrated artifacts

After completing these steps you will be able to deploy the Integration flow and monitor your scenario
    
1.  Click on the <b>SOAP Adapter</b> and view the <b>Connection</b> details. You can see that the endpoint address has been automatically set based on the integration flow name that you have entered.
    <br>![](/exercises/ex2/images/Open_Iflow.png)
    
2. For this particular scenario, no manual steps need to be carried out. It should run as is. Select <b>Deploy</b> to get the integration flow deployed on the tenant runtime.
    <br>![](/exercises/ex2/images/Deploy_Con.png)
   
3. You can check the deployment status via the monitor dashboard. Navigate to <b>Monitor > Integrations</b>, and select the <b>Manage Integration Content</b> tile.
    <br>![](/exercises/ex2/images/Monitor_Int.png)
   
4. Your integration flow should be in status <b>Started</b>. From here, you get the endpoint that you need to call to test the scenario. <b>Copy the endpoint</b> as we will use it in the next step.
    <br>![](/exercises/ex2/images/Copy_endpoint.png)
   
Now you are all set to test your scenario!

## Verify the Interface via Insomnia

After completing these steps you will be able to test the interface and get the desired result of converting a number into a text.

1. Open Insomnia and click on <b>Use the local Scratch Pad</b>
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/5cc2dff9-b872-4746-8e62-234961db2a6b)

2. Create a <b>New HTTP-Request</b>.
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/9972321f-adb2-4637-a55d-81d36f1754ea)

3. <b>Change the Request Method from GET to POST</b>, by clicking the dropdown icon next to GET.
 <br>  ![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/5741a591-a781-4cf0-b74d-ddb644434ef4)

4. <b>Paste the endpoint</b> from you integration flow as URL.
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/0f81d52f-f8f7-4709-b97b-fac0c24ad4cc)

5. Add a <b>Body</b> of type XML.<br>
 <br>  ![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/d0a2c83c-8313-443d-bcea-e841f11b0cdb)

6. Provide following payload:
  ```xml
<soapenv:Envelope
    xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
    xmlns:pi="http://pi-elevation.bootcamp.com">
    <soapenv:Header />
    <soapenv:Body>
        <pi:MT_NumberConversion_REQ>
            <number>1389</number>
        </pi:MT_NumberConversion_REQ>
    </soapenv:Body>
</soapenv:Envelope>
```

<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/1fce6a4d-15d4-45ce-b4e7-90d5e38dc51a)

7. Switch to tab <b>Auth</b> and choose <b>Basic Auth</b>
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/0cf19b1f-8dae-4094-8e35-2631b5eabd7d)

8. Provide following credentials:<br>
<b>Username</b>: sb-0f0c8c67-655f-4cf4-beff-98b7fdbdaecc!b3814|it-rt-teched23blr11!b68<br>
<b>Password</b>: 5abe805e-e0e6-42a0-864c-bc8bbba360b5$rFhomkIHs7BNnWic5VWMAz1asCp5uR5LRIX0Z62n7lw=
<br> ![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/24e94326-0394-41c8-b8df-2cbb0e88da58)



10. Press <b>Send</b>. The request should return HTTP code 200 and a response with the converted text.
<br>![image](https://github.com/SAP-samples/teched2023-IN268/assets/118828983/f8f11abd-42df-464b-8135-e24832e0f008)

## Summary - Congratulations You have successfully tested your scenario now.

Continue to - [Exercise 3 - Migrate and Test SOAP to REST Scenario](../ex3/README.md)

