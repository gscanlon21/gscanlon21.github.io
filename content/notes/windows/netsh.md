+++
title = "netsh"
updated = 2021-03-27

[extra]
site = "https://docs.microsoft.com/en-us/windows-server/networking/technologies/netsh/netsh"
references = [
  { mark = "1", title = "Docs", href = "https://docs.microsoft.com/en-us/windows-server/networking/technologies/netsh/netsh" }
]
+++

# netsh
> Network shell (netsh) is a command-line utility that allows you to configure and display the status of various network communications server roles and components<sup>[1]</sup>

## Reserved Ports

Applications may reserve port ranges to make sure they don't run into 'port already in use' conflicts.

### Find excluded IPV4 ports
```powershell
netsh interface ipv4 show excludedportrange protocol=tcp
```

### Reserve a port range
```powershell
netsh interface ipv4 add excludedportrange protocol=tcp startport=50101 numberofports=1 store=persistent
```