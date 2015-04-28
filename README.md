# Supervisor service for Systemd #

This service is for  Systemd (system and service manager) on CentOS 7 / Fedora 21.

## Usage ##

### Installation. ####

Install supervisor:

```
$ sudo yum install python-setuptools -y
$ sudo easy_install supervisor
```

### Clone repository. ###

Clone this repo:

```
$ git clone https://github.com/zokeber/supervisor-systemd.git ~/supervisor-systemd
```

### Copy directories and files. ###

Copy directories/files to destinations ```/etc/supervisor``` and ```/etc/systemd/system```, and create the log directory:

```
$ sudo cp -vr ~/supervisor-systemd/etc/supervisor /etc/supervisor
$ sudo cp -vr ~/supervisor-systemd/etc/systemd/system/supervisord.service /etc/systemd/system/
$ sudo mkdir -p /var/log/supervisor
```

Create alias in ~/.bashrc or ~/.zshrc files:

```
alias supervisorctl="supervisorctl -c /etc/supervisor/supervisord.conf"
```

Enable supervisord service:

```
$ sudo systemctl enable supervisord.service
```

Start supervisord service:

```
$ sudo systemctl start supervisord.service
```