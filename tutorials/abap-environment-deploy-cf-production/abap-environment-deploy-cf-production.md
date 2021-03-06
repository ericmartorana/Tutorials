---
auto_validation: true
title: Develop and Run SAP Fiori Application With SAP Business Application Studio
description: Develop and run your SAP Fiori application with SAP Business Application Studio
primary_tag: products>sap-cloud-platform--abap-environment
tags: [  tutorial>beginner, topic>abap-development, products>sap-cloud-platform, products>sap-business-application-studio ]
time: 25
author_name: Merve Temel
author_profile: https://github.com/mervey45
---

## Prerequisites  
- You need a SAP Cloud Platform ABAP Environment trial user or a license.
- In a licensed system, the business catalog `SAP_A4C_BC_DEV_UID_PC` (Development - UI Deployment) needs to be assigned to a business role of the developer user. For an existing ABAP systems, the business catalog needs to be added manually to the existing developer business role.


## Details
### You will learn  
- How to assign role collections
- How to create dev spaces
- How to set up organization and space
- How to create list report object pages
- How to run SAP Fiori applications
- How to deploy applications
- How to check BSP library in Eclipse
- How to create IAM apps and business catalogs

---
[ACCORDION-BEGIN [Step 1: ](Assign role collection to user)]

  1. Login to [SAP Cloud Platform trial cockpit](https://cockpit.hanatrial.ondemand.com/) and click **Enter Your Trial Account**.

      ![assign role collection](bas1.png)

  2. Select your subaccount **trial**.

      ![assign role collection](bas2.png)

  3. Select **Subscriptions** and click **SAP Business Application Studio**.

      ![assign role collection](bas21.png)

  4. Click **Subscribe**. You have now subscribed the SAP Business Application Studio and can assign the corresponding role to your user.

      ![assign role collection](bas22.png)

  5. Click **Trust Configuration** to set up your trust.

      ![assign role collection](bas3.png)

      HINT: If you are using a licensed system, make sure you have the trust administrator role assigned to your user.

  6. Select **sap.default**.

      ![assign role collection](bas4.png)

  7. Enter your e-mail address and click **Show Assignments**.

      ![assign role collection](bas5.png)

  8. Click **Assign Role Collection** .

      ![assign role collection](bas6.png)

  9. Select **`Business_Application_Studio_Developer`** and click **Assign Role Collection**.

      ![assign role collection](bas7.png)

  10. Check your result. Now your user should have the **`Business_Application_Studio_Developer`** role collection assigned.

      ![assign role collection](bas8.png)

      You are now able to develop on SAP Business Application Studio.


[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Create dev space)]

  1.  Select **trial** > **Subscriptions** > **SAP Business Application Studio** and click **Go to Application**.

      ![dev](studio.png)

  2.  Check the privacy statement and click **OK**.

      ![dev](studio2.png)

  3. Now the SAP Business Application Studio has started. Click **Create Dev Space**.

      ![dev](studio3.png)

  4. Create a new dev space:
       - Name: **Fiori**
       - Type: **SAP Fiori**
       - Additional SAP Extensions: **Launchpad Module**

       Click **Create Dev Space**.

     ![dev](studio4.png)

  5. When your status is **Running**, select your dev space **Fiori**.

      ![dev](studio5.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](Set up organization and space)]

  1. Now you are in your **Fiori** dev space in SAP Business Application Studio.
     Select **Open Workspace** to set your workspace.

      ![organization](studio6.png)

  2. Select **projects** and click **Open**.

      ![organization](studio7.png)

  3. Select **The organization and space in Cloud Foundry have not been set.**

      ![organization](studio8.png)

  4. Press enter to set your Cloud Foundry endpoint.

      ![organization](studio9.png)

  5. Enter the same e-mail address you set in your trial instance and press enter.
      ![organization](studio10.png)

  6. Enter your password and press enter.

      ![organization](studio11.png)

  7. Select your global account and press enter.

      ![organization](studio12.png)

  8. Select dev as your space and press enter.

      ![organization](studio13.png)

  9. Check your result. Now your organization and space have been set.

     ![organization](studio14.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 4: ](Create list report object page)]

  1. Select **View** > **Find Command**.

    ![object](studio15.png)

  2. Search for **Yeoman UI Generators** and select it.

    ![object](studio16.png)

  3. Select **SAP Fiori elements application** and click **Next >**.

    ![object](studio17.png)

  4. Select **List Report Object Page** and click **Next >**.

    ![object](studio18.png)

  5. Configure data source, system and service:
     - Data source: **Connect to SAP System**
     - System: **`New System`**
     - ABAP Environment: **`default_abap-trial`**
     - Service: **`ZUI_C_TRAVEL_M_XXX(1) - odata v2`**

     Click **Next >**.

     A destination for the `abap-trial` service instance is generated automatically. The naming convention is `abap-cloud-<your abap-trial service instance>`, for example, `abap-cloud-abap-trial`.

    ![object](studio19.png)

  6. Select your main entity **`TravelProcessor`** and click **Next >**.

    ![object](studio20.png)

  7. Configure project attributes:
     - Name: **`ztravel_app_xxx`**
     - Title: **Travel App XXX**
     - Description: **A Fiori application.**

     Click **Finish**.

    ![object](studio21.png)

    HINT: Your **application name must** begin with a `z letter` and **must** be in **lowercase letters**.

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 5: ](Run SAP Fiori application for data preview)]

  1. Close the wizard.

      ![run](studio22.png)

  2. Press the run button on the left side and select the **`Start ztravel_app_xxx`** run button to start your SAP Fiori application.

      ![run](studio24.png)

      HINT: An alternative to run the application is to open the terminal and enter: `npm start`.

  3. Click **Open in New Tab**.

      ![run](studio25.png)

  4. Select **`test/`**.

      ![run](studio27.png)

  5. Select **`flpSandbox.html`**.

      ![run](studio28.png)

  6. Now your SAP Fiori application runs. Select your application **Travel App XXX**.

      ![run](studio29.png)

  8. Click **Go** to see your result.

      ![run](studio30.png)

  9. Check your result.

     ![run](studio31.png)

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 6: ](Deploy your application)]

  1. Go back to SAP Business Application Studio, select projects, right-click your project **`ztravel_app_xxx`** and select **Open in Terminal**.

      ![deploy](deploy.png)

  2. To add Fiori Launchpad content use this command, enter **`npx fiori add flp-config`**.

     Add following information:

       - Semantic Object: **`ztravel_app_xxx`**
       - Action: display
       - Title: Travel App XXX
       - Subtitle (optional): press enter

       ![deploy](deploy2.png)

  3.  Open eclipse, search your package **`ZTRAVEL_APP_XXX`** and open it. Open your transport organizer to see your transport request. Copy your transport request for later use. You can find your **transport request** underneath the **Modifiable** folder.

      ![deploy](deploy3.png)

  4. To add `deploy config` details enter **`npx fiori add deploy-config`**.

     Add following information:

      - Please choose the target: ABAP
      - Is this an SAP Cloud Platform system?: Y
      - Destination: press enter for default
      - Name: press enter for default
      - Package: **`ztravel_app_xxx`**
      - Transport Request: **`<your_transport_request>`**
      - Generate standalone index.html during deployment: y

      ![deploy](deploy4.png)

      The `ui5-deploy.yaml` will be generated as part of this `deploy config` command.

  5. Enter **`npm run deploy`** to deploy your application.
     When prompted, check deployment configuration and press y.
     Open the URL at the end of the deployment log in browser to preview the application.

      ![deploy](deploy5.png)

      When the deployment is successful, you will get these two information back as a result: **UIAD details** and **deployment successful**.


