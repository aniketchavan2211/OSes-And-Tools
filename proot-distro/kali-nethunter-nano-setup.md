# Setting up Kali Linux NetHunter Nano in Termux PRoot-distro PKG

Basic Preparation:

update and upgrade Termux Environment.

```bash
apt -y update && apt -y upgrade
```

Install require packages.

```bash
apt install -y proot proot-distro
```

Next to Main Step

**Copy / Paste** or **Download** `kali.sh` in your local
termux environment.

You can also download directly to `$PREFIX/etc/proot-distro/kali.sh`
Path of proot-distro, Where every distro script lives.


And you are done.

you can run proot-distro as normal usage.

```bash
proot-distro add kali # add / i / in / ins / install
proot-distro sh kali # sh / login ( optional flag ) --isolated
```

On login wait for few seconds.

On login normal things to avoid Dev Message.

```bash
touch ~/.hushlogin
```
