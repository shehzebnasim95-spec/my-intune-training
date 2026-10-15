# Wifi Profiles on Intune Windows 10

An Intune wifi profile is Intune solution for pushing wifi settings onto devices. It allows users in an organization to seamlessly access wifi.
To use it, I went to settings catalog, created a wifi profile and assigned it to my Device group Win Devices:
This profile would be used as part of a zero touch device provisioning strategy.

The goal of this lab was to practice deployment of a wifi profile.

##  Quick Start
### 1) Configure policy
1. Go to intune configuration profiles
2. Create a new wifi policy
3. Using templates catalog, choose wifi
4. Fill out SSID, and other settings before assigning it a windows device group.




<img width="588" height="419" alt="10-9-intune" src="https://github.com/user-attachments/assets/247db285-6d9e-497b-ae1e-d928e90a3b74" />

<img width="357" height="611" alt="intune-10-10" src="https://github.com/user-attachments/assets/24e044ed-02d1-42f8-b844-e09da7ab9630" />
