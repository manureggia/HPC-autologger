# HPC-autologger
a basic script for auto logging on ssh tunnel for Unimore's HPC Course

## Required Packages

To ensure that the script works properly, you need to install the following packages on your system:

1. **sshpass**: This tool allows non-interactive SSH login by passing the password directly through a command. It's required for the script to automate the SSH connections without requiring manual password entry.
   
   **Installation**:
   - On Debian/Ubuntu-based systems:  
     ```bash
     sudo apt-get install sshpass
     ```
   - On RedHat/CentOS-based systems:  
     ```bash
     sudo yum install sshpass
     ```
   - On macOS (using Homebrew):  
     ```bash
     brew install hudochenkov/sshpass/sshpass
     ```

2. **OpenSSH**: The `ssh` command, which is used to establish the tunnel and login, is part of the OpenSSH suite. This is generally installed by default on most Linux systems and macOS. However, if it's missing, you can install it using the following commands.

   **Installation**:
   - On Debian/Ubuntu-based systems:  
     ```bash
     sudo apt-get install openssh-client
     ```
   - On RedHat/CentOS-based systems:  
     ```bash
     sudo yum install openssh-clients
     ```
   - On macOS (using Homebrew):  
     ```bash
     brew install openssh
     ```

### Optional Tools

- **ps command**: This command is used to check the status of processes. It should be available by default on most Unix-like systems, including macOS. If not, install the `procps` package:

  **Installation**:
  - On Debian/Ubuntu-based systems:  
    ```bash
    sudo apt-get install procps
    ```
  - On RedHat/CentOS-based systems:  
    ```bash
    sudo yum install procps-ng
    ```
  - On macOS, `ps` is installed by default.

Make sure these packages are installed and accessible in your system's `PATH` to ensure the script works correctly.

## Installation

You can install this script using one of the following methods:

### Method 1: Place the Script in the `~/bin` Directory

1. Make the script executable:
   ```bash
   chmod +x hpc-tunnel
   ```
2. Move the script to the /usr/bin directory:
  ```bash
  mv hpc-tunnel /usr/bin/
  ```
### Method 2: Use a Custom Directory and Add It to Your `PATH`

1. Choose or create a custom directory where you want to store the script, for example, ~/my-scripts:
  ```bash
  mkdir -p ~/my-scripts
  ```
2. Make the script executable:
  ```bash
  chamod +x hpc-tunnel
  ```
3. Move the script to the chosen directory:
  ```bash
  mv hpc-tunnel ~/my-scripts
  ```
4. Add the custom directory to your PATH. Edit your shell configuration file (~/.bashrc, ~/.zshrc, etc.) and add the following line:
  ```bash
  echo 'export PATH=$PATH:~/my-scripts' >> ~/.bashrc
  ```
5. Reload your shell configuration to apply the changes:
  ```bash
  source ~/.bashrc
  ```

## Use

To start ssh tunnel 

```bash
hpc-tunnel start <OPTIONAL:PORT>
```
> if not specified it will connect to a pre-configured `PORT`

To close ssh tunnel

```bash
hpc-tunnel stop
```
To login into your Jetson nano use

```bash
hpc-tunnel login
```