[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 7: ](Check BSP library and SAP Fiori Launchpad app descriptor item in Eclipse)]

  1. Open Eclipse and check the **BSP library** and **SAP Fiori Launchpad app descriptor item folder** in your package **`ZTRAVEL_APP_XXX`**. If you are not able to see BSP applications and SAP Fiori Launchpad app description items, refresh your package `ZTRAVEL_APP_XXX` by pressing `F5`.

    ![library](library.png)

[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 8: ](Create IAM App and business catalog)]

  1. In Eclipse right-click your package **`ZTRAVEL_APP_XXX`** and select **New** > **Other Repository Object**.

      ![iam](iam.png)

  2. Search for **IAM App**, select it and click **Next >**.

      ![iam](iam2.png)

  3. Create a new IAM App:
     - Name: **`ZTRAVEL_IAM_XXX`**
     - Description: IAM App

      ![iam](iam3.png)

      Click **Next >**.

  4. Click **Finish**.

      ![iam](iam4.png)

  5. Select **Services** and add a new one.

      ![iam](iam5.png)

  6. Select following:
      - Service Type: `OData V2`
      - Service Name: `ZUI_C_TRAVEL_M_XXX_0001`    

      ![iam](iam6.png)

      Click **OK**.

      **Save** and **activate** your IAM app.

  7. Right-click your package **`ZTRAVEL_APP_XXX`** and select  **New** > **Other Repository Object**.

      ![catalog](catalog.png)

  8. Search for **Business Catalog**, select it and click **Next >**.

      ![catalog](catalog2.png)

  9. Create a new business catalog:
     - Name: **`ZTRAVEL_BC_XXX`**
     - Description: Business catalog

      ![catalog](catalog3.png)

      Click **Next >**.

 10. Click **Finish**.

      ![catalog](catalog4.png)

 11. Select **Apps** and add a new one.

      ![catalog](catalog5.png)

 12. Create a new business catalog:
     - IAM App: `ZTRAVEL_IAM_XXX_EXT`
     - Name: `ZTRAVEL_BC_XXX_0001`

      ![catalog](catalog6.png)

      Click **Next >**.

 13. Click **Finish**.

       ![catalog](catalog7.png)

 14. Click **Publish Locally** to publish your business catalog.

       ![catalog](catalog8.png)


[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 9: ](Run SAP Fiori application)]

  1. Go back to SAP Business Application Studio and deploy your changes. Therefore right-click your project **`ztravel_app_xxx`** and select **Open in Terminal**.

    ![url](url.png)


  2. Enter **`npm run deploy`**. When prompted, check deployment configuration and press y.

      ![url](url2.png)

  3. Press **`CTRL and click the following link`** to open the URL in a browser.

      ![url](url3.png)

  4. Log in to ABAP Trial.

      ![url](url4.png)

  5. Click **Go**.

      ![url](url5.png)

  6. Check your result.

      ![url](url6.png)

[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 10: ](Test yourself)]

[VALIDATE_1]
[ACCORDION-END]

<p style="text-align: center;">Give us 55 seconds of your time to help us improve</p>

<p style="text-align: center;"><a href="https://sapinsights.eu.qualtrics.com/jfe/form/SV_0im30RgTkbEEHMV?TutorialID=abap-environment-deploy-cf-production" target="_blank"><img src="https://raw.githubusercontent.com/SAPDocuments/Tutorials/master/data/images/285738_Emotion_Faces_R_purple.png"></a></p>
