# webhook-catcher
#### Simple HTTP-server for processing webhooks from Github or Gogs portals.

You may define one repo by arguments:

  `--dir, --secret, --branch, --remote, --action, --full_name, --clone_proto`
  
define "wild" dir, using:

  `--wild_dir, --wild_secret, --wild_proto`
  
specify configuration file in .json format:

  `-c|--config`
  
or mix them all.

"wild" directory will be used to pull all repos which not defined in config or arguments. No actions allowed for wild repos.

If repo directory does not exists, it will be cloned at first hook.

Repos identifyed by "full_name", so if more then one repo defined, you must define "full_name" to all of them.

You may send SIGHUP to restart server with same arguments and re-read config if it supplied.

Also, server will be restarted after successfull pulling repo which defined as "self_update_repo" in config file.

-----

#### Usage

```
webhook-catcher [-h] [-c CONFIG_PATH] [-a LISTEN_ADDRESS]
                [-p LISTEN_PORT] [-q] [--debug]
                [--wild_dir PATH_TO_DIR] [--wild_secret SECRET]
                [--wild_proto <HTTP|SSH>] [--dir PATH_TO_REPO]
                [--secret SECRET] [--branch BRANCH_NAME]
                [--remote REMOTE_NAME] [--action ACTION]
                [--full_name FULL_NAME] [--clone_proto <HTTP|SSH>]
                [--version]
```

-----

Good luck!
