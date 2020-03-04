# ChromeOS Debugging Tool  

This tool will run tests on devices to reproduce errors or issues.

## Prerequisites

You will need to install sshpass to run this script. 

```
$ sudo apt-get install sshpass
```

## Running

```
$ python chromeDebugging.py
```

## Syntax

Here is an example of how to execute the tool using the arguments.

```
$ python chromeDebugging.py --test servo_coldboot --ip 192.168.1.234 --command "dmesg" --search_for "HC died" 
```


usage: chromeDebugging.py 
						[-h] [--testcase TESTCASE_TO_RUN]
                        [--test TEST_TO_RUN] [--ip IP_ADDRESS]
                        [--after_test_delay WAIT_DEVICE_INITIALIZATION]
                        [--count ITERATION_COUNT] [--command CMD_TO_RUN]
                        [--search_for SEARCH_PATTERNS [SEARCH_PATTERNS ...]]

optional arguments:
  -h, --help            show this help message and exit

  --testcase TESTCASE_TO_RUN
                        testcase to run is before reboot or suspend test

  --test TEST_TO_RUN
						test to run is either "reboot" or "suspend" or
                        "rtc_coldboot" or "ec_coldboot" or "servo_coldboot"

  --ip IP_ADDRESS
						provide remote system ip

  --after_test_delay WAIT_DEVICE_INITIALIZATION
                        Provide Device initialization delay in seconds after test!

  --count ITERATION_COUNT
                        Provide iteration count!

  --command CMD_TO_RUN
						Please mention the command to check in double quotes!

  --search_for SEARCH_PATTERNS [SEARCH_PATTERNS ...]
                        Provide one or many search strings with space. 
						If found, test will FAIL/STOP.  

