# hl-pyvpn
Revised Python version of the commandline OpenVPN solution for Hacking-Lab.com, originally created by Zy0d0x

## Requirements:
* python (at least 2.7, but 3.5+ also works)
* openvpn
* the Hacking-Lab certificate (it can be downloaded from http://media.hacking-lab.com/largefiles/livecd/z_openvpn_config/backtrack/)


## Usage:
python hl-pyvpn.py [-h] [--hostname HOSTNAME] [--port PORT]
                   [--certificate CERTIFICATE] [--logdir LOGDIR] [--logvpn]

### Arguments:
  `-h`, `--help`            show this help message and exit
  `--hostname` HOSTNAME   sets the host address (default: 212.254.246.102)
  `--port` PORT           sets the port of the host (default: 443)
  `--certificate` CERTIFICATE
                        path to the certificate file (default: hlca.crt)
  `--logdir` LOGDIR       dir to place log files (default: /var/log/hl_pyvpn/)
  `--logvpn`              if specified, all openvpn output is logged in
                        log_hl_openvpn.log (default: False)


* There is usually no need to touch `--hostname` or `--port` unless Hacking-Lab changes it.
* `--certificate` should point to the path of the .crt-file downloaded from the link above. Alternatively the .crt-file can be named `hlca.crt` and placed in the same directory as the script, thus the `--certificate` parameter is not needed.
* The `--logvpn` flag specified whether the OpenVPN output should be logged to a file as well. NOTE: This will store your entered password as cleartext!!!


## Contributing
Please comment and critique. Also feel free to add pull requests with improvements. The state of the code seems to me alright, but it could certainly be refactored.
