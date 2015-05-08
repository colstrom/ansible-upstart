# ansible-upstart

[Upstart](http://upstart.ubuntu.com/) is an event-based replacement for the /sbin/init daemon which handles starting of tasks and services during boot, stopping them during shutdown and supervising them while the system is running.

[![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)

Tunables
--------
* `upstart_runtime_root` (string) - Directory for runtime data
* `upstart_pidfile_path` (string) - Path for pidfile
* `upstart_user` (string) - User to run as
* `upstart_group` (string) - Group to run as
* `upstart_name` (string) - Name of the process
* `upstart_description` (string) - Description of the process
* `upstart_start_on` (list) - Events to start on
* `upstart_stop_on` (list):  - Events to stop on
* `upstart_file_descriptor_limit` (integer) - File descriptor limit for the process
* `upstart_environment` (list) - Environment data
* `upstart_pre_start` (list) - Commands to run prior to starting
* `upstart_post_stop` (list) - Commands to run after stopping
* `upstart_script` (list) - Script to run
* `upstart_exec_path` (string) - A single command to execute
* `upstart_exec_flags` (list) - Parameters to be passed to the command
* `upstart_log_root` (string) - Directory for logs
* `upstart_log_path` (string) - Path for log file
* `upstart_capture_errors` (boolean) - Redirect STDERR to STDOUT?

Dependencies
------------
* [colstrom.logrotate](https://github.com/colstrom/ansible-logrotate/)

Example Playbook
----------------
    - hosts: servers
      roles:
         - role: colstrom.upstart
           upstart_name: nginx
           upstart_user: www-data
           upstart_start_on:
             - startup
           upstart_stop_on:
             - shutdown

License
-------
[MIT](https://tldrlegal.com/license/mit-license)

Contributors
------------
* [Chris Olstrom](https://colstrom.github.io/) | [e-mail](mailto:chris@olstrom.com) | [Twitter](https://twitter.com/ChrisOlstrom)
* Aaron Pederson
* Justin Scott
* Steven Harradine
