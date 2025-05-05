# Process Management in Linux

## Introduction to Process Management

A process is an instance of a running program. Linux provides multiple utilities to monitor, manage, and control processes effectively. Each process has a unique Process ID (PID) and belongs to a parent process.

### Index of Commands Covered

#### Viewing Processes

1. ps aux – View all running processes
   
2. ps -u username – View processes for a specific user
    
3. ps -C processname – Show a process by name

4. pgrep processname – Find a process by name and return its PID

5. pidof processname – Find the PID of a running program

#### Managing Processes

1. kill PID – Terminate a process by PID

2. pkill processname – Terminate a process by name

3. kill -9 PID – Force kill a process

4. pkill -9 processname – Kill all instances of a process

5. kill -STOP PID – Stop a running process

6. kill -CONT PID – Resume a stopped process

7. renice -n 10 -p PID – Lower priority of a process

8. renice -n -5 -p PID – Increase priority of a process(requires root)

#### Background & Foreground Processes

1. command & – Run a command in the background

2. jobs – List background jobs

3. fg %jobnumber – Bring a job to the foreground

4. Ctrl + Z – Suspend a running process

5. bg %jobnumber – Resume a suspended process in the background

#### Monitoring System Processes

1. top – Interactive process viewer

2. htop – User-friendly process viewer (requires installation)

3. nice -n 10 command – Run a command with a specific priority

4. renice -n -5 -p PID – Change priority of an existing process
   
#### Daemon Process Management

1. systemctl list-units --type=service – List all system daemons

2. systemctl start service-name – Start a daemon/service

3. systemctl stop service-name – Stop a daemon/service

4. systemctl enable service-name – Enable a service at startup

#### Viewing Process Details

##### Using ps

Show processes for a specific user:

```ps -u username```

Show a process by name:

```ps -C processname```

##### Using pgrep

Find a process by name and return its PID:

```pgrep processname```

##### Using pidof

Find the PID of a running program:

```pidof processname```

#### Managing Processes

##### Killing Processes

To terminate a process by PID:

```kill PID```

To terminate using process name:

```pkill processname```

Force kill a process:

```kill -9 PID```

Kill all instances of a process:

```pkill -9 processname```

##### Stopping & Resuming Processes

Stop a running process:

```kill -STOP PID```

Resume a stopped process:

```kill -CONT PID```

#### Changing Process Priority

View process priorities:

```top  # Look at the NI column```

Change priority of a running process:

```renice -n 10 -p PID  # Lower priority (positive values)```
```renice -n -5 -p PID  # Higher priority (negative values, root required)
```
##### Running Processes in the Background

Run a command in the background:

```command &```

List background jobs:

```jobs```

Bring a job to the foreground:

```fg %jobnumber```

Send a running process to the background:
```
Ctrl + Z  # Suspend process
bg %jobnumber  # Resume in background
```

#### Monitoring System Processes

##### Using top

Interactive process viewer:

1. Press k and enter a PID to kill a process.
   
2. Press r to renice a process.

3. Press q to quit.

Using htop

A user-friendly alternative to top:

```htop```

Allows mouse-based interaction for process management.

##### Using nice & renice

Run a command with a specific priority:

```nice -n 10 command```

Change the priority of an existing process:

```renice -n -5 -p PID```

#### Daemon Processes

Daemon processes run in the background without user intervention. List all system daemons:

```systemctl list-units --type=service```

Start a daemon:

```systemctl start service-name```

Stop a daemon:

```systemctl stop service-name```

Enable a service at startup:

```systemctl enable service-name```

## Conclusion
Process management is crucial for system performance and stability. By using tools like ps, top, htop, kill, and nice, you can efficiently control and monitor Linux processes.
