# docker-with-windows11-home
As we know, Windows11 Home cannot use the docker and here is the solution.

1. Open PowerShell in administrator mode, enter the wsl --install command, then restart your machine.
```console
wsl --install
```

2. Before install Linux distributions, you need to enable virtualization on Windows 11 PCs first.
2.1 Select Start > Settings > System > Recovery > Advanced startup, then select Restart now.
2.2 Once your PC restarts, F12. Select Troubleshoot > Advanced options > UEFI Settings > Restart.
2.3 Your PC will restart again and you'll be in the UEFI utility. At this step, you might see the UEFI referred to as the BIOS on your PC.
2.4 For my PCs (Manufacturer GIGABYTE), Settings > Advanced CPU Settigns > SVM Mode > Enabled > Save & Exit
2.5 You can check virtualization is enabled by Task Manager > Performance > CPU > Virtualization row
2.6 Turn on Virtual Machine Platform in Windows
2.6.1  Select Start, enter Windows features, and select Turn Windows features on or off from the list of results.
2.6.2 In the Windows Features window that just opened, find Virtual Machine Platform and select it.
2.6.3 Select OK. You might need to restart your PC.

3. Install Linux distributions
```console
wsl --install -d <Distribution Name>
```
To see a list of available Linux distributions available for download through the online store, enter
```console
wsl -l -o
```

After install Linux distributions, you can check the version of WSL each is set to by entering the command:
```console
wsl -l -v
```

Now you can use Docker command line either in PowerShell or WSL after you install docker desktop (Ensure that "Use the WSL 2 based engine" is checked in Settings > General and enable Docker integration on by going to: Settings > Resources > WSL Integration).