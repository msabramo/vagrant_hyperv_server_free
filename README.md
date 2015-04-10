A lightweight VM with Microsoft Hyper-V Server 2012 R2

https://vagrantcloud.com/msabramo/boxes/HyperVServer2012

# Prerequisites

- [Vagrant][]
- [VirtualBox][]

# Install and start up

The first time that you do this it will download a large Vagrant box
file (about 2.7 GB) from the Internet, so you may want to wait until you
have a good connection.

```bash
vagrant up
```

If this works, then (perhaps after a long time downloading), a new
VirtualBox window should appear and it will boot into a very
stripped-down Windows environment with 2 windows and no start menu, task
bar, system tray, etc.

![Screenshot](screenshot.png)


# Details

You now have a VirtualBox VM with:

- [Microsoft Hyper-V Server 2012 R2][Hyper-V Server] – free, stripped-down
  version of Windows; has very little GUI or admin/desktop tools, but it's good
  enough to run SQL Server Express and it can be managed remotely via PowerShell.
- [Chocolatey][] (a package manager for easily installing software in Windows)


# Tips

- If you want UNIX goodies, you can install [Cygwin][] with `choco
  install -y cyg-get` in a command prompt or PowerShell. This will
  create a basic Cygwin install in `C:\tools\cygwin`.

- If you accidentally close the command prompt window and need to open
  another, press Ctrl + Alt + Del and pick "Task Manager". Then in the
  `File` menu, choose "Run new task" and type `cmd` and hit Enter.

- You can [RDP][] to the host by doing `vagrant rdp`.

- `vagrant ssh` will not work out of the box, because the guest has no
  ssh server. If you are determined to use ssh, you can look into
  installing an ssh server like [winsshd][] (Bitvise SSH Server)],
  [freesshd][], the openssh package from Cygwin, etc. but you might be
  able to live without an ssh server, because you hopefully don't need to
  do much with the VM, or if you need to customize things, hopefully you
  can do it DevOps-style and do it by adding PowerShell commands to the
  `Vagrantfile` or use ansible (which can also send PowerShell commands
  over WinRM), etc.

- To see the list of services that are running, you can do `net start`
  from the command prompt or PowerShell.


[Vagrant]: https://www.vagrantup.com/
[VirtualBox]: https://www.virtualbox.org/
[Hyper-V Server]: https://technet.microsoft.com/en-us/library/hh833684.aspx
[Chocolatey]: https://chocolatey.org/
[Cygwin]: https://www.cygwin.com/
[RDP]: http://en.wikipedia.org/wiki/Remote_Desktop_Protocol
[winsshd]: https://www.bitvise.com/ssh-server
[freesshd]: http://www.freesshd.com/
