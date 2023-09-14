# Migration Assessment

In this exercise, you will learn out how to migrate your existing integration scenarios to SAP Integration Suite with the Migration Assessment. This offering helps you estimate the technical efforts involved in the migration process and evaluates how various integration scenarios might be migrated.

## Login to Integration Suite tenant
After completing these steps you will be able to see the SAP Integration Suite landing page and all the capabilities offered as part of the SAP Integration Suite

1. Click on the link https://teched23blr07.integrationsuite.cfapps.ap10.hana.ondemand.com/shell/home
2. Enter User as userXX (where XX is from 00 to 99) and Password as Welcome1
## Checkout Configuration for Process Orchestration System



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
