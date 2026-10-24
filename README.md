# IcarOS manifest

[repo](https://gerrit.googlesource.com/git-repo) manifest for the IcarOS NAS
distro (Yocto 6.0 Wrynose, Seagate GoFlex Net / Marvell Kirkwood).

## Clone

    mkdir icaros && cd icaros
    repo init -u https://github.com/ska/icaros-manifest.git -b wrynose
    repo sync

## Build

    . ./setup-environment        # creates and enters ./build
    bitbake nas-image-minimal

Set `ICAROS_ADMIN_HASH` in `build/conf/local.conf` before building a real
image (see `meta-icaros/classes/nasusers.bbclass`).

## Layout

    sources/bitbake              2.18
    sources/openembedded-core    wrynose
    sources/meta-openembedded    wrynose
    sources/meta-yocto           wrynose
    sources/meta-kirkwood        wrynose (BSP: kernel, machine)
    sources/meta-icaros          wrynose (distro, image, recipes)
