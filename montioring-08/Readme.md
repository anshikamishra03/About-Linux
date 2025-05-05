# Linux System Monitoring

## Introduction to System Monitoring

Monitoring system resources is essential to ensure optimal performance, detect issues, and troubleshoot problems in Linux. Various tools allow us to monitor CPU, memory, disk usage, network activity, and running processes.

### Index of Commands Covered

#### CPU and Memory Monitoring

1. top – Real-time system monitoring

2. htop – Interactive process viewer (requires installation)

3. vmstat – Report system performance statistics

4. free -m – Show memory usage

#### Disk Monitoring

1. df -h – Check disk space usage

2. du -sh /path – Show disk usage of a specific directory

3. iostat – Display CPU and disk I/O statistics

#### Network Monitoring

1. ifconfig – Show network interfaces (deprecated, use ip a)

2. ip a – Show network interface details

3. netstat -tulnp – Show active connections and listening ports

4. ss -tulnp – Alternative to netstat for socket statistics

5. ping hostname – Test network connectivity

6. traceroute hostname – Show network path to a host

7. nslookup domain – Get DNS resolution details

#### Log Monitoring

1. tail -f /var/log/syslog – Live monitoring of system logs

2. journalctl -f – Live system logs for systemd-based distros

3. dmesg | tail – View kernel logs

#### CPU and Memory Monitoring

##### Using top

To view real-time CPU and memory usage:

```top```

Press q to quit.

##### Using htop

A user-friendly alternative:

```htop```

Use arrow keys to navigate and F9 to kill processes.

##### Using vmstat

To check CPU, memory, and I/O stats:

```vmstat 1 5  # Update every 1 sec, show 5 updates```

##### Checking Memory Usage

```free -m```

Shows free and used memory in megabytes.

#### Disk Monitoring

##### Using df

Check available disk space:

```df -h```

##### Using du

Find the size of a directory:

```du -sh /var/log```

##### Using iostat

Check disk and CPU usage:

```iostat```

#### Network Monitoring

##### Checking Network Interfaces

```ip a  # Show IP addresses and interfaces```

##### Viewing Open Ports and Connections

```
netstat -tulnp  # Show listening ports

ss -tulnp  # Alternative to netstat

```
##### Testing Connectivity

```
ping google.com  # Test internet connection

traceroute google.com  # Trace the path to Google

```
##### Checking DNS Resolution

```nslookup example.com```

#### Log Monitoring

##### Live Monitoring of System Logs

```
tail -f /var/log/syslog  # Follow logs in real-time
journalctl -f  # Systemd logs
```

##### Checking Kernel Logs

```dmesg | tail```
