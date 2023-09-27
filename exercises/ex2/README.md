# Exercise 2 - Create Employee Scenario (SOAP to REST)

In this exercise, we will create migrate a SOAP to REST scenario. 9.	For this particular scenario, not all attributes of the ICO on SAP Process Orchestration could be mapped to the parameters in the integration flow on Cloud Integration, so a couple of manual adjustments will need to be carried out which we will do as a part of the exercise.

1. Open your previously created package, and switch to the Artifacts tab, then switch to Edit Mode.
<br>![](/exercises/ex2/images/1.OpenPreviousPackage.png)
2. 

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

## Summary

You've now ...

<!--
Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
-->
