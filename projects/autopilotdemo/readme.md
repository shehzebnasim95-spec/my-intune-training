
# Deploying Autopilot

### Autopilot is method for deploying windows without having to reinstall from scratch

This method requires obtaining the hash ID of the device, uploading it, and creating an Entra Identity, Autopilot security group. An autopilot deployment is then assigned to the group. 

#Entra identity
Autopilotdemo group was used to associate a deployment profile
#Hardware Hash
6666-1189-7542-2380-xxxxx

Step 1 obtaining the hardware hash:


--In powershell:Powershell

Set-ExecutionPolicy bypass

Install-Script Get-WindowsAutoPilotInfo

Get-WindowsAutoPilotInfo.ps1 -OutputFile "C:\AutoPilotHWID.csv"

/
Step 2. Upload the Hardware Hash as a csv file
*In production this is not needed because the vendor will register your device in intune 

Step 3. Create an Entra security group 
Assignments : dynamic : dynamic query: (device.devicePhysicalIDs -any (_ -startsWith "[ZTDid]"))



This group is needed to associate a deployment profile to, which will configure my VM. 

Step 4. Create an ESP
An enrollment sign up page is what the user sees during the Autopilot set up phase. 
It enforces and tracks many things like:
App installations
User-targeted settings
Compliance checks


<img width="1103" height="168" alt="importedcsv" src="https://github.com/user-attachments/assets/da2dc1c6-2888-4184-9eab-811e793e039f" />

Screenshots:

<img width="702" height="453" alt="autopilotmanagedgroup" src="https://github.com/user-attachments/assets/2de9bba9-8f6a-44ec-af8c-3b8664023e8b" />

<img width="1105" height="275" alt="Screenshot 2026-10-23 173958" src="https://github.com/user-attachments/assets/adb3d641-3e96-493e-9e9a-6757653a3b03" />



