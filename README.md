# ms-powerplatform-aibuilder-object-detection
The project demonstrate how MS Power Platform's AI builder can be used to create a MLM to identify objects from images. The developed model can also be integrated in a Power App or Power Automate Flow. This project was part of the micro degree on Power Platform, organized by Microsoft and Kajaani University of Applied Science in Finland.

## Objective

1. To determine the type of green tea from package(s) detected from images
2. Using this capability into a MS Power App (Canvas type)
3. Using this capability into A Power Automate Flow.

## Used Services

1. MS Power Platform AI Builder: AI-enabled business solutions can be built quickly for streamlining workflows. Comes with MS Copilot to enhance productivity. Usecases include (but not limited to) document processing (invoice processing, email analysis, document dematerialization, etc.) and object identifications (object counting, brand logo recognition, object recognition and learning, etc.)
2. MS Power Platform Power Apps: Enables to build professional business solutions with low/no code development. Two types of applications, model-driven and canvas, can be implemented from scratch or with the help of MS Copilot 
3. MS Power Platform Power Automate: Allows to optimize business processes by end-to-end automation. It is scalable to extend across the organization with built-in security, governence and 360 degree monitoring. Automated processes can be integrated  with Power Apps, Copilots, websites, etc.

## Prior Preparations
- Signing up to MS Power Platform using a work or school account from Microsoft. The account might already have a trial license associated to use the Power Platform services.
- If IT admins have disabled free trials, the system will notify this upon sign-up. You can contact your administrators or proceed to create a free Azure AD account instead.
- Instructions to activate free Azure AS trial to access MS Power Platform can be found [here](https://learn.microsoft.com/en-us/power-apps/maker/signup-for-powerapps).
- Alternatively, a [MS Power Platform Developer plan](https://www.microsoft.com/en-us/power-platform/products/power-apps/pricing) can be used to access the Power Platform services.
- Signing in to access Power Platform


## Actions Executed
1. Creating, testing and publishing a machine learning model (MLM) to identify green tea types from packages detected from testing images
2. Integrating the created MLM into a MS Power App (Canvas App)
3. Integrating the created MLM into a Power Automate Flow

## Creating the Machine Learning Model

1. In Power Apps or Power Automate, the AI Models (Previously AI Builder) can be found from the left panel.
2. Click AI Models > Images (on top of the page). Then select "Detect custom objects in images".
3. On the preview window, click `Create Custom Model`


### Things to consider:
1. Max 6 MB of image sizes to trainin. Supported formats: JPG, PNG, BMP. Minimum width / height of 256 pixels x 256 pixels
2. For each tag created, there should be atleast 15 relevant images to train the model. AI Builder would indicate the readiness of each tags and how many objects have been identified for a specific tag during the MLM creation.
