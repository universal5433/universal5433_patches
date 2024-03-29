#  universal5433_Patches
 * Bunch of important patches
 
# Patching
- Apply using `git am *.patch` or repopick if on lineage gerrit

## system/core
* Handle empty thread names : [Source](https://review.lineageos.org/c/LineageOS/android_system_core/+/256219)
* Needed to fix `Abort message: 'thread name not provided to Thread::run'`

## packages/modules/NetworkStack
* Opt-out for TCP info parsing on legacy Kernels [Source](https://github.com/ArrowOS/android_packages_modules_NetworkStack/commit/19bbd6fb49222c3849e8f9f8f5f2c56c61bdfc81)
* Needed to fix `TcpSocketTracker AAAAAAAAA*` Spam and `TcpSocketTracker: java.lang.IllegalArgumentException: Bad position 65648/3648`

## frameworks/native
* disable touch input while using a stylus : [Source](https://review.lineageos.org/c/LineageOS/android_frameworks_native/+/319404)
* Enable back PalmRejection When using Stylus/S-PEN

## frameworks/base
* Add support for app signature spoofing : [Source](https://github.com/ProtonAOSP/android_frameworks_base)
* Needed for MicroG Support `Optional patch`

## frameworks/base
* Add AttestationHooks : [Source](https://github.com/hentaiOS/platform_frameworks_base)
* SafetyNet/CTS Fix `Optional patch`

## Repopick
`repopick 256219 -P system/core -f` # Handle Empty Thread Name

`repopick 319404 -f` # disable touch input while using a stylus

`repopick --topic 18-snet -f` # SafetyNet/CTS AttestationHooks

`repopick 301619 -f` # EffectsFactory: add debug and trace wrappers for NXP LifeVibes