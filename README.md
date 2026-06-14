# aur-package-checker-installer

A simple script to check AUR packages (and dependecies) for malicious code patterns and against the (growing) compromised list of AUR packages.

I primarily wrote this script for myself as I am an active Thinkpad addict that has installed Arch on a majority of them and wanted to be able to verify none of the compromised packages were installed.

I then thought that I wanted to do this everytime I installed a new AUR packe, besides reading the PKGBUILD file myself. I also thought it would be worthwhile to not only check the dependencies against the compromised package list, but also to peek into each PKGBUILD file with the most basic of heuristics to try and indentify and malicious looking patterns. I then decided to top it off witrh a simple log as well as generating a list of any possible compromised packages (based oin heuristics). I am in no way trying to create yet another AUR installed, so this is not at all full featuerd, I am only sharing this as a stop gap unttil a more solid and viable solution can be made by Arch to limit or outright prevent AUR packages being published by bad actors or vibe-coders.

If enough people use this and are interested, I will add the ability to upload possible compromissed pacakges through the interface and run more stringent and through testing of all of the code attached to each package, while maintaining and update the list of compromised package, including a way for packages that have been patrches/update/replaced to be removed from this living list.

Disclaimer: Local Ollama instace with qwen2.5 and the Cline VSCode extension was used for syntax , formatting, and pattern matching

### Install:

Clone or download [aur-package-check-installer.sh](http://aur-package-check-installer.sh)

### Usage:

(chmod +x to script)

./[aur-fetch-installer.sh](http://aur-fetch-installer.sh)  [aur-package-name2] ...   (Check and install packages)

./[aur-fetch-installer.sh](http://aur-fetch-installer.sh) --view-logs | -v                              (View color-coded history log)

### Environment Variables:

MALWARE_LIST_URL  Override the source malware list feed URL.

Current Active URL: [https://md.archlinux.org/s/SxbqukK6IA/download](https://md.archlinux.org/s/SxbqukK6IA/download)

Status: Using default Arch Linux source.

### Available Flags and Options:

-c, --check-all                Download and run deep heuristic checks on packages being installed and their AUR dependencies.

-l, --check-local                Scan your currently installed system packages against the malware list without installing anything.

-v, --view-logs                  View the color-coded history log of script activities.

-h, --help                       Show this complete help and usage message.  

Running the script with the -l flag will not install any packages, it will check currently installed AUR packages against the current copy of the list.
