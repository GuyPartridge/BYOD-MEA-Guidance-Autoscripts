# BYOD-MEA-Guidance-Autoscripts
BYOD-UK-Blueprint-Auto
This GitHub is for Automating the BYOD MEA advice provided here: https://3er1viui9wo30pkxh1v2nh4w-wpengine.netdna-ssl.com/wp-content/uploads/prod/sites/133/2021/03/MEA-Blueprint-for-BYOD-Use-v1.0-Final-Version.pdf

The full article can be found here:https://news.microsoft.com/en-xm/2021/03/18/how-to-have-secure-remote-working-with-a-byod-policy/

A large number of the scripts are based on the PowerShell scripts created by Dave Falkus which can be found here: https://github.com/davefalkus/powershell-intune-samples
These scripts were created by and cloned from Matthew Pottinger's Github. Thanks Mat for all your help! https://github.com/matthewpottinger/BYOD-UK-Blueprint-AutoScripts

Script information
The following provides details on what each script does

BYOD-MEA-MasterScript.ps1
Triggers the running of all other scripts

AADGroups-Create.ps1
Creates the following Groups:

BYOD-Good-Mobile Device-Users-Enabled
BYOD-Good-PC-Users-Enabled
BYOD-Good-Exclude Mobile Device-Users
BYOD-Good-Exclude PC-Users
BYOD-Better-Mobile Device-Users-Enabled
BYOD-Better-PC-Users-Enabled
BYOD-Better-Exclude-Mobile Device-Users
BYOD-Better-Exclude PC-Users
BYOD-Best-Mobile Device-Users-Enabled
BYOD-Best-PC-Users-Enabled
BYOD-Best-Exclude Mobile Device-Users
BYOD-Best-Exclude PC-Users
AppRegistration-Create.ps1
Creates an AppRegistration called BYOD UK BP PowerShell Tool with the following permissions:

Group.Read.All (Groups)
Policy.Read.All (CA)
Application.Read.All (CA)
Policy.ReadWrite.ConditionalAccess (CA)
DeviceManagementApps.ReadWrite.All (MAM)
DeviceManagementServiceConfig.ReadWrite.All (DER)
to export/import all required Policies

CA-Policies-Import.ps1
Imports Conditional Access policies from the JSON\CA JSON folder into tenant with the correct permissions in Report Only Mode

MAM-Policies-Import.ps1
Imports App protection policies from the JSON\MAM Folder into tenant with the correct permissions

AC-Policies-Import.ps1
Imports App configuration Policies from the JSON\ACP Folder into tenant with the permissions

DER-Import.ps1
Imports Device Enrollement Restrictions into the tenant. Currently will be lowest priority after the Default policy

Implementation Guide
This script will implement all steps in the guidance. Except:
MCAS Policies
Locations and Location based policy
