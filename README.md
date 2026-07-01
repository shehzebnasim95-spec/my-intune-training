### my-intune-training
This repository documents me learning Microsoft intune. Microsoft Intune is an MDM solution provided by Microsoft. I wanted to learn Microsoft intune because it has a nice integration with Entra ID, where Intune defines compliance but relies on Entra ID to handle storage of identities and conditional access.Entra Id serves as a gate that only allows access to your device and organizations resources if Intune has labelled the device as being compliant. When a user requests a resource like SSPR, Entra asks who the device is- John Doe logging in from Windows 11 from this location- and determines what they are allows to do.

Intune is managed in the intune portal. Here the compliance policies that will be assigned to different groups are designed, as well as the configuration profiles that will set up devices with Bitlocker, a vpn, OS version.

After I joined my Windows computer to the entra domain and had the MDM authority set to intune, my device enrolled itself into Intune. On https://intune.microsoft.com/ you can verify this.
For IOS devices the process is different: Apple will not allow intune to provide any MDM unless a APN certificate is there. The certificate is what gives intune the authority to manage the device. Importantly, the certificate is only valid for 365 days, and without it, you will see the device on the intune portal but it is no longer being synced to intune because it doesn
t have authority.

<img width="833" height="562" alt="image" src="https://github.com/user-attachments/assets/267e2eb6-29b9-41fd-b6af-e503e94b813e" />

<img width="611" height="286" alt="image" src="https://github.com/user-attachments/assets/b56a4f78-3437-453b-bb40-88ee79b4e97e" />





