# JellyFin-For-Xbmc4Xbox
JellyFin-For-Xbmc4Xbox.
1. How to Install the App on the Xbox

You’ll Need:
A softmodded or hardmodded original Xbox
XBMC4Xbox 3.6 installed
FTP access to the Xbox (via FileZilla or similar)
 Step-by-Step Install:
Unzip plugin.video.jellyfin.zip
→ It gives you a folder:
plugin.video.jellyfin
Upload to Xbox via FTP
Use FileZilla
Connect to your Xbox (usually ftp://192.168.0.x, user: xbox, pass: xbox)
Navigate to:
Q:\plugins\video\
Drop the entire folder:
plugin.video.jellyfin
Restart XBMC4Xbox
Open:
Videos → Video Add-ons → JellyFin for Xbox
 2. How to Get Your Jellyfin Server Details

 IP Address of the Jellyfin Server
On the computer running Jellyfin, open a web browser and visit:
http://localhost:8096
Now, from another device on your network (like your Xbox), use the machine’s local IP:
http://192.168.1.45:8096
(Adjust IP to your network; check in System Preferences → Network or run ipconfig / ifconfig)
 3. How to Get API Key and User ID

 API Key
Go to your Jellyfin web dashboard:
http://<your-ip>:8096/web
Sign in as admin
Click:
Admin Dashboard → API Keys
Click + Add API Key
Call it something like xbmc and copy the key.
Example:
462bcc0cdbc2406aabfd90537970ef06
 User ID
Option 1: Use the Users API
Go to:

http://<your-ip>:8096/Users?api_key=YOUR_API_KEY
It returns:

[
  {
    "Name": "timeout",
    "Id": "4ac5e4a927a74d7b99a253567d9f1ade",
    ...
  }
]
Option 2: View in browser tools

Open the Jellyfin dashboard as your user
Open Developer Tools > Network tab
Reload and look for requests like /Users/<ID>/Items — that’s your user ID
 4. Edit the Plugin to Use Your Server

Open this file on your PC:

plugin.video.jellyfin/default.py
Find and change:

base_url = "http://192.168.1.45:8096"
api_key = "462bcc0cdbc2406aabfd90537970ef05"
user_id = "4ac5e4a927a74d7b99a253567d9f1ade"
Replace with your:

IP address
API key
User ID
Save it, then FTP it back to the Xbox.

 You’re Done!
