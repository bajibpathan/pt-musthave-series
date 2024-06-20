## Linux Native Monitoring Tools

The Linux operating system includes numerous native monitoring tools that assist in monitoring server performance.

In some situations, when no external monitoring tools are available for Linux servers, we can rely on these built-in tools to effectively monitor server performance.

### Key Server Components

- CPU
- Memory
- Disk
- Network

### Native tools to monitor key server components

- CPU
  - top
  - vmstat
  - mpstat
- Memory
  - vmstat
  - free
- Disk
  - iostat
- Network
  - sar

### How to monitor?

- Execute the tools individually
- Custom Scripts

### Tools with some examples

1. **top** - Provides a real-time, dynamic view of system processes and CPU usage

```bash
# Syntax:
$ top [options] [arguments]

# To list all runnning Linux processes on the system
$ top

# To exit after "x" repetitions
$ top -n 5

# Sort Processes
#By default, top sorts the process list using the %CPU column. To sort processes using a different column, press one of the following keys:

M. Sort by the %MEM column.
N. Sort by PID column.
T. Sort by the TIME+ column.
P. Sort by the %CPU column.

# To Filter Processes by Specific User
$ top -u
```

2. **vmstat** - To obtain information about memory, system processes, paging, interrupts, block I/O, disk, and CPU scheduling

```bash
# Syntax:
$ vmstat [options] [delay [count]]

# Note: If you don't have vmstat on your machine, install it by running
$ sudo dnf install sysstat

# To display system information
$ vmstat

# To display Active and Inactive System Memory
#Active Memory: Memory in use by a process
#Inactive Memory: Memory allocated to a process which is no loner running
$ vmstat -a

# To delay the each output update
# Here there is a 5 second delay betwen each report update. If no delay specified only output is printed.
$ vmstat 5

# To use a count value to carry out the X number of updates
$ vmstat 5 3
```

3. **mpstat** - To report processor related statistics

```bash
# Syntax:
$ mpstat [options] [arguments]

# Note: If you don't have vmstat on your machine, install it by running
$ sudo dnf install sysstat

# To display processor and CPU statistics.
$ mpstat

# To display processor number of all CPUs.
$ mpstat -P ALL

# To display the utilization by a specific processor.
# 1 is the processor number
$ mpstat -P 1

# To display CPU usage with a time interval
$ mpstat 1 5
```

4. **free** - To get a detailed report on the system’s memory usage.

```bash
# Syntax:
$ free [options]

# To display information about the memory and swap.
$ free

# To display the memory usage in human readable format
$ free -h

# To display the column totals
$ free -h -t

# To display the output for a specific number of times with a specific delay
$ free -s 5 -c 3
```

5. **iostat** - To monitor system input/output statistics for devices and partitions.

```bash
# Syntax:
$ iostat [options]

# To displays CPU usage information and I/O stats for each partition on the system.
$ iostat

# To gather the data at a given interval
$ iostat 5
#Note: You must use Ctrl + C to exit the run.

# To display the data more readable format
$ iostat -m

# To display the output for a specific number of times with a specific delay
$ iostat -m 2 3
```

6. **sar** - To monitor the System CPU / Memory/ Network activity. sar - System Activity Reporter.

```bash
# Syntax:
$ sar [options]
-u: CPU Usage
-r: free and Used Memory
-b: I/O Activities
-n: Network Stastics

Note: You can add additional parameters at the end of the command.

# To display a summary of CPU usage for 1 sec interval for 3 times.
$ sar -u 1 3

# To display the network stats
$ sar -n DEV 1
```

### How to Monitor?

- By executing the commands / tools /utilities individually from terminal
- By creating the custom shell scripts and scheduling them.

### Sample Shell Script

```bash
$ vi monitor.sh

#Press I to switch to INSERT mode

#Type the below inside the monitor.sh script

#######################
#!/bin/bash

#Get current CPU usage as a percentage
CPU=$(date && top -bn1 | grep "Cpu(s)" | awk '{print $2, $4}')
echo $CPU >> cpu_report.csv

#Get current RAM usage as a percentage
MEMORY=$(free -tm | grep "Total" | awk '{print $2, $3, $4}')
echo $MEMORY >> memory_report.csv
#######################

# To save and quit type :wq
# To give executable permissions type the following command
$ chmod 755 monitor.sh

# To execute the script
$ ./monitor.sh
```

To schedule the script periodically, we need to use "crontab"

```bash
# To list the existing scheduled jobs
$ crontab -l

# To create a new schedule
$ crontab -e
# Type the following in the editor
* * * * * sh ~/monitor.sh

# To delete the schedules
$ crontab -r
```
