# My OpenEmbedded/Yocto build configurations

An alternative approach to setting up the Yocto Project layers using git submodules instead of the `bitbake-setup` tool for build configurations that are useful to me.

- Poky master

## Why?

So far, I simply have not found a workflow based on `bitbake-setup` that allows me to use git and VSCode effectively.
I follow the KISS principle: git and git submodules, and I'm not a fan of wrapper tools in general.

## Quick Start

1. **Clone the repository with submodules**:

   ```bash
   git clone --recursive <repository-url>
   cd poky-master-sm
   ```

   If you already cloned without `--recursive`, initialize submodules:

   ```bash
   git submodule update --init --recursive
   ```

2. **Initialize the build environment**:

   ```bash
   source oe-init-build-env build/poky-master
   ```

   This will initialize a build environment for the poky-master reference distro.
   Choosing a different distro is as simple as using another directory in the build folder.

3. **Build an image**:

   ```bash
   bitbake core-image-minimal
   ```

   This builds a minimal console-based image.

## Updating Submodules

To update all components to their latest versions:

```bash
git submodule update --remote
```

Or update specific components:

```bash
git submodule update --remote layers/bitbake
git submodule update --remote layers/openembedded-core
git submodule update --remote layers/meta-yocto
```

For comprehensive documentation, visit:
[Yocto Project Documentation](https://docs.yoctoproject.org/)
Most sections except the quick start should still be applicable.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
