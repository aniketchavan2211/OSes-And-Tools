Alpine is Best OS for container environments and docker images, mostly used in DevOps & DevSecOps Domain.

## Features
- Lightweight

Alpine is highly lightweight linux, used mostly in deployment environment by Maintainers, by DevOps Engineers, and others.

Alpine is built for:
- containers
- servers
- security-sensitive environments
- people who want to understand their system

Not for:
- desktop hand-holding
- magical automation
- legacy behavior preservation

## Installation on Virtual Box

Host Machine / OS : kali
Guest OS : alpine

Official Home Page of Alpine Linux : [Alpine Linux](https://www.alpinelinux.org/)

Download Official ISO image from [Downloads](https://www.alpinelinux.org/downloads)

Also download [Virtualbox Home Page](https://www.virtualbox.org/) if not. Install [VirtualBox](https://www.virtualbox.org/ wiki/Downloads) and Virtual Box Extensions.

We are using alpine standard edition iso file. for x86_64 architecture.

### Virtual Box Settings

Click on `New` (`CTRL + N`) creates new virtual machine.

#### New Virtual Machine

**Name anything you want :**
> Example: **Alpine Standard**

**Select `ISO Image` from `Downloads` directory  :**
> Example: **/home/aniket/Downloads/alpine-standard-3.23.3-x86_64.iso**

**OS :**
> Linux

**OS Distribution :**
> Other Linux

**OS Version :**
> Other Linux (64-bit)

#### Specify virtual hardware

**Base Memory :**
> 4096 MB around 4 GB

**Number of CPUs :**
>  2

##### Create a New Virtual Hard Disk

**Disk Size :**
> 8 GB

**Hard Disk File Type and Format :**
> VDI ( Virtual Disk Image ) 

- [ ] Uncheck Pre-allocate Full Size ( ***This will save space*** )

#### Virtual Machine Settings

Now that virtual machine is setup, still need some twerking.

Open **Virtual Machine Settings**.

Switch to `Expert` tab.

Check all every settings are set or not, if not set set them.

Expand *System* -> *Motherboard tab*,

set `Hard Disk` on top, disable `Floppy`.

Switch to **Processor**,

- [x] checked Nested VT-x/AMD-V

Go on **Display** -> **Screen** tab.

- Video Memory : `128 MB` MAX

Cross Check **Network**, open **Adapter1** Tab.

Enable Network Adapter, 
- Attached to `NAT` OR `Bridged Adapter`

`NAT` is more secure because network only exists inside virtualbox.

Start **Alpine Virtual Machine  Start with GUI / Normal start**.

On booting ISO image will boot, and ask for root passwd,

Default Password:
root password : `root`

Check network connection & DHCP client & DNS server is configure or not.
```bash
ip link
```


if interface is down, make it active or up
```bash
ip link set eth0 up
```

After get a IP Address from DHCP, 
```bash
udhcpc -i eth0
```

Check DNS is working:
```bash
ping -c 5 8.8.8.8
ping -c 5 google.com
```

we here checking 8.8.8.8 Google DNS service and checking connection to Google service (ping to Google server).

If works, Good still add Google DNS Servers in `/etc/resolv.conf`:
```bash
echo "nameserver 8.8.8.8" >> /etc/resolv.conf
echo "nameserver 8.8.4.4" >> /etc.resolv.conf
echo "nameserver 1.1.1.1" >> /etc/resolv.conf
```

If need an Text Editor `vi` is pre-installed by default, nano, vim, neovim is not installed

Now that, Network is configured, 
Move to Alpine OS Installation on Virtual Hard Disk.

```bash
setup-alpine
```

Keyboard: `in`, Again Set Keyboard: `in-eng`

Set hostname : `alpine`

Set `interface` settings:

- Interface: `eth0`
    
- IP address: `dhcp`
    
- Manual network config? → **no**

Set Root password to any thing Just Remember or write & keep in secure location.

Set Timezone : `Asia/Kolkata`

Skip Proxy settings for now.

Set `busybox` for **NTP ( Network Time Protocol )**

**APK Mirror Repositories**
Hit `f` for fast apk mirrors repos

It will take some time.

Set Normal Non Root `User Name` & `Password`.

set others to defaults.

On ***Disk & Install***

Select disk : `sda`

Use as : `sys`

Data be Erased : `y`

After installation succeeded, Reboot system
```bash
reboot
```

It will automatically boot from virtual hard disk

and Don't forget to remove iso image attach as CD/DVD booting drive.

Login as Normal or Root User.

Alpine uses **APK Package Manager**  for adding, managing, deleting & others do with packages, same as `apt` & `dpkg` in `debian` & `kali` uses package management. 

For help:
```bash
apk
apk -h
apk --help
```

all commands brings help menu.

- To update & upgrade on Alpine Linux

Change user to root user by `su` command, enter passwd for super user, and execute this command:
```bash
apk update && apk upgrade
```

Notice `$` ( dollar sign ) change to `#` ( hash sign ), signify shell switch to root shell.
Risky command might get you losing of data.

Now, that we update and upgrade `apk package manager`.

Let's try to install some package:

```bash
apk add curl
apk add bash zsh nano vim nvim git tor wget
apk add cargo # rust lang
```


To search for specific package:

```bash
# apk search packge-name
apk search nano
```

To check specific package details:
```bash
apk info nano
```

To remove / delete / uninstall package:
```bash
apk del nano
```

This will uninstall / remove nano package if installed.

>[!WARNING]
>Install wget pkg before runnning this command some mirrors need wget package.


Setup apk repos if needed:
```bash
setup-apkrepos
```

if need to add, remove apk repos from mirror lists modify `/etc/apk/repositories`
```bash
nano /etc/apk/repositories
```

Also enable ***Community Repos Mirrors lists***.

## 1️⃣ OpenRC instead of systemd

### What OpenRC is

OpenRC is an **init system** (PID 1 controller), but it is:

- shell-script based
    
- dependency-driven
    
- **not** a service manager + logger + IPC bus + everything else
    

OpenRC does _one job_: start and stop services in order.

### Why Alpine chose it

*systemd*:

- tightly coupled
    
- binary-heavy
    
- complex state machine
    
- assumes full OS boot with privileges
    

*OpenRC*:

- transparent
    
- readable
    
- works in containers, chroots, proot
    
- trivial to debug (`cat /etc/init.d/service`)
    

In Alpine:

```bash
rc-service networking restart 
rc-update add sshd default
```
No D-Bus dependency chain. No hidden activation.

## 2️⃣ musl libc instead of glibc

This is one of Alpine’s most controversial choices.

### What musl is

musl is the **C standard library** (the thing _everything_ links against).

glibc:

- huge
    
- feature-rich
    
- backwards-compatible forever
    
- optimized for enterprise desktops/servers
    

musl:

- small
    
- standards-focused
    
- consistent behavior
    
- predictable memory usage
    

### Why this matters

musl advantages:

- tiny binaries
    
- faster cold starts (containers!)
    
- simpler dynamic linker
    
- fewer weird edge cases
    
- better static linking
    

musl trade-offs:

- some precompiled binaries won’t run
    
- glibc-specific assumptions break
    
- some language runtimes need patches
    

This is why:

- “random binary from internet” sometimes fails on Alpine
    
- container images based on Alpine are _tiny_
    

Security angle 🔐:

- smaller libc = smaller attack surface
    
- less historical baggage

## 3️⃣ BusyBox instead of GNU coreutils

BusyBox is sometimes called:

> “The Swiss Army knife of embedded Linux”

### What BusyBox does

It provides **dozens of commands** in one binary:

- `ls`
    
- `cp`
    
- `ps`
    
- `clear`
    
- `mount`
    
- `ifconfig`
    

All via:

`/bin/busybox`

Everything else is symlinks.

### Why Alpine uses it

GNU coreutils:

- feature-rich
    
- heavy
    
- slower startup
    
- massive codebase
    

BusyBox:

- tiny
    
- fast
    
- enough for 90% of real work
    
- fewer flags, fewer surprises


Example difference:

```bash
ps aux   # works on Debian 
ps aux   # fails on Alpine 
ps       # works
```

This forces you to:

- learn POSIX behavior
    
- stop relying on GNU extensions

## Enable Color Shell Prompt

You will get color_prompt shell script in `/etc/profile.d` dir.

**To enable** :
```ash
mv /etc/profile.d/color_prompt.sh.disabled /etc/profile.d/color_prompt.sh
```

**To disable** :
```ash
mv /etc/profile.d/color_prompt.sh /etc/profile.d/color_prompt.sh.disabled
```

We are changing the `color_prompt.sh` shell script name by enabling it to work.