# Parrot WSL Builder
This repo contains the WSL building code.

The WSL image is based on the parrotsec/core docker image.
## Project Layout

### Launcher

Launcher contains the VSCode project needed to build launcher.exe, however aslong as we update the install.tar.gz included with the launcher updates can be provided to the base install image(or via apt upgrade with existing installs)

This should only need modification should the install process need changed/updates.

Based from [https://github.com/Microsoft/WSL-DistroLauncher](https://github.com/Microsoft/WSL-DistroLauncher)

## Base_Builder

This contains the code to:
1. Download the parrotsec/core docker image
2. Add needed packages for WSL support(locales, sudo)
3. Extract this into the install.tar.gz used

This process has been automated via gitlab CI, and the artifacts can be downloaded for the latest run [here](https://gitlab.com/parrotsec/project/wsl/-/artifacts)

## Running
You can run the WSL distro by downloading the latest release from the parrotsec website, or from the build arifacts then:

1. Extract the .zip file
2. Run Launcher.exe
3. Follow the installation prompts to create a user account and choose to download the full tools.

Note: Nested Virtualization is not supported(i.e. running WSL in a VM), however it _should_ work.


# Credits

Written and maintained by @0xEmma

With bug testing help from @Beerrise
