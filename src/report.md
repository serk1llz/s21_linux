
## Part 1. Installation of the OS ##

 - ![](report/1_version.PNG "Ubuntu version")
   *Ubuntu version*

## Part 2. Creating a user ##

 - ![](report/2_useradd.PNG "Creating a user")
   *Creating a user*
 - ![](report/2_groupadd.PNG "User existense")
   *User is created*
   
## Part 3. Setting up the OS network ##

- с помощью команды sudo nano /etc/hostname поменял имя машины
 - ![](report/3_hostname.PNG "Machine name change")
   *Machine name set to user-1*
 - ![](report/3_date.png "Timezone")
   *Ttimezone set*
 - ![](report/3_ifconfig.PNG "Network interfaces")
   *Network interfaces*
 - Интерфейс lo (loopback) является особым виртуальным интерфейсом в сетевой подсистеме операционной системы. Он используется для установления связи между различными сетевыми приложениями, работающими на одном и том же устройстве. 
 - ![](report/3_addr.PNG "IP from DHCP")
   *IP address from DHCP*
 - Протокол динамической настройки хоста. DHCP используется для автоматической настройки сетевых устройств, например компьютеров, маршрутизаторов и других устройств, в сетях TCP/IP. DHCP предоставляет устройствам IP-адрес, маску подсети, адрес шлюза, DNS-сервер и другие параметры, необходимые для подключения к сети.
 - ![](report/3_gw_ip.png "GW IP")
   *External gateway IP*
   - Open file /etc/netplan/00-installer-config.yaml
   - Set IP, GW and public DNS manually
   - Apply changes and reboot
 - ![](report/3_route.png "GW and IP before change")
   *GW and IP before change*
 - ![](report/3_dns.png "DNS before change")
   *DNS before change*
 - ![](report/3_netplan.png "Path to config file")
   *Path to configuration file*
 - ![](report/3_config_file.png "Config file before change")
   *Configuration file before change*
 - ![](report/3_config_file_chaged.png "Config file after change")
   *Configuration file after change*
 - ![](report/3_netplan_apply.png "Apply configuration")
   *Apply configuration*
 - ![](report/3_gw_ip_chanegd.png "GW and IP after change")
   *GW and IP after change*
 - ![](report/3_dns_chn.png "DNS after change")
   *DNS after change*
 - ![](report/3_ping_111.png "Ping 1.1.1.1")
   *Ping 1.1.1.1 result*
 - ![](report/3_ping.png "Ping ya.ru")
   *Ping ya.ru result*
 
## Part 4. OS update ##

 - ![](report/4_update.png "Updated system")
   *All packages updated*

## Part 5. Using the sudo command ##

 - The sudo command (Superuser Do) grants a user authorities that are by default restricted for the root user for safety
 - ![](report/5_user_sudo.png)
 - ![](report/5_user_dok.png)
 - ![](report/5_hostname.png "Hostname changed")
   *Hostname set by user created in Part 2*
   
## Part 6. Installing and configuring the time service ##

 - ![](report/6_time.png "Timezone synchronized")
   *Timezone synchronized*
   
## Part 7. Installing and using text editors ##

 - ![](report/7_nano.png "Nano. Nickname")
   *Nano editor. Nickname*
 - ![](report/7_vim.png "Vim. Nickname")
   *Vim editor. Nickname*
 - ![](report/7_joe.png "Joe. Nickname")
   *Joe editor. Nickname*
 - Nano: press Ctrl+s, then Ctrl+x
 - Vim: in the command line, type :wq!
 - Joe: press Ctrl + K, press X
 - ![](report/7_nano_nosave.png "Nano. Content changed")
   *Nano editor. Content changed*
 - ![](report/7_vim_nosave.png "Vim. Content changed")
   *Vim editor. Content changed*
 - ![](report/7_joe_nosave.png "Joe. Content changed")
   *Joe editor. Content changed*   
 - Nano: press Ctrl+x, then type N
 - Vim: in the command line, type :q!
 - Joe: press Ctrl + K, press D, then press n and press Enter
 - ![](report/7_nano_search.png "Nano. Search")
   *Nano editor. Search to replace*
 - ![](report/7_vim_search.png "Vim. Search")
   *Vim editor. Search to replace*
 - ![](report/7_joe_search.png "Joe. Search")
   *Joe editor. Search to replace*
 - Nano:
   - press Ctrl+\
   - type a search word, and press Enter
   - type a substitution word, and press Enter
   - select "Y" to replace all occurrences
 - Vim:
   - in the command line, type :%s/word-to-replace/substitution-word/g, and press Enter
   - (% is to search throughout the file, g is to replace all occurrences)
 - Joe:
  - press Ctrl + K, and press F
  - type a search word and select Ignore mode
  - Press Ctrl + K, and press L, select string, and search
  - If replace, select Replace mode
  - repeat 3 point, and press y
 - ![](report/7_nano_chn.png "Nano. Replace")
   *Nano editor. Replacement*
 - ![](report/7_joe_chn.png "Joe. Replace")
   *Joe editor. Replacement*
 - ![](report/7_vim_chn.png "Vim. Content replaced")
   *Vim editor. Content replaced*

