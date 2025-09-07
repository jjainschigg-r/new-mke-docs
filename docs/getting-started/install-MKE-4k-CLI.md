# Install the MKE 4k CLI

Before you can proceed with the MKE 4k installation, you must download and
install `mkectl`. You can do this automatically using an `install.sh` script,
or you can do it manually.

## Install automatically with a script

1. Install `mkectl` by downloading and executing the following shell script:

   ```bash
sudo /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/MirantisContainers/mke-release/refs/heads/main/install.sh)"
   ```
   If you want to override default dependency versions, pass the
   `MKECTL_VERSION` as required. For example:

   ```bash
sudo MKECTL_VERSION=v4.1.0 /bin/sh -c "$(curl -fsSL https://raw.githubusercontent.com/MirantisContainers/mke-release/refs/heads/main/install.sh)"
   ```
   If you prefer to run the script in the debug mode for more detailed output and logging,
   set `DEBUG=true`:

   ```bash
sudo DEBUG=true /bin/sh -c "$(curl -fsSL https://raw.githubusercontent.com/MirantisContainers/mke-release/refs/heads/main/install.sh)"
   ```
2. Confirm the installation:

   ```bash
mkectl version
   ```
   Expected output:

   ```bash
Version: v4.1.0
   ```
   

!!! info
    By default, the script installs mkectl v4.1.0.

The `install.sh` script detects the operating system and the
underlying architecture, based on which it will install the `mkectl` binary in `/usr/local/bin`. Thus, you must ensure that
`/usr/local/bin` is in your `PATH` environment variable.

You can now proceed with MKE 4k cluster creation.

## Install using Homebrew

1. Add the `mirantis` repository to your local taps:

   ```bash
brew tap mirantis/tap
   ```
!!! info
    If the `mirantis` tap is already present and you want to update it, run:

       ```bash
brew update
       ```
2. Install `mkectl`:

   - To install the latest `mkectl` version:

     ```bash
brew install mkectl
     ```
   - To install a specific `mkectl` version:

     ```bash
brew install mkectl@<version-number>
     ```
## Install manually

1. Download the `mkectl` binary from the S3 bucket:

   | Distribution | Architecture | Download                                                                                                          |
   | ------------ | ------------ | ----------------------------------------------------------------------------------------------------------------- |
   | Linux        | x86_64       | [download](https://github.com/mirantiscontainers/mke-release/releases/latest/download/mkectl_linux_x86_64.tar.gz) |
   | MacOS        | x86_64       | [download](https://github.com/mirantiscontainers/mke-release/releases/latest/download/mkectl_darwin_arm64.tar.gz) |

2. Ensure that the `mkectl` binary is executable:

   ```bash
chmod +x mkectl
   ```
3. Copy the `mkectl` binary to `/usr/local/bin/`:

   ```bash
mv mkectl /usr/local/bin/
   ```