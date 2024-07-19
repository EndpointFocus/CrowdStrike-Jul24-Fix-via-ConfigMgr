# CrowdStrike-Jul24-Fix-via-ConfigMgr

There is a workaround to bypass the BSOD error on Windows. We’re now finding that clients that stay online long enough will update this file to a new working version.
Workaround Steps:
1.	Boot Windows into Safe Mode or the Windows Recovery Environment
2.	Navigate to the C:\Windows\System32\drivers\CrowdStrike directory
3.	Locate the file matching “C-00000291*.sys”, and delete it.
4.	Boot the host normally
Tech alert article is here Tech Alert | Windows crashes related to Falcon Sensor | 2024-07-19 (crowdstrike.com)
https://supportportal.crowdstrike.com/s/article/Tech-Alert-Windows-crashes-related-to-Falcon-Sensor-2024-07-19


If you have a Configuration Manager environment, you can use this Task Sequence to automate the workaround.
Note: It won't work for:
* VMs hosted in Azure (no PXE)
* PCs that have bitlocker enabled or other drive encryption
