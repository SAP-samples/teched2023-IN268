<!-- [![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2023-IN268)](https://api.reuse.software/info/github.com/SAP-samples/teched2023-IN268) -->

# IN268 - Start with the Right Mind-Set and Learn How to Modernize Your Integration

<!--
## Description

This repository contains the material for the SAP TechEd 2023 session called <b>IN268 - Start with the Right Mind-Set and Learn How to Modernize Your Integration</b>.  

This session will guide you on how to migrate your existing SAP Process Integration and SAP Process Orchestration (PI/PO) scenarios to SAP Integration Suite with the Migration Assessment and semi-automated Migration Tooling. Migration Assessment is a new capability within SAP Integration Suite which helps you estimating the technical efforts involved in the migration process and evaluates how various integration scenarios might be migrated. 

After having finished the assessment of the current SAP Process Orchestration landscape and having estimated the effort needed to migrate with the Interface Migration Assessment capability, the next step is the actual migration. The goal of the Migration Tool is to provide a semi-automated migration where interfaces in SAP Cloud Integration will be automatically created based on SAP Process Orchestration information, so that ideally 60-70% of technical migration efforts are automated. The migration of scenarios is based on a template approach, which means that integration flow templates are used as skeleton to migrate the content and create the final integration flows. Additional templates are already on the roadmap.
-->

## Overview

This session introduces attendees to Migration Assessment and Migration Tooling which are capabilities of SAP Integration Suite. This session will guide you on how to migrate your existing PI/PO integration scenarios to SAP Integration Suite with the Migration Assessment and semi-automated Migration Tooling.

Migration Assessment is a new capability within SAP Integration Suite which helps you estimating the technical efforts involved in the migration process and evaluates how various integration scenarios might be migrated. 

After having finished the assessment of the current SAP Process Orchestration landscape and having estimated the effort needed to migrate with the Interface Migration Assessment capability, the next step is the actual migration. The goal of the Migration Tool is to provide a semi-automated migration where interfaces in SAP Cloud Integration will be automatically created based on SAP Process Orchestration information, so that ideally 60-70% of technical migration efforts are automated. The migration of scenarios is based on a template approach, which means that integration flow templates are used as skeleton to migrate the content and create the final integration flows. Additional templates are already on the roadmap.

## Requirements

The requirements and the steps to be followed for this exercise are listed below. Please note, that the first five steps have been already done for TechEd, they are listed here for your information just in case that you like to run through the exercise on your own environment. For TechEd, we will concentrate on the other steps highlighted in bold. 

1. Download and install Insomnia. Please note that this is already done for the TechEd laptops.
2. Connect PO to tenants using Cloud Connector
3. On each tenant, provision Migration Assessment and Cloud Integration
4. Assign appropriate roles to the users
5. Setup destination to PO
5. <B>Run Data Extraction Request</B>
6. <B>Run Data Evaluation Request</B>
7. <B>Generate and Analyse the Report</B>
8. <B>Create Cloud Integration Package</B>
9. <B>Use the Migrate option to migrate scenarios</B>
10. <B>Test in Insomnia</B>

## Code of Conduct
1. Use the tenant that we provide only for this exercise, and not for anything else. For further exploration of Migration Assessment and Cloud Integration, use a free BTP trial account or a Free Tier tenant.
2. Do not share any private or personal information such as your name, email address or affiliation.
3. Please strictly follow the instructions, regarding the naming conventions you will use to name the artifacts you will create. This ensures that you will be able to successfully complete the tasks, without clashing with other participants.
4. Other artifacts, created by other participants, will appear in your shared account. Do not access or delete these artifacts. Please respect the rules and allow others to have the same learnings as you.
5. We have done everything to make this experience enjoyable. Your TechEd tenants were pre-configured by a competent technical BTP administrator, and you already have all the roles and definitions you need to complete the exercises.

Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## Exercises

<!-- Provide the exercise content here directly in README.md using [markdown](https://guides.github.com/features/mastering-markdown/) and linking to the specific exercise pages, below is an example. -->

- [Exercise 1 - Migration Assessment](exercises/ex0/)
- [Exercise 2 - Migrate and Test SOAP to SOAP Scenario](exercises/ex1/)
- [Exercise 3 - Migrate and Test SOAP to REST Scenario](exercises/ex2/)
  
<!-- **OR** Link to the Tutorial Navigator for example... 
Start the exercises [here](https://developers.sap.com/tutorials/abap-environment-trial-onboarding.html).
-->

<!--
**IMPORTANT**
Your repo must contain the .reuse and LICENSES folder and the License section below. DO NOT REMOVE the section or folders/files. Also, remove all unused template assets(images, folders, etc) from the exercises folder. 
-->

<!--
## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.
-->

## How to obtain support
Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2023 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
