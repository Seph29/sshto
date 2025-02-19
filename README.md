# sshto

Small bash script that builds a menu (via dialog) from your ~/.ssh/config.</br>
![screeenshot](https://user-images.githubusercontent.com/18072680/60570513-69e99f00-9d7a-11e9-916d-48b74fa7585a.png)
</br>
Allows you to connect to your servers or run commands from menu. Available commands:</br>
![screeenshot](https://user-images.githubusercontent.com/18072680/93428736-a2ff2800-f8c8-11ea-9af4-d04a18022d8e.png)
</br>
Your commands can be easily added to this list. Just edit this part of the script:</br>
<pre>
cmdlist_renew () { cmdlist=(
    #Command#  #Description#
    "Username" "Change ssh username to $GUEST"
    ''         ''
    "ls  -la"  "List Files"
    "free -h"  "Show free memory"
    "df  -ih"  "Show free inodes"
    "df   -h"  "Show free disk space"
    "Custom"   "Run custom command on $target"
    ''         ''
    "Info"     "Full system info"
    "Sshkey"   "Add my ssh key to $target"
    "Alias"    "Add my usefull aliases to $target"
    "Copy"     "Copy selected file or dir to $target"
    ''         ''
    "Dest"     "Change destination folder $DEST on $target"
    "Upload"   "Upload   file or folder from $PWD to $target:$DEST"
    "Download" "Download file or folder from $target:$DEST to $PWD"
    ''         ''
    "Local"    "Change local  port $LOCAL"
    "Remote"   "Change remote port $REMOTE"
    "Tunnel"   "Start portunneling from $target port $REMOTE to local port $LOCAL"
    ''         ''
    "ShowConf" "Show ssh config for this host"
    "EditConf" "Edit ssh config for this host"
); }
</pre>
First collumn - command, second - description.</br>
Simple commands like 'ls -la' can be added as is.</br>
A list of commands or a complicated logic better add via function.</br>
Empty string is used as a delimiter.</br>
You can quick jump to the selected server via <i>CONNECT</i> button.</br>
When you done press ^D it'll bring you back to <i>sshto</i> commands section.</br>
</br>
Hosts description needs to be added like this:</br>
<pre>
Host server1 #DESCRIPTION
HostName 192.168.0.1
Port 22
User admin
</pre>
Start menu delimiters '---{ TEXT }---' can be added like this:</br>
<pre>
#Host DUMMY #TEXT#
</pre>
------
~/.ssh/config example:
<pre>
#Host DUMMY #Rybinsk#

Host rybserver1 #First server
HostName localhost

Host rybserver2 #Second server
HostName localhost

Host rybserver3 #Third server
HostName localhost

#Host DUMMY #Moscow#

Host moserver1 #First server
HostName localhost

Host moserver2 #Second server
HostName localhost

Host moserver3 #Third server
HostName localhost
</pre>
Script greps data from multiple config files via pattername <i>'config*'</i> in <i>~/.ssh</i> dir.<br>
So you can split config to multiple files and use them with <i>Include</i> directive, example:
<pre>
Include config_moscow
Include config_rybinsk
Include config*
</pre>

You can customize dialog colors by creating a config file:
<pre>
dialog --create-rc ~/.dialogrc
</pre>
# How to install
Clone\download this project, go to it's folder and run:
<pre>sudo cp sshto /usr/bin/

#and to unistall
sudo rm /usr/bin/sshto
</pre>

<a href="https://asciinema.org/a/PQMuRvfmxlHUc4oZMN76LY2V4">See how it works at asciinema</a></br>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=FhnsVH8t96Q
" target="_blank"><img src="http://img.youtube.com/vi/FhnsVH8t96Q/0.jpg" 
alt="ssh config guide" width="240" height="180" border="10"/></a></br>
Tom Lawrens video guide about ssh config and sshto

[![paypal](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://paypal.me/sshto?locale.x=en_US) Feel free to support the project!)</br>

BTC: 1LxRxsyXP389YW3Ezw9YzNetE5VYj1RaJf</br>
![btc](https://user-images.githubusercontent.com/18072680/106382955-f2f00e80-63d3-11eb-9316-b6653225820c.png)

BCH: qqnssal30x6acrga6zt4pd4q2s2t8um3cyqvd37qs7</br>
![bch](https://user-images.githubusercontent.com/18072680/108552897-fd326800-7302-11eb-8ae7-97eb0cc81d5e.png)

ETH: 0xd7e17A37DD936B211790ba70Aa985448277030E8</br>
![eth](https://user-images.githubusercontent.com/18072680/106382951-f2577800-63d3-11eb-8c01-f7ade514fb58.png)

XMR: 484z9YpiD4VBd4BfsaG7jKGYGuJ84tYJyCJBX4ZnAPqQXsUWgTY14TKRH3JLosFSAsKsv75nyt9yWPkFMUJhryxi7zccHNB</br>
![mon](https://user-images.githubusercontent.com/18072680/106383275-15832700-63d6-11eb-87d5-8b9f4ba08c40.png)

LTC: LRVPYR7dvRVdNET23gg3fvTwDM9hotQkZw</br>
![ltc](https://user-images.githubusercontent.com/18072680/106383361-7a3e8180-63d6-11eb-9239-48b6d80c3c4b.png)

DASH: Xtz7P6GasicE9yS8zXkH3PH2qAF2qWJADG</br>
![dash](https://user-images.githubusercontent.com/18072680/108553387-a11c1380-7303-11eb-9560-81f0deec2fbc.png)

ZEC: t1ZDgHci8yDVkoGvUFG7QtxUNRuzsF1Qtse</br>
![zec](https://user-images.githubusercontent.com/18072680/108553595-f7895200-7303-11eb-9ca8-17d1c81df7eb.png)

MKR: 0xd7e17A37DD936B211790ba70Aa985448277030E8</br>
![mkr](https://user-images.githubusercontent.com/18072680/108553822-4505bf00-7304-11eb-9db9-0833141e36c9.png)
