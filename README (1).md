---
cover: >-
  https://opensource.com/sites/default/files/lead-images/tux_linux_penguin_code_binary.jpg
coverY: 32.67221801665406
---

# Basic Linux

{% hint style="info" %}
Some common Linux commands that are useful during CTF
{% endhint %}

#### Navigating

`cd` - change directory

`cd ~` - Change directory to your home directory

`cd -` - Go back to previous directory

#### Looking at files <a href="#looking-at-files" id="looking-at-files"></a>

`ls` - List files in directory

`ls -al` - List files with hidden files

`file` `<filename>` - Show and detect type of files

`cat` - Read the contents of a file and print them into the terminal,

#### Others

`grep` - filter content

`base64 -d <filename>` - Decode base64 text

#### Installation

`apt-get update` - Sync with Repositories.&#x20;

`apt-get upgrade` - Upgrade installed packages.&#x20;

`apt-get dist-upgrade` - Upgrade distribution packages.&#x20;

`apt-get install "Package Name"` - Install the package.&#x20;

`apt-get remove "Package Name"` - Uninstall the package.

#### Keyboard Shortcuts

`Ctrl + r` : search for old commands that you have used

`Ctrl + a` : Move to the start of line.

`Ctrl + e` : Move to the end of line.&#x20;

`Ctrl + w` : Cut from cursor to previous white space.&#x20;

`Ctrl + k` : Cut from cursor to the end of line.&#x20;

`Ctrl + y` : Paste the last cut text.

#### References

{% embed url="https://linuxjourney.com/" %}

{% embed url="https://bitvijays.github.io/LFF-ESS-P0B-LinuxEssentials.html" %}
