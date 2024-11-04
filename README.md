# Install-Git.ps1
A PowerShell script to install the latest 64-bit Git for Windows with installer-selected defaults and minimal user interaction, created because school-managed computers are reset on reboot and do not come preinstalled with Git.

Also found here: https://github.com/ravesec/eku-ccdc/blob/main/scripts/windows/Install-Git.ps1

Comes will option to configure global user.name and user.email.

Multiple installations of git may conflict, not every edge case has been tried.

***RUN AT OWN RISK***

## Installation Quirks
- Git will install system-wide if:
  - You are in a PowerShell instance that is running as Administrator
  - You are running as a non-Administator but allow the installer access to the system via UAC
- Git will install only for the current user if:
  - You cannot (due to permissions) allow the installer access to the system via UAC
  - You run this script with the `-UserInstall` parameter (it will still prompt for UAC if you have permission to elevate, select Yes)
- Git will cancel the installation if:
  - You have permission to allow the installer access to the system via UAC yet choose not to

## How to Run
- System-wide installation:
  - `iex "(& {$(irm https://raw.githubusercontent.com/lj-sec/Install-Git/Install-Git.ps1)})"`
- Forced user installation:
  - `iex "(& {$(irm https://raw.githubusercontent.com/lj-sec/Install-Git/Install-Git.ps1)} arg -UserInstall)"`
