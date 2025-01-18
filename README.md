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
2. Click **AI Models** > **Images** (on top of the page). Then select **Detect custom objects in images**. </br></br>
![image](https://github.com/Nazarah/ms-powerplatform-aibuilder-object-detection/blob/main/images/2-model-domain-and-naming.png)
4. On the preview window, click `Create Custom Model`
5. On **Select Domain** view, click on `Common Objects`. Here, the project can be renamed as well. This model has been named as **Green tea type**. </br></br>
![image](https://github.com/Nazarah/ms-powerplatform-aibuilder-object-detection/blob/main/images/2-model-domain-and-naming.png)
6. Click `Next`.
7. On **Choose Objects** view, object names to be identified from training/test images can be added. These will be used later for tagging objects in training images. For training this model, the object names added are **Green Tea Mint**, **Green Tea Cinnamon**, and **Green Tea Rose**. </br></br>
![image](https://github.com/Nazarah/ms-powerplatform-aibuilder-object-detection/blob/main/images/3-object-naming.gif)
8. Click `Next`
9. In **Add images** view, training images will be added. Images can be added from local storage, SharePoint or Azure Blob storages. The images used for training the model can be found downloaded from [here](https://github.com/Nazarah/ms-powerplatform-aibuilder-object-detection/blob/main/sample-data/ObjectDetection_GreenTea.zip). The images under **train** folder should be used. </br></br>
![image](https://github.com/Nazarah/ms-powerplatform-aibuilder-object-detection/blob/main/images/4-add-image.gif) </br></br>

**IMPORTANT: **
> For each object name defined in the previous step, there should be **atleast 15 relevant images** to train the model. While tagging objects in an image with the defined object names, AI Builder would indicate the readiness of each tags and how many objects have been identified for a specific tag during the MLM creation. </br></br>
10. After selecting the images, click `Upload <number> images`.
11. CLick `Done` on the dialog when all the images have been uploaded. Click `Next` on the **Add images** view to proceed for tagging the images.
12. In **Tag images**, view, it should be posisble to see which which images have already been tagged or not. The right side panel shows **tagging requirements** and **progress** for each object
13. Select an image to start tagging. Tagging can be performed in fullscreen. The algorithm will suggest bounding boxes around the objects in the picture that can be resized to adjust to object. Custom boxes can be also drawn and dragged across the objects on the images. (SS5 + SS6)
14. After tagging is done, click `Done tagging`. Click `Next`. 
15. In the Model Summary view, the model's details can be reviewed. </br></br>
![image](https://github.com/Nazarah/ms-powerplatform-aibuilder-object-detection/blob/main/images/7-Review.gif)
16. If everything appears acceptable, click `Train`. The training will require a couple of minutes to complete. </br></br>
![image](https://github.com/Nazarah/ms-powerplatform-aibuilder-object-detection/blob/main/images/8-train.gif)

### Things to consider:
1. **Max 6 MB** of image sizes can be used to train the model. Supported formats: **JPG**, **PNG**, **BMP**. Minimum width / height of **256 pixels x 256 pixels**. More details can be found [here](https://learn.microsoft.com/en-us/ai-builder/collect-images#format-and-size).
2. For each tag created, there should be **atleast 15 relevant images** to train the model. AI Builder would indicate the readiness of each tags and how many objects have been identified for a specific tag during the MLM creation.
3. **Test images** should be available at hand to quickly tryout the model before publishing.

## Testing the trained model

After the model has finished training, important details about the newly trained model can be viewed on a details page. (SS9)
Before publihing the model, a quick test should be done to check the effectiveness of the trained model.</br></br>

1. Images separate from the ones used for training should be used to train the data. From the bulk images provided [here](https://github.com/Nazarah/ms-powerplatform-aibuilder-object-detection/blob/main/sample-data/ObjectDetection_GreenTea.zip). The images under **train** folder should be used.
2. When the testing is complete, the detected, chosen fields and the associated confidence scores for retrieving the individual fields compared to the trained model can be viewed.


## Publishing the trained model

The model can be used into apps and flows when it is published. After the test provides satisfying scores, click `Publish` to make the model available for use.

## References

1. [Microsoft AI Builder](https://learn.microsoft.com/en-us/ai-builder/overview)
2. [Microsoft Power Apps](https://learn.microsoft.com/en-us/power-apps/powerapps-overview)
3. [Microsoft Power Automate](https://learn.microsoft.com/en-us/training/powerplatform/power-automate)

