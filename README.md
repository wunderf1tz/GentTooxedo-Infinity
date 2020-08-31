# Gentoo Kernel .config of [TUXEDO InfinityBook Pro 15 v5](https://www.tuxedocomputers.com/de/Linux-Hardware/Linux-Notebooks/15-16-Zoll/TUXEDO-InfinityBook-Pro-15-v5-SILVER-Edition.tuxedo) 

See here: 

### Firmware:

Added this line to have the firwmare loaded by the kernel on bootup:

```markdown
Device Drivers  --->
    Generic Driver Options  --->
        Firmware loader  --->
          -*- Firmware loading facility
                (i915/kbl_dmc_ver1_04.bin) Build named firmware blobs into the kernel binary
                      (/lib/firmware) Firmware blobs root director </code>
```

### Tuxedo Keyboard backlight Kernel modules:

Lets you control the Keyboard backlight by pressing FN + Keys from the numberpad

sys-power/tuxedo-cc-wmi
-> Git-Repo link: https://github.com/tuxedocomputers/tuxedo-keyboard

app-laptop/tuxedo-keyboard
-> Git-Repo Link: https://github.com/tuxedocomputers/tuxedo-cc-wmi