## Part 8. Installing and basic setup of the SSHD service ##

 - ![](report/8_enable_ssh.png "SSH autostart enabling")
  *SSH service autostart enabling*
 - To reset SSHd port: open file /etc/ssh/sshd_config, and manually change the port from 22 to 2022
 - ![](report/8_port.png "SSHd port change")
   *Changing SSHd port from 22 to 2022*
 - To enable the changes, it is necessary to uncomment the line with the word "Port" and restart the sshd service
 - ![](report/8_procces.png "SSHd presence")
   *SSHd process presence*
 - the ps command is to view running processes:
   - the aux option is to show all processes running
   - grep command is to search the list of running processes for a patter following it (grep write into standard output each line that matches the pattern)
 - ![](report/8_netstat.png "Netstat -tan")
   *Netstat -tan output*
 - The combination -tan actually includes two arguments of thecommand tool Netstat:
   - -at is to show only TCP sockets
   - -n is to show addresses of hosts/ports/users numeriacally rather than symbolically
 - Column output explanation:
   - 1 Transmission Control Protocol
   - 2 a queue of bytes to be received
   - 3 a queue of bytes to be sent
   - 4 IP address of the local host and the port number in use
   - 5 the remote device IP the host tries to connect to
   - 6 a state of the socket (when set to LISTEN, i is listening to incomming connections)
   - 0.0.0.0 in the address means the wildcard address indicative of the device trying to get network traffic on any interface

## Part 9. Installing and using the top, htop utilities ##

 - ![](report/9_top.png "Top")
   *Top utility window*
 - Uptime is 3:30; Number of authorised users: 1
 - Total system load: 0.00
 - Total number of processes: 106
 - CPU load: 0.0
 - Memory load: 218.1 MiB of 1964.6 MiB
 - The highest memory usage process PID: 1 root
 - The highest CPU time process PID: 1 root
 - ![](report/9_sort_by_pid.png "Htop. Sort by PID")
   *Htop. Sorting by PID*
 - ![](report/9_sort_by_cpu.png "Htop. Sort by PERCENT_CPU")
   *Htop. Sorting by PERCENT_CPU*
 - ![](report/9_sort_by_mem.png "Htop. Sort by PERCENT_MEM")
   *Htop. Sorting by PERCENT_MEM*
 - ![](report/9_sort_by_time.png "Htop. Sort by TIME")
   *Htop. Sorting by TIME*
 - ![](report/9_filtr_sshd.png "Htop. Filter for SSHD")
   *Htop. Filter for SSHD process*
 - ![](report/9_syslog.png "Htop. Search for syslog")
   *Htop. Search for syslog process*
 - ![](report/9_time_add.png "Htop. Parameters added")
   *Htop. Hostname, clock, and uptime added*

## Part 10. Using the fdisk utility ##

 - ![](report/10_fdisk.png "Hard disk info")
   *Hard disk info*
 - Hard disk name: SDA
 - Hard disk capacity: 25 GB
 - Number of sectors: 52428800
 - Swap size: 2 GB.
 - ![](report/10_swap_size.png "Swap size")
   *Swap size*

## Part 11. Using the df utility ##

 - ![](report/11_df_info.png "Root partition in k-blocks")
   *Root partition parameters in k-blocks*
 - Partition size: 11758760 K-blocks
 - Space used: 6104260 k-blocks
 - Space free: 5035392 k-blocks
 - Pecentage in use: 55%
 - Measured in k-blocks. 1k-block = 1024 bytes.
 - ![](report/11_df_flags.png "Root partition in GB")
   *Root partition parameters in Gigabytes*
 - Partition size: 12 Gb
 - Space used: 5.9 Gb
 - Space free: 4.9 Gb
 - Percentage in use: 55%
 - Measured in Gbytes. 1 Gigabyte = 1,048,576 bytes

## Part 12. Using the du utility ##

 - ![](report/12_du_files.png "Directorys size in bytes")
   *Home directory size in bytes*
 - ![](report/12_du_var_log.png "Var/log directory content size, bytes")
   *Var/log directory content size in bytes*
   
## Part 13. Installing and using the ncdu utility ##

 - ![](report/13_nsdu_home.png "Home directory size")
   *Home directory size*
 - ![](report/13_nsdu_var.png "Var directory size")
   *Var directory content size*
 - ![](report/13_nsdu_var_log.png "Var/log directory size")
   *Var/log directory content size*
   
## Part 14. Working with system logs ##

 - ![](report/14_logined.png "Last login")
   *Last successful login*
 - Last successful login: time is 29 Feb 09:19:48, maokaica, password-login method
 - ![](report/14_sshd_res.png "SSHd restart")
   *SSHd restart, auth.log*
 - ![](report/14_ssh_syslog.png "SSHd restart")
   *SSHd restart, syslog*
   
## Part 15. Using the CRON job scheduler ##

 - ![](report/15_cron_log.png "Uptime via cron")
   *Uptime in 2 minutes via CRON*
 - ![](report/15_cron_list.png "Crontab")
   *CRON jobs*
 - ![](report/15_cron_del.png "Crontab removal")
   *Removal of CRON jobs*
