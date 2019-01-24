# ciscotool

## How to use

### Install Windows Subsystem for Linux and Ubuntu

https://docs.microsoft.com/en-us/windows/wsl/install-win10

### Run Bash on Windows Terminal and install ansible and git

```
sudo apt update
sudo apt upgrade
sudo apt install ansible git
```

### Clone this repo

```
git clone https://github.com/corsmith/ciscotool
```

### Edit the configuration

```
nano hosts
```

### Example Invocation

```
cd ciscotool
ansible-playbook -i hosts ciscotool.yaml
```

This will create a backups/ folder that looks like:

- method-host_cmd.txt

By default this will run the following ios commands on each host:

- show run
- show cdp neighbor

This can be changed by editing the file group_vars/cisco

```
nano group_vars/cisco
```

### Linux cheatsheet

list a directory (dir)
```
ls
```

change directory (cd)
```
cd somedir
```

edit text file (notepad++)
```
nano somefile
```

### Advanced Topics

The home directory of the bash on windows terminal should be in c:\Users\you\.  You should be able to browse to the backups folder in explorer and be able to open the text files.  Unix text files typically only have newlines so you may want to use notepad++ to view.

You could also have separate hosts files for each engagement for example and keep copies between engagements.

### Future Updates

- Add the output dir to the hosts file so you can separate output directories for each client
- Use git to manage the customer changes and auto commit any changes.  This would allow you to look at the changes to the customer environment over time.
