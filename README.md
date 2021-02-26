# Source code for Voyance Updater

:: Create MTU Path

Powershell New-Item -Path 'C:\MTU' -ItemType Directory

:: Downloads the Dealer.pkg branding package into the MTU directory

Powershell Invoke-WebRequest https://www.dropbox.com/s/5bqldroc4x86ree/Dealer.pkg?dl=1 -OutFile C:\MTU\Dealer.pkg 

:: Downloads Voyance into the MTU Directory

Powershell Invoke-WebRequest http://medicatechusa.com/wp-content/uploads/voyance/Voyance_v1.3.1612.2946_cfc4ebb3_Setup.exe -OutFile C:\MTU\Voyance_v1.3.1612.2946_cfc4ebb3_Setup.exe

:: Installs Voyance passing the silent argument parameter

start /wait C:\MTU\Voyance_v1.3.1612.2946_cfc4ebb3_Setup.exe /SILENT /VERYSILENT

:: Deletes the wifi image

del "C:\Program Files\Voyance\Resources\Images\wi-fi-disc.png" /s /f /q
