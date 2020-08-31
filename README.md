# Gentoo Kernel .config and make.conf compilation USE flags for [TUXEDO InfinityBook Pro 15 v5](https://www.tuxedocomputers.com/de/Linux-Hardware/Linux-Notebooks/15-16-Zoll/TUXEDO-InfinityBook-Pro-15-v5-SILVER-Edition.tuxedo) 

------------

See here: 

## make.conf USE flags

### Processor

Intel Core i7-10510U 10th generation Comet Lake

**app-portage/cpuid2cpuflags**

Tool I used to find out which USE flag should be defined under "CPU_FLAGS_X86".

<code>CPU_FLAGS_X86="aes avx avx2 f16c fma3 mmx mmxext pclmul popcnt sse sse2 sse3 sse4_1 sse4_2 ssse3"</code> \

**This enables auto-detection of the CPU's architecture.** \
<code>COMMON_FLAGS="-O2 -pipe -march=native"</code>

### Graphic card: Intel UHD 620
According to the [Gentoo Intel wiki page (8 through Gen 9+)](https://wiki.gentoo.org/wiki/Intel#USE_flags).
Still, no entry specifying 10th generation Intel Core Comet Lake, hopefully out soon.

<code>VIDEO_CARDS="intel i965 iris"</code> 

------------

## Firmware:

**sys-kernel/linux-firmware \

Added **this lines** to have the firwmare loaded by the kernel on bootup:

```markdown
Device Drivers  --->
    Generic Driver Options  --->
        Firmware loader  --->
          -*- Firmware loading facility
                (**i915/kbl_dmc_ver1_04.bin**) Build named firmware blobs into the kernel binary
                      (**/lib/firmware**) Firmware blobs root director </code>
```
## Tuxedo Keyboard backlight Kernel modules:

Lets you control the Keyboard backlight by pressing FN + Keys from the numberpad.

**sys-power/tuxedo-cc-wmi** \
-> Git-Repo link: https://github.com/tuxedocomputers/tuxedo-keyboard
\
\
**app-laptop/tuxedo-keyboard** \
-> Git-Repo Link: https://github.com/tuxedocomputers/tuxedo-cc-wmi


#### Debugging to do list:
- [ ] Get video signal through HDMI port on external monitor -> see this [vivid exchange with Gentoo legend NeddySeagoon](https://forums.gentoo.org/viewtopic-t-1118210.html)
