# hl-pyvpn
Revised Python version of the commandline OpenVPN solution for Hacking-Lab.com, originally created by Zy0d0x

## Quickstart:
```bash
$ [sudo] apt-get install git python python-pip openvpn -y
$ [sudo] pip install pexpect
$ git clone https://github.com/ragerin/hl-pyvpn ~/hl-pyvpn/
$ curl -o ~/hl-pyvpn/hlca.crt http://media.hacking-lab.com/largefiles/livecd/openvpn-config/general/hlca.crt
```
_**NOTE:**_ The `SyntaxError` when using pip(2.7) to install `pexpect` **doesn't matter**. [[see pexpect issue #220]][1]

[1]: https://github.com/pexpect/pexpect/issues/220

Start it with:
```bash
$ [sudo] python ~/hl-pyvpn/hl-pyvpn.py
```


## Requirements:
* `python2.7` or `python3`
* `pip` or `pip3`
* `openvpn`
* `pexpect-4.0.1`
* the Hacking-Lab certificate (it can be downloaded from http://media.hacking-lab.com/largefiles/livecd/openvpn-config/general)




## Usage:
`$ python hl-pyvpn.py [-h] [--hostname HOSTNAME] [--port PORT] [--certificate CERTIFICATE] [--logdir LOGDIR] [--logvpn]`

### Arguments:
| FLAG               | ARG          | DESCRIPTION                                           |
| ------------------ |:------------:| ----------------------------------------------------- |
| `-h`, `--help`     | N/A          | show this help message and exit                       |
| `--hostname`       | `HOSTNAME`   | sets the host address (default: 212.254.246.102)      |
| `--port`           | `PORT`       | sets the port of the host (default: 443)              |
| `--certificate`    | `CERTIFICATE`| path to the certificate file (default: hlca.crt)      |
| `--logdir`         | `LOGDIR`     | dir to place log files (default: /var/log/hl_pyvpn/)  |
| `--logvpn`         | N/A          | if specified, all openvpn output is logged in log_hl_openvpn.log (default: False)|


* There is usually no need to touch `--hostname` or `--port` unless Hacking-Lab changes it.
* `--certificate` should point to the path of the .crt-file downloaded from the link above. Alternatively the .crt-file can be named `hlca.crt` and placed in the same directory as the script, thus the `--certificate` parameter is not needed.
* The `--logvpn` flag specified whether the OpenVPN output should be logged to a file as well. NOTE: This will store your entered password as cleartext!!!


## Contributing
Please comment and critique. Also feel free to add pull requests with improvements. The state of the code seems to me alright, but it could certainly be refactored.
