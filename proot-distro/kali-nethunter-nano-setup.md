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

***`kali.sh`***
```bash
# Custom Kali NetHunter Nano aarch64
DISTRO_NAME="kali"
DISTRO_COMMENT="Kali Nethunter Nano ( aarch64 )"

TARBALL_URL['aarch64']="https://kali.download/nethunter-images/current/rootfs/kali-nethunter-rootfs-nano-arm64.tar.xz"              TARBALL_SHA256['aarch64']="73134c64ca91a562fd2dc4be428633001c92d8d48be59ef4cbfaa73d358986a1"
```

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
