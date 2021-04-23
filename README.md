Ensure that you have appropriate user permissions as outlined in the Change Sets documentation to perform the following actions.

# 1.  Create Deployment Connections
1.  Log in to the target organization. This is the organization that will receive the incoming change set.(This can be production or testing ernviorment)
2.  Navigate to Setup and enter Deployment Settings into the Quick Find box.
3.  Click Edit next to the source organization name. This is the organization used to create the outbound change set.
4.  Select Allow Inbound Changes and click Save to authorize inbound changes from the source organization.

To see this information in video format, watch How to Create a Deployment Connection for a Change Set.
 
# 2.  Create Outbound Change Sets
1. Login to the source organization.
2. Navigate to Create an Outbound Change Set in Setup from the Awtestpart (testing environment. After user has approved as well CCB is approved for release).
3. Click New to create a new change set.
4. Specify a name and description (optional) and click Save.
5. Click Add to select the component and add it to the Change Set.
6. Click View/Add Dependencies.
Any components that depend on the component added in step 5 will be listed. Select the components that need to be migrated and click Add to Change Set.
7. After adding all of the desired components, click Upload to select the target organization and upload the Change Set.
 
# 3.  Review and deploy Inbound Change Sets
1. Log into the org that has received the Change Set.
2. Navigate to Viewing Inbound Change Sets in Setup.
3. Click a Change Set name to see its detail.
4. Click Validate to validate the Change Set before deploying. Validate for all the test classes in the production.
5. Once the validation completes, click View Results to check for any errors. 
6. Click Deploy to apply the change set to your org.
7. Click View Results again to see the status and individual changes or errors.
![image](https://user-images.githubusercontent.com/82831785/115885627-20ba8180-a41e-11eb-8681-ff1cf28334b1.png)
