# Exercise 1 Migration Tool

After having finished the assessment of the current SAP Process Orchestration landscape and having estimated the effort needed to migrate with the Migration Assessment capability, the next step is the actual migration. The goal of the Migration Tool is to provide a semi-automated migration where interfaces in SAP Cloud Integration will be automatically created based on PI Elevation content, so that ideally 60-70% of technical migration efforts are automated. The migration of scenarios is based on a template approach, which means that integration flow templates are used as a skeleton to migrate the content and create the final integration flows. Additional templates are already on the roadmap. 


## Create a Cloud Integration package

In this exercise, we will migrate SOAP to SOAP interface. As a prerequisite, you first need to create an integration package where the automatically generated integration flows are created.

1. Switch back to the SAP Integration Suite landing page.
  <br>![](/exercises/ex1/images/Navigate_Back.png)
2. Navigate to  Design  Integrations, and select  Create.
   <br>![](/exercises/ex1/images/Create_Pack.png)
3. Fill in  the Name, e.g., Demo_<userxx> where xx is from 00 to 99, and a short description eg <Migrate SOAP to SOAP>. Then  Save.
    <br>![](/exercises/ex1/images/Create_Pack.png)
4. In the package you just created, you should be already in Edit mode. If not, on the top right click  Edit.
5. Click on  Migrate to start the migration wizard.
   <br>![](/exercises/ex1/images/Migrate.png)
6. Select the SAP Process Orchestration system for which the assessment was previously done. For this expand the  Name section and select your system from the drop-down menu. click  Next Step to proceed with configuring the scenario.
    <br>![](/exercises/ex1/images/PO_sys.png)
7. Currently, only Integrated Configuration Objects (ICO) are supported. You can use the filter to filter out the list of ICOs and choose the appropriate scenario.  Click on Show Filters and fill in “http://pi-elevation.bootcamp.com“ as Namespace. Choose the interface “SI_NumberConversion_Out” from the drop-down list. Click  Next Step.
   <br>![](/exercises/ex1/images/Namespace_Next.png)

After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex1/images/01_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello World! | ). 
```



## Migrate SAP Process Orchestration Artifacts (SOAP to SOAP scenario)

## Deploy migrated artifacts

## Test it via Insomnia



After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

