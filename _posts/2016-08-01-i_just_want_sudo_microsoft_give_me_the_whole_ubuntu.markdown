---
  
layout: post  
title:  "I just want sudo, Microsoft give me the whole Ubuntu"  
date:   2016-07-31 17:25:00  
categories: bash ubuntu windows  
language: en

---  

My laptop just got updates last night. It seems I got Windows 10 Anniversary Update earlier. One feature that I've been waiting is Windows Subsystem for Linux (WSL), or more known as Bash on Windows on Ubuntu. So why not give it a try?

## Enabling Windows Subsystem for Linux
My Windows build version after update is **14393**. To enable *bash* feature, go to **Programs and Features** in Control Panel, click **Turn Windows features on or off** in left sidebar. Tick **Windows Subsystem for Linux (Beta)** checkbox and click **OK**

![Turn On WSL Feature][wsl-1]

Restart computer and run *bash* from Start Menu by clicking **Bash on Ubuntu on Windows**. You can also run via **Run (Win+R)** and write `bash`. Type `y` to continue. Windows will download required files to install *Ubuntu on Windows*.

![Start Bash][wsl-2]

## First Impression
It is awesome to have UNIX command lines such as *grep*, installing tools as easy as *apt-get* and gain privileges as simple as *sudo*. I really hate UAC prompt to pop up and open new terminal everytime I want to gain privileges from command line. *Windows Command Line* lack of these features and somehow I just don't like *PowerShell*.
 
*bash* Home folder is separated with Windows Home folder. To access from *Windows Explorer*, go to `C:\Users\%YOUR_USERNAME%\AppData\Local\lxss`.  *bash* cannot execute Windows binaries so I have to install *git* and other tools via *apt-get* and sources. *ruby* packages is outdated too, so I install it from [Brightbox repository][brightbox-repo].

## My Verdict
I'm more graphical UI guy, but lately I found it's more productive to use command line. I use *Git for Windows* or *git-bash* as my default terminal. It's awesome because I got UNIX command lines as well as able to execute Windows binaries. 

Comparing *git-bash* to *Bash on Windows*, I don't think it will replace my default terminal anytime soon. Developer tools that I mostly used like *node*, *go*, and *docker* is available natively for Windows. Even though some features would be missed, it's still enough for most developers and students. Besides, there won't be any features to [run Windows exectable][wsl-issue-1] very soon. 

For Ruby developers, Jekyll bloggers and others who relies on open-source tools which not available natively on Windows, *Bash on Windows* will be very helpful when setting up development environment. I don't have to run VirtualBox VM again just to modify my Jekyll blog.

*Bash on Windows* is still in Beta. I'm sure it will be getting richer features and getting better in the future. If you found problems, you could find solutions or ask a question in [here][bash-win-issues] 

## Alternative
If you want to accomplish Ubuntu terminal features in Windows, I recommend you to use [Git for Windows][git-win], [ConEmu][conemu] for console emulator and [Chocolatey][chocolatey] for *apt-get* alternative.

![ConEmu][conemu-image]

If you don't want hassle, there is [Cmder][cmder], a fully-packaged console emulator based on *ConEmu*, *clink*, and *Git for Windows*

![Cmder][cmder-image]

In the end, I realized that I just want **sudo** in Command Prompt.

[wsl-1]: https://raw.githubusercontent.com/saggafarsyad/saggafarsyad.github.io/master/images/wsl-1.png
[wsl-2]: https://raw.githubusercontent.com/saggafarsyad/saggafarsyad.github.io/master/images/wsl-2.png
[brightbox-repo]: https://www.brightbox.com/docs/ruby/ubuntu/
[wsl-issue-1]: https://github.com/Microsoft/BashOnWindows/issues/333
[git-win]: https://git-scm.com/download/win
[conemu]: https://conemu.github.io/
[conemu-image]: https://conemu.github.io/img/ConEmu-Maximus5.png
[chocolatey]: https://chocolatey.org/
[cmder]: http://cmder.net/
[cmder-image]: https://raw.githubusercontent.com/saggafarsyad/saggafarsyad.github.io/master/images/cmder.jpg
[bash-win-issues]: https://github.com/Microsoft/BashOnWindows