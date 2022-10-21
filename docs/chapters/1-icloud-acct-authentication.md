------

The Apple iCloud Account is logged into when iCloud3 starts. It provides:

- Information for the devices in the Family Sharing list
- Information for the devices that are sharing their location on the FindMy App

The device information from the iCloud account s displayed on the Event Log during startup.

The Apple iCloud account username and password needs to be set up on the *iCloud Account Login Credentials* screen before that happens. The process of setting up the iCloud account, and then authenticating access to the account is described below.



### iCloud Account Login Credentials

Select *iCloud3 Configurator > iCloud Account Account Login Credentials* to display this screen.

The purpose of this screen is to:

- Enter the Apple iCloud account username and password.
- Specify the source of location information for tracked and monitored devices:
  - Apple iCloud Account only - iOS App mobile_app devices will not be monitored on any device; zone enter/exit triggers and location updates will not be available.
  - iOS App only - The username and password are not required.
  - Both the Apple iCloud and the iOS App - Normal mode of operation.
  - ​                                        <img src="../images/cf-acct-login.png" style="zoom:80%;" />  

Special Notes:

1. Select **Login** and **Submit** to login into your iCloud account. 

   - Apple will send you a notification that someone is logging into your iCloud account and display the map with the login location. 
   - Tap **Allow**  to continue and display the 6-digit verification code. 
   - Instructions for entering the 6-digit code are shown below. 
2. The password is stored in the iCloud3 configuration file in an encrypted format. It is displayed here in a hidden format.

   - Select **Show/Hide Username/Password** and **Submit** to show or hide it.




### Apple iCloud Account Authentication

When iCloud3 logs into the Apple iCloud Account the first time, and every 3-months or so after that, the *Someone is logging into your iCloud Account* notification popup is displayed on the devices.  

1. Select **Allow** on the *Someone is logging into your iCloud Account* notification popup
2. The 6-digit verification code popup window is displayed. This code is entered on the *Apple ID Verification*  configurator screen next. 
3. After a few seconds, the HA Notification alert is displayed. Tap the **Notification Alert**. The image below shows the sequence of windows you will encounter.
4. A window explaining the notification opens in the upper-left corner. Tap **Check it out**
5. The Integrations page is displayed, the red iCloud3 Configurator is displayed indicating a reauthentication is needed. Tap **Reauthenticate**
6. The Apple ID Verification Code entry window is displayed. **Enter the 6-digit verification code**.
7. Tap **Submit**

![](../images/auth-process.png)

 