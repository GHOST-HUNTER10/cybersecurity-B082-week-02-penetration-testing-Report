# Network Discovery Commands

> Perform network discovery only on an owned or explicitly authorized network.

## Windows Network Configuration

```cmd
ipconfig
```

Use the result to identify the authorized subnet.

## Zenmap

Recommended practical workflow:

```text
Target: [authorized subnet]
Profile: Ping Scan
```

Record:

- Live hosts
- IP addresses
- MAC addresses where available
- Host observations
- Topology output

Do not replace actual evidence with example addresses.
