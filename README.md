## My-intune-training
This repository documents me learning Microsoft intune. Microsoft Intune is an MDM solution provided by Microsoft. I wanted to learn Microsoft intune because it has a nice integration with Entra ID, where Intune defines compliance but relies on Entra ID to handle storage of identities and conditional access.Entra Id serves as a gate that only allows access to your device and organizations resources if Intune has labelled the device as being compliant. 

Some of my goals are
1. To troubleshoot common scenarios
2. Understanding intune in multiple OSes- the different requirements, what Apple allows Intune to do, and how things can fail.
3. Using autopilot to handle device provisioning.
4. Learning Entra Id for managing cloud based identities.

## Set up and enrolling my first device

I have one windows 11 computer and an Iphone.

After I joined my Windows computer to the entra domain and had the MDM authority set to intune, my device enrolled itself into Intune.

For IOS devices the process is different: Apple will not allow intune to provide any MDM unless a APN certificate is there. The certificate is what gives intune the authority to manage the device. Importantly, the certificate is only valid for 365 days, and without it, you will see the device on the intune portal but it is no longer being synced to intune.

First go to Intune portal> Apple devices > enrollment and download the CSR file. Upload the CSR file to apple, and download the pem. This proccess is a three way handshake with Apples server that gives Intune the rights to manage an Apple device.
<img width="833" height="562" alt="image" src="https://github.com/user-attachments/assets/267e2eb6-29b9-41fd-b6af-e503e94b813e" />

<img width="611" height="286" alt="image" src="https://github.com/user-attachments/assets/b56a4f78-3437-453b-bb40-88ee79b4e97e" />


# Security groups/ Dyanmic groups/ RBAC
Its best practice to assign licenses through groups in order to do this at scale. I wanted to practice dynamic groups which populate by setting attributes when you form the group. To set the attribute, click new group > Membership type, Dyanmic and then add it. For the NewHires group, this rule will add a user if their hire date is within the last 30 days. Testing this group is done by clicking validate rules, and select a test user to see if that group assignment picks up

<img width="839" height="498" alt="setup dynamicgroup" src="https://github.com/user-attachments/assets/e13af3c9-a2fc-4b63-9787-278c30ea291a" />

<img width="661" height="408" alt="Screenshot 2026-05-10 120612" src="https://github.com/user-attachments/assets/3f7ac09e-125a-455d-9348-ab167083e520" />


<img width="560" height="95" alt="Screenshot 2026-05-10 120616" src="https://github.com/user-attachments/assets/1525b957-81c0-410f-8069-78b821b9e591" />

The green check mark means the assignment picked up! If I now assign licenses to the group, Entra will process the membership rule and provision a license to the user.





