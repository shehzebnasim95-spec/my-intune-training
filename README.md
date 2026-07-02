### my-intune-training
This repository documents me learning Microsoft intune. Microsoft Intune is an MDM solution provided by Microsoft. I wanted to learn Microsoft intune because it has a nice integration with Entra ID, where Intune defines compliance but relies on Entra ID to handle storage of identities and conditional access.Entra Id serves as a gate that only allows access to your device and organizations resources if Intune has labelled the device as being compliant. 

Some of my goals are
1. To troubleshoot common scenarios
2. Understanding intune in multiple OSes- the different requirements, what Apple allows Intune to do, and how things can fail.
3. Using autopilot to handle device provisioning.
4. Learning Entra Id for managing cloud based identities.

# Set up
I have one windows 11 computer and an Iphone.

After I joined my Windows computer to the entra domain and had the MDM authority set to intune, my device enrolled itself into Intune.
For IOS devices the process is different: Apple will not allow intune to provide any MDM unless a APN certificate is there. The certificate is what gives intune the authority to manage the device. Importantly, the certificate is only valid for 365 days, and without it, you will see the device on the intune portal but it is no longer being synced to intune.

Problem: On IOS the device stops syncing to intune. Solution: Check the APN certificate is valid and the Apple ID is owned by the organization. 

<img width="833" height="562" alt="image" src="https://github.com/user-attachments/assets/267e2eb6-29b9-41fd-b6af-e503e94b813e" />

<img width="611" height="286" alt="image" src="https://github.com/user-attachments/assets/b56a4f78-3437-453b-bb40-88ee79b4e97e" />
# Security groups/ Dyanmic groups/ RBAC

Before learning Intune it was important to learn how to manage groups because that is what I will have to rely on when I assign Intune policies. In entra the two main groups are
M365 groups and Security Groups. Security groups are what you want to create when youre applying permissions- for example I can create a licensing group that I assign my licenses to. Dynamic groups are not assigned, instead users are automaticaly assigned based on attributes. Here I created a new hire group that assigns users by<img width="839" height="498" alt="setup dynamicgroup" src="https://github.com/user-attachments/assets/e13af3c9-a2fc-4b63-9787-278c30ea291a" />


<img width="839" height="498" alt="setup dynamicgroup" src="https://github.com/user-attachments/assets/1bde814d-9eb9-44b3-ab50-ddd4bd5ff60c" />


<img width="661" height="408" alt="Screenshot 2026-05-10 120612" src="https://github.com/user-attachments/assets/6b319b79-6740-4dae-8490-75afda836666" />



