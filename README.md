# checkconfig2
CA UIM Checkconfig2

Retrieve configuration for hubs, robots and probes / packages (and SSR profile id if here). You can retrieve .log and .cfg as well (there are stored in the ouput directory).

At every execution a new SQLite table is created, at the end of the execution you can open the SQLite database to see your data.

> Think to update the use lib "X:/Nimsoft/perllib"; at the start of the script

## Requirements
- CA UIM Perl SDK (with all the requirement & perl executable installed on the system)

## Configuration 

```xml
<setup>
    logfile = checkconfig.log
    loglevel = 3
    logsize = 1024
    login = 
    password = 
</setup>
<monitoring>
    get_probes_configuration = 1
    get_probes_log = 0
    get_packages = 1
    get_processes = 0
    monitored_probes  = cdm,processes,logmon,ntservices,ntevl,dirscan
    excluded_robots =
    hubs_list =
    hubs_restrict = 0
    conf_commit = 1
</monitoring>
``` 

> Dont forget to enter the login and password.

- hubs_restrict => Active the hubs_list
- conf_commit => SQL auto-commit (stay to 1 for good performance).


## Load with .txt containing a robots list

```
checkconfig.pl -f robotslist.txt
```

The list of robots must be separated by a new line `\n`.

```
robot1
robot2
robot3
```
