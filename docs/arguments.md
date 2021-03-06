---
title: Arguments
linktitle: Arguments
description: A list with all arguments for Gitfs
keywords: [gitfs, arguments, usage]
menu:
  global:
    weight: 3
---

## Using options

In order to use options when mounting gitfs, you need to append the options as an argument when using the mount command like this:

```
-o option1=value1,option2=value2,option3=value3...
```

## All available options

<div class="formated_table col-1-25 col-2-25"></div>

| **Name**             | **Default**                | **Description**                                                                                                                                                                                                                                                                                                       |
|----------------------|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `remote_url`         |                            | the URL of the remote. The accepted formats are: <ul><li>`https://username:password@hostname.com/repo.git` – for HTTP</li><li>`username@hostname.com:repo.git` – for SSH</li></ul>                                                                                                                                    |
| `branch`             | `master`                   | the branch name to follow                                                                                                                                                                                                                                                                                             |
| `repo_path`          | `/var/lib/gitfs/repo_path` | the location where the repositories will be cloned                                                                                                                                                                                                                                                                    |
| `max_size`           | `10MB`                     | the maximum file size in MBs allowed for an individual file. If set to 0, then allow any file size                                                                                                                                                                                                                    |
| `user`               | `root`                     | the user that will mount the file system                                                                                                                                                                                                                                                                              |
| `group`              | `root`                     | the group that will mount the file system                                                                                                                                                                                                                                                                             |
| `commiter_name`     | `user`                     | the name that will be displayed for all the commits                                                                                                                                                                                                                                                                   |
| `commiter_email`    | `user@FQDN`                | the email that will be displayed for all the commits                                                                                                                                                                                                                                                                  |
| `merge_timeout`      | `5 sec`                    | the interval between idle state and commits/pushes                                                                                                                                                                                                                                                                    |
| `fetch_timeout`      | `30 sec`                   | the interval between fetches                                                                                                                                                                                                                                                                                          |
| `min_idle_times`     | `10`                       | idle cycles until gitfs will go to idle mode                                                                                                                                                                                                                                                                          |
| `idle_fetch_timeout` | `30 min`                   | the interval between fetches, when in idle mode                                                                                                                                                                                                                                                                       |
| `log`                | `syslog`                   | the path of the log file. Special name `syslog` will log to the system logger                                                                                                                                                                                                                                         |
| `log_level`          | `warning`                  | the logging level. One of `error`, `warning`, `info`, `debug`                                                                                                                                                                                                                                                         |
| `debug`              | `false`                    | the switch that sets the log level to `debug` and also enables FUSE’s debug                                                                                                                                                                                                                                           |
| `foreground`         | `true`                     | the switch that specifies whether FUSE will work in the foreground or not                                                                                                                                                                                                                                             |
| `allow_other`        | `true`                     | the switch that overrides the security measure restricting file access to the user mounting the file system. So, all users, including root, can access the files. This option is, by default, only allowed to root, but this restriction can be removed with a configuration option described in the previous section |
| `allow_root`         | `false`                    | the switch that’s similar to `allow_other` but file access is limited to the user mounting the file system and root. This option and `allow_other` are mutually exclusive                                                                                                                                             |
| `username`           |                            | the username for HTTP basic auth                                                                                                                                                                                                                                                                                      |
| `password`           |                            | the password for HTTP basic auth                                                                                                                                                                                                                                                                                      |
| `key`                | `$HOME/.ssh/id_rsa`        | the path of the SSH private key. **NOTE**: the public key is constructed by appending .pub to this path and the file **MUST** exist                                                                                                                                                                                   |
