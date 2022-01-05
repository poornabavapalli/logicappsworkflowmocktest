# Logic Apps Workflow Mocktest
Test Azure Logic Apps workflows using mock data

This demo details steps to create logic apps and how to set up mock data on an action in a logic app workflow

* **Date:** 10 Jan 2022
* **Squad:** Integration
* **Duration:** 30 minutes

## Pre-requisites

Azure account and subscription

Office 365 Outlook or Outlook.com email account that works with Logic Apps

## Scenario

This example uses the Recurrence trigger and Office 365 Outlook connector. In the workflow we will be setting up mock data for the Outlook 365 send mail action.On succesful run, Logic App just returns the mock data provided, rather than call Outlook and send an email.

## Create a Logic App
1. Sign in to the [Azure portal](https://ms.portal.azure.com/#home) with your Azure account
2. In the Azure search box, enter **logic apps**, and select **Logic apps**.
![image](https://user-images.githubusercontent.com/38941010/148082159-1339c9ae-7277-49c7-b8af-ee0775c009fa.png)
3. On the **Logic apps** page, select **Add**.
![image](https://user-images.githubusercontent.com/38941010/148082230-ea0b41cb-caa2-483d-a122-4c82862dfd8a.png)
4. On the **Create Logic App** pane, select the **Azure subscription** to use, create a **new resource group** for your logic app resource, and provide basic details about your logic app resource.
![image](https://user-images.githubusercontent.com/38941010/148082526-2be186ad-725b-4939-acea-4f2be215c7e3.png)
5. Select **Review + Create**. On the validation page, confirm the details that you provided, and select **Create**.
6. After Azure successfully deploys your app, select **Go to resource**. Or, find and select your logic app resource by typing the name in the Azure search box.

   ![image](https://user-images.githubusercontent.com/38941010/148086749-4350be79-64ed-45b1-896b-0b80601f69c8.png)
 
   The workflow designer opens and shows a page with an introduction video and commonly used triggers
7. Under **Templates**, select **Recurrence Trigger**.
   Set the **interval** and **frequency** for the recurrence. In this scenario, set these properties to run your workflow every minute.
9. Select **New step**. Under **Choose an operation**, select **All**
10. In the search box, enter **outlook** so that you can find connector. Select **Office 365 Outlook **
![image](https://user-images.githubusercontent.com/38941010/148197317-8d66e5d1-711e-45f4-b3e2-4cdb34239ca4.png)
10. You can now more easily find and select the action that you want, for example, **Send an email**:
![image](https://user-images.githubusercontent.com/38941010/148198609-881bb57a-0123-4be2-a3d5-2d4b6189535a.png)
11. If your selected email service prompts you to sign in and authenticate your identity, complete that step now.
![image](https://user-images.githubusercontent.com/38941010/148198872-108806ef-5906-4d5e-a1b2-3f955d7ccb8c.png)
12. In the Send an email action, specify the information to include in the email.
    **To** : Enter your email address
    **Subject**: Logic Apps testing
    **Body**: Logic app testing using mock data
13. Save your logic app. On the designer toolbar, select **Save**

## Run your workflow
1. To check that the workflow runs correctly, you can wait for the trigger to run based on the set schedule. Or, you can manually run the workflow by selecting Run on the workflow designer toolbar
2. Succesful workflow sends an email for each run
![image](https://user-images.githubusercontent.com/38941010/148200964-cca15072-c5f6-48d7-a87d-bb921d4d2950.png)

## Enable mock data output
1. Open your logic app workflow in the designer
2. On the outlook action where you want to return mock data, follow these steps:
   - a. In the action's upper-right corner, select the ellipses (...) button, and then select **Testing**.
   - b. On the **Testing** pane, select **Enable Static Result (Preview)**. When the action's required (*) properties appear, specify the mock output values that you want to           return as the action's response.
     - The properties differ based on the selected action type. For example, the Outlook action has the following required properties
       - **Status**	      _The action's status to return_
       - **Status Code**	_The specific status code to return as output_
       - **Headers**     	_The header content to return_
![image](https://user-images.githubusercontent.com/38941010/148205138-9aa9dc9d-5e95-4faa-8c80-4f79be9592b1.png)

3. For optional properties, open the **Select optional fields** list, and select the properties that you want to mock.
![image](https://user-images.githubusercontent.com/38941010/148208947-8ddbde3d-6038-4156-b909-2c50e51168f1.png)

4. When you're ready, select **Done**.
   In the action's upper-right corner, the title bar now shows a test beaker icon (Icon for static result), which indicates that you've enabled static results.
![image](https://user-images.githubusercontent.com/38941010/148201352-23995924-89df-4a22-96d4-38fc8f4ca525.png)

## Find runs that use mock data
To find earlier workflow runs where the actions use mock data, review that workflow's run history.

1. In the Azure portal, open your logic app workflow in the designer.
2. On your logic app resource menu, select **Overview**.
3. Under the **Essentials** section, select **Runs history**, if not already selected.
4. In the **Runs history** table, find the **Static Results** column.
   Any run that includes actions with mock data output has the **Static Results** column set to **Enabled**, for example:
![image](https://user-images.githubusercontent.com/38941010/148208327-87380998-678d-44ba-9b6f-b888d4fbf4d7.png)

5. To view that actions in a run that uses mock data, select the run that you want where the **Static Results** column is set to **Enabled**.
   Actions that use static results show the test beaker (Icon for static result) icon, for example:
![image](https://user-images.githubusercontent.com/38941010/148201798-ef64b9a8-c05b-4be5-8efc-50004898363a.png)

## Clean up resources
When you are done with this hand-on, delete the sample logic app resource and any related resources by deleting the resource group that you created

## Contributors
* Poorna Bavapalli - poorna.bavapalli@microsoft.com
