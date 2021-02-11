# sftpConfigReader

### Intro

**sftpConfigReader** is a tiny package that reads SFTP client configuration
settings stored in **\*.ini** configuration file.

I created the package for convenience when working on and application that 
was using Paramiko SFTP library:
[http://www.paramiko.org/](http://www.paramiko.org/)

### Example:
Suppose your SFTP client configuration file is stored in
/home/johndoe/.sftp/some_sftp_server/config.ini. 
```
[sftp]
sftp_host=localhost
port=22
user=john
password=helloJohn
known_hosts=/home/john/.ssh/known_hosts
```

You want your Python application to access the SFTP connection settings.
```
from sftpConfigReader import read_sftp_config

conf_file = r'home/johndoe/.sftp/some_sftp_server/config.ini'
settings_dict = read_sftp_config(conf_file, 'sftp')

```
If the path to the configuration file and the section name are correct, then
*settings_dict* variable contains SFTP settings as a dictionary.

### Project GitHub:
[https://github.com/alv2017/sftp_config_reader](https://github.com/alv2017/sftp_config_reader)