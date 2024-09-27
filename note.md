## R6687BB53-kitsune (27001)

- Minor zygisk changes

If you want to read changelog of previous builds, please visit [Release page](https://github.com/HuskyDG/magisk-files/releases)

### Diffs to official Magisk

- [App] Added a new feature to install Magisk into `/system` partition for emulators that do not have a boot image.
- [Zygisk] Changed the method of loading Zygisk to ptrace init implementation (required Android 8+). The implementation comes from [ZygiskNext](https://github.com/Dr-TSNG/ZygiskNext). This method does not need to change any property and is more compatible with some emulators that ignore `ro.dalvik.vm.native.bridge` property.
- [General] Support for mounting in pre-init for modules.
- [General] Support deleting file by using indicated whiteout character device, similar to `overlayfs`
- [Zygisk] Added support for GrepheneOS Android 14, a privacy and security focused mobile OS with Android app compatibility. This is because the official Magisk does not support it.
- [General] Restored support for devices with no selinux support, which was removed by the official Magisk. This allows users to use Magisk on devices that do not have selinux enabled in kernel.
- [General] Update resetprop to avoid increasing serial counter for read-only properties
- [Module] Mounting module files to system no longer need mirrors
- [App] Add biometric authentication back
- [General] Check full path of `init.rc`
- [General] Grant root to shell by default (for debug build)
- [General] Disable magisk app signature verification
- [Module] Support Magic mount for more partitions

### Magisk upstream level

- HEAD commit: 154121f

## Magisk (3d91a561) (27001)

- Minor bug fixes

## Diffs to v26.4

- [Zygisk] Introduce new code injection mechanism
- [Zygisk] Support new signature introduced in U QPR2
- [SEPolicy] Update libsepol to properly set some policy config bits
- [MagiskBoot] Support compressing `init` so Magisk is installable on devices with small boot partitions
- [ResetProp] Add new wait for property feature `resetprop -w`