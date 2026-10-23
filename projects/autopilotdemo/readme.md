
# Deploying Autopilot

### Autopilot is method for deploying windows without having to reinstall from scratch

This method requires obtaining the hash ID of the device, uploading it, and creating an Entra Identity, Autopilot security group. An autopilot deployment is then assigned to the group. 

Step 1 obtaining the hardware hash:


In powershell:Powershell
Set-ExecutionPolicy bypass
Install-Script Get-WindowsAutoPilotInfo
Get-WindowsAutoPilotInfo.ps1 -OutputFile "C:\AutoPilotHWID.csv"

/
Step 2. Upload the Hardware Hash as a csv file
*In production this is not needed because the vendor will register your device in intune 

Step 3. Create an Entra security group 
Assignments : dynamic : dynamic query: (device.devicePhysicalIDs -any (_ -startsWith "[ZTDid]"))



This group is needed to associate a deployment profile to, which will configure my VM. 

Step 4. Deploy an autopilot profile 




Screenshots:

<img width="702" height="453" alt="autopilotmanagedgroup" src="https://github.com/user-attachments/assets/2de9bba9-8f6a-44ec-af8c-3b8664023e8b" />

<img width="1105" height="275" alt="Screenshot 2026-10-23 173958" src="https://github.com/user-attachments/assets/adb3d641-3e96-493e-9e9a-6757653a3b03" />



