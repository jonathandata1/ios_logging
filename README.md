
![iOS Logging](https://i.postimg.cc/pVfhczyX/0-E58-B055-44-DB-4-FED-B40-B-4-CC654-E02-B63.jpg)

# iOS Logging
> #### Jonathan Scott - @jonathandata1
> #### Date: October 7th,2021
> #### Version 1.0

# Summary

### This repo contains the .mobileconfig files that you are able to download if you are an apple developer to help you debug your applications. The interesting part about all of these debug tools is the amount of data that can actually be gathered. 

### Some will say...well these are debug tools, of course you're going to be able to get more data than you normally should. The issue lives in the fact that the code to have this extensive logging is already written and embedded into the iOS kernel.

### These .mobileconfig files are simply enumerators for services, and boolean switchers for entitlements that are already built into the iOS ecosystem. 

# What's included

AccountsAuthKit.mobileconfig
AdPlatformsLogging.mobileconfig
AirTags.mobileconfig
AppSSO.mobileconfig
AppleConfigurator.mobileconfig
Baseband.mobileconfig
BatteryLife.mobileconfig
CFNetworkDiagnostics.mobileconfig
CalendarReminders.mobileconfig
ClassroomDebug.mobileconfig
CloudKit.mobileconfig
DataAccess.mobileconfig
Digital_Car_Key.mobileconfig
FSMetadata.mobileconfig
GSSDebugProfile.mobileconfig
HealthKit.mobileconfig
Home.mobileconfig
Launch_Hang_Diagnostics.mobileconfig
LocationAndMotion.mobileconfig
ManagedConfiguration.mobileconfig
MegaWifiProfile.mobileconfig
MobileMail.mobileconfig
NotesDebugLogging.mobileconfig
PerformanceTrace.mobileconfig
Photos_iOS.mobileconfig
ProximityReader.mobileconfig
ReportMemoryException.mobileconfig
SignificantLocations.mobileconfig
SiriDebugLogging.mobileconfig
Spotlight.mobileconfig
StreamLoggingWithConsent.mobileconfig
SwiftPreviews.mobileconfig
TailspinProfile.mobileconfig
TestFlightLoggingProfile.mobileconfig
TouchID.mobileconfig
UI_Hang_Diagnostics.mobileconfig
VPN.mobileconfig
WalletFull.mobileconfig
carplay.mobileconfig
iCloudBackup.mobileconfig
iCloudDrive.mobileconfig
iCloudKeyValue.mobileconfig
iOSBluetoothLogging.mobileconfig
iWorkDiagnosticsProfile.mobileconfig
iapd_debug_profile.mobileconfig
intercomlogging.mobileconfig
itmsdebugging.mobileconfig
loggingiOS.mobileconfig
mDNSResponder.mobileconfig
mapslogging.mobileconfig
promotedcontent.mobileconfig

# Tools needed
 1. `brew install libimobiledevice`
 2. iPhone 6 or higher running iOS 11 and higher

# How to install

1. after you download these .mobileconfig files you will need to send them to your phone. You can do this a few ways, airdrop one of these files to your phone and you will see a prompt asking to install
2. Go to Settings > General> VPN & Device Management and install the mobileconfig
![iOS Logging](https://i.postimg.cc/LsGDDL53/IMG-0150.png)
3. When the mobileconfig is downloaded you will see it in your list of configurations
![iOS Logging](https://i.postimg.cc/QxSqPRVt/IMG-0151.png)


# Gathering The Data

1. Depending on the .mobileconfig you installed, you may be asked to restart your device.
2. Actively use your device for about 15 minutes in order to gather enough data
3. Press volume up + volume down + power at the same time and then release. You will feel a buzz and possibly even take a screenshot (this is ok)
4. Wait another 10 minutes for the sysdiagnose to compress the data in your phone
5. Plugin your phone to your computer
6. If a trust dialogue comes up on the phone press trust and enter your passcode to trust if required
7. Open a terminal and type the following `idevicecrashreport -e -k -d .`

#### You should start to see an output that looks similar to this this.
![iOS Logging](https://i.postimg.cc/j5dx8w1C/Screen-Shot-2021-11-07-at-9-53-04-PM.png)

9. Once complete you will see a lot of files, and among those file will be a directory called "DiagnosticLogs," open that directory
10. You will now see a directory called,  "sysdiagnose," open that directory
11. Now you will see a compressed file that could be anyware from 50MB to 3+ GIGS, and should have a similar name to this: sysdiagnose_2021.10.19_03-55-36-0500_iPhone-OS_iPhone_19A404.tar.gz 
12. Use a decompressor app if you are not using a Mac, or double click on this file if you are on a Mac, and it will extract the decompressed information. 
