# Windows Environment Setup Guide

> ⚠️ **NOTE**
> You may use **any package manager** or install each tool manually from their official installation instructions.
> The steps below use [Chocolatey](https://chocolatey.org/) as an example and are **verified** to work with this project.
>
> ✅ The project has been tested and is known to work with:
> - **Java**: version `11.*`
> - **Python**: version `3.13.*+`
> - **Spark**: version `3.5.*+`
>
> ⚠️ We do **not guarantee** project stability with other versions of these applications.

⚠️⚠️⚠️  The software mentioned below is **approved by company policy**.
If you decide to use alternative tools (e.g., **Docker Desktop** instead of **Rancher Desktop**), we highly recommend reviewing the list of allowed software in the internal knowledge base: [Approved Freeware](https://kb.epam.com/display/public/EPMSAM/Approved+Freeware)

This guide will help you configure your Windows environment.

---

## Step 1: Install Chocolatey (Package Manager)

1. Open **PowerShell as Administrator**.
2. Run the following command:

   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
   ```

3. Close and reopen your PowerShell window to refresh the environment.

## Step 2: Install WSL

1. In PowerShell, run:

   ```powershell
    wsl.exe --install
   ```

2. Reboot your machine when prompted.
3. Wait for WSL installation to finish (this may take a few minutes).

## Step 3: Install Required Tools with Chocolatey

Once your system is back up and WSL is set up:

In PowerShell, run the following command to install all required tools:

   ```powershell
    choco install -y rancher-desktop openjdk11 azure-cli maven terraform python git dos2unix kubernetes-helm kubernetes-cli 
   ```

## Step 4: Start Rancher Desktop

1. Launch Rancher Desktop.
2. Make sure it’s running and configured for WSL/Kubernetes (default settings work for most setups).

In PowerShell, run the following command to check if the `docker` command is available:

   ```powershell
    docker -v
   ```

If you see the Docker version printed, everything is working correctly.
Otherwise, please try restarting Rancher Desktop and check again.

## Step 5: Install Spark using Python PIP

Close and reopen your PowerShell window to refresh the environment.
In PowerShell, run the following command to install spark:

   ```powershell
    pip install pyspark
   ```

⚠️  Note: Some packages like Spark  may require manual setup after install. Refer to the official documentation if you face issues.

✅ You’re All Set

Once all tools are installed and Rancher Desktop is running, you’re ready to move on with the project setup.
