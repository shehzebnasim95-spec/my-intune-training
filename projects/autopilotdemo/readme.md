
# Deploying Autopilot

### Autopilot is method for deploying windows without having to reinstall from scratch

This method requires obtaining the hash ID of the device, uploading it, and creating an Entra Identity, Autopilot security group. An autopilot deployment is then assigned to the group. 

Step 1 obtaining the hardware hash:
I used the code:

Step 2. Upload the Hardware Hash as a csv file
*In production this is not needed because the vendor will register your device in intune 

Step 3. Create an Entra security group 
Assignments : dynamic : dynamic query 

Step 4. Deploy an autopilot profile 


