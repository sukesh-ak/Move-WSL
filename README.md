# Move WSL to alternate drive
How to move WSL from C Drive to D Drive

### WSL configuration is stored in registry here
```
\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Lxss\
```

### Find you distro you want to move in the above location
Then open the path mentioned in `BasePath`.  
This is where the `ext4.vhdx` file is stored where the WSL distro is mounted from.

### Prepare for the move
```bash
# Open a command prompt and list all the running distros
> wsl -l
Windows Subsystem for Linux Distributions:
Ubuntu (Default)
docker-desktop-data
docker-desktop

# Terminate the distro instance
> wsl --terminate Ubuntu

# Shutdown WSL
> wsl --shutdown

```

### Final Step
Move the `ext4.vhdx` to new location.  
Update the registry with the new location.  

```bash
# Verify your distro is running
> wsl -l

# Start WSL again
> wsl
```
