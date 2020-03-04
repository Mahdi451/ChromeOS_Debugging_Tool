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
$ python chromeDebugging.py --test reboot --ip 190.128.1.120 --command "dmesg" --search_for "HC died" 
```

```
usage: chromeDebugging.py 
		[-h] [--testcase TESTCASE_TO_RUN]
                [--test TEST_TO_RUN] [--ip IP_ADDRESS]
                [--after_test_delay WAIT_DEVICE_INITIALIZATION]
                [--count ITERATION_COUNT] [--command CMD_TO_RUN]
                [--search_for SEARCH_PATTERNS [SEARCH_PATTERNS ...]]

optional arguments:
  -h, --help    
  		Show this help message and exit

  --testcase TESTCASE_TO_RUN
                Specify which testcase to run on system.
		testcase_to_run is before reboot or suspend the test.

  --test TEST_TO_RUN
		Choose from the following options for test_to_run is either "reboot" 
		or "suspend" or "rtc_coldboot" or "ec_coldboot" or "servo_coldboot"

  --ip IP_ADDRESS
		Provide IP of remote system 

  --after_test_delay WAIT_DEVICE_INITIALIZATION
                Provide Device initialization delay in seconds after test!

  --count ITERATION_COUNT
                Provide iteration count!

  --command CMD_TO_RUN
		Please mention the command to check in double quotes!

  --search_for SEARCH_PATTERNS [SEARCH_PATTERNS ...]
                Provide one or many search strings with space. 
		If found, test will either return FAIL/STOP.  
```

