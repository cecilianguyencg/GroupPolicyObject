# Creating a New Group Policy Object (GPO)

## Video Demonstration
### [YouTube: Creating a New Group Policy Object (GPO) in Active Directory Domain](https://www.youtube.com/watch?v=B9c8gPlvLdY)

## Description
I'll walk through creating a new group policy object (GPO) to set a default wallpaper for an Organizational Unit (OU) for an Active Directory domain that I previously set up in another project. 
### [YouTube: Setup Active Directory Home Lab and Adding Users with PowerShell](https://www.youtube.com/watch?v=4CahkQ1Ewko) 

## Languages and Utilities Used

- Oracle VirtualBox
- Group Management

## Environments Used

- Server 2022

## Program Walk-Through

1. Open up VirtualBox and select the DC server that already has Active Directory installed on it..
2. To create a new group policy object, open the Group Policy Management application either by typing group in the Windows start menu or opening it up from Server Manager.
> Group Policy Management lets you set policies to manage how machines in your domain act. It can apply policies to the whole domain or to separate OUs or Organizational Units.

![Server manager](https://i.imgur.com/yOMRaOQ.png)

![Search](https://i.imgur.com/TsAnP8v.png)

3. Let’s add a new policy to the **_ADMINS** OU that’s already been created in the domain, in my case it’s called mydomain.com. Right-click on the **_ADMINS OU** and select **Create a GPO in this domain, and Link it here…**

![Create GPO](https://i.imgur.com/Icsejpp.png)

4. I want to create a group policy to set a default wallpaper for the **_ADMINS** OU, so I’ll call this policy **New Wallpaper** and click **OK**.
5. The policy will be added under **Group Policy Objects** and a link will be added under the **_ADMINS** OU . Let’s edit the policy by right-clicking on **New Wallpaper** and selecting **Edit**. Here you can configure all settings that can be set in a group policy. 
6. The **Group Policy Management Editor** appears and is where you can configure all settings that can be set in a group policy. To set the wallpaper, you’ll need to find this setting by going to **User Configuration, Policies, Administrative Templates, Desktop, Desktop**.
7. Double-click on **Desktop Wallpaper** in the **Setting** pane. 

![Edit](https://i.imgur.com/jEuBJz0.png)

8. To set the value of the wallpaper, click **Enabled** and enter the path for the wallpaper. This can be a local path on the machine or a network path on a server. I’ve saved mine to the Pictures folder on this machine: C:\Users\a-cnguyen\Pictures\wallpaper.jpg. For **Wallpaper Style**, I've also selected **Center**.

![Set Value](https://i.imgur.com/AwL5gzG.png)

9. Click **OK** and to verify this new group policy is enabled, go back to the **Group Policy Management** application and click on the **Settings** tab of the new policy and you’ll see that it says it’s **Enabled**.

![Enabled](https://i.imgur.com/xMWwh8I.png)

10. Right now, the desktop wallpaper is the default Windows one. To see this new group policy go into effect, log out of this account and log back in.

![Default](https://i.imgur.com/0ix7dsD.png)

11. Put in your password and now you’ll see the account has the new wallpaper set up from the newly created **Group Policy Object**.

![New](https://i.imgur.com/gdK4q6d.png)
