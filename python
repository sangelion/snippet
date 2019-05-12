# Python Snippet

## PYTHONPATH declaration in the script
``` python
import os
import sys

IOT_TEST_BASEDIR = os.path.dirname(os.path.abspath(__file__))

if IOT_TEST_BASEDIR not in sys.path:
    sys.path.append(IOT_TEST_BASEDIR)
```
```python
import os
import sys

VT_PATH = os.path.abspath(os.path.join(os.path.dirname(__file__), "..", ".."))

sys.path.append(VT_PATH)
```
``` python
import os

uppath = lambda _path, n: os.sep.join(_path.split(os.sep)[:-n])
# dir1 = uppath(__file__, 1)
# print(dir1)
WEB_DIR = uppath(__file__, 3) + "/iot_test_framework/utils/web/"

sys.path.append(WEB_DIR)
```

## PYTHONPATH declaration using systemd
``` sh
[Unit]

[Service]
Type=idle
User=root
Environment='PYTHONPATH=locationofthepathwithinitpy'
ExecStart=/usr/bin/python python.py
RestartSec=10s
Restart=on-failure

[Install]
```

## Argument the module
```python
#!/usr/bin/env python

import argparse
import importlib

config_descp = 'Configuration file from {BASEDIR}/config/CONFIG_FILE'
parser = argparse.ArgumentParser()
parser.add_argument('--config', dest='config_file', help=config_descp)
args = parser.parse_args()

config_module = "config." + args.config_file
config = importlib.import_module(config_module)
```

## logger, stdout to terminal and file
``` python
import sys

class Logger(object):
    def __init__(self):
        self.terminal = sys.stdout
        self.log = open("logfile.log", "a")

    def write(self, message):
        self.terminal.write(message)
        self.log.write(message)

    def flush(self):
        #this flush method is needed for python 3 compatibility.
        #this handles the flush command by doing nothing.
        #you might want to specify some extra behavior here.
        pass

sys.stdout = Logger()
print 'Hello'

```
