# Migration Assessment

In this exercise, you will learn out how to migrate your existing integration scenarios to SAP Integration Suite with the Migration Assessment. This offering helps you estimate the technical efforts involved in the migration process and evaluates how various integration scenarios might be migrated.

## Login to Integration Suite tenant
After completing these steps you will be able to see the SAP Integration Suite landing page and view the Migration Assessment and Cloud Integration  capabilities offered as part of the SAP Integration Suite

1. Click on the link https://teched23blr07.integrationsuite.cfapps.ap10.hana.ondemand.com/shell/home
2. Enter User as userXX (where XX is from 00 to 99) and Password as Welcome1 and Click on Log On.
   <br>![](/exercises/ex0/images/Login.png)
3. In the SAP Integration Suite landing page, scroll down to Capabilities, and select   Create Requests from the Assess Migration Scenarios tile.
  <br>![](/exercises/ex0/images/Access Migration Scenarios.png)

## Checkout Configuration for Process Orchestration System
After completing these steps you will be able to test the connection between the Integration Suite tenant and PO system. Additionally, we will also walk you through the steps on how to setup your own PO system.
Note: For this exercise, the connection to a cloud connector running on the CAL system has been established, PO System is connected to the Integration Suite tenant and you do not have Admin roles to add a system.

1. Navigate to Settings and Select J2EE System to view the details.
   <br>![](/exercises/ex0/images/View_PO_System.png)
2. (Optional)After adding the system if you are setting it up in your own tenant, you can test the connection if it is successful or not. To change the connection details, you can edit it too.
3. For this exercise, system setup is already done and you click on Test Connection to check the connection to PO system.
   <br>![](/exercises/ex0/images/Login.png)
In the Migration Assessment Application, the page now displays information about the Integration Directory and, optionally, the Enterprise Services Repository you connected to your previously created system.

4. In the Migration Assessment Application, navigate to Configure > Rules.
   <br>![](/exercises/ex0/images/Configure_Rule.png)
Here you can find a list of rules predefined by SAP. Rules are a set of characteristics according to which the application evaluates whether an integration scenario can be migrated and what effort you can expect.

Note: Currently, you can’t add custom rules or edit the standard rules. You can only view the standard rules.

5. As an example, select the rule SenderAdapterType
   <br>![](/exercises/ex0/images/Select_Sender_Adapter_Type.png)
Here, you can see all the parameters of the rules, such as Rule Match Value, Assessment Category, and the Weight assigned to each rule match value. Based on these weights, the application calculates the estimated effort, which means that some parameters, and therefore rules, have a bigger influence on the final estimation than others.
   
## Create Data Extraction Request
After completing these steps you will have....

1.	Click here.
<br>![](/exercises/ex0/images/00_00_0010.png)

2.	Insert this code.
``` abap
 DATA(params) = request->get_form_fields(  ).
 READ TABLE params REFERENCE INTO DATA(param) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.
```

## Summary

Now that you have ... 
Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
