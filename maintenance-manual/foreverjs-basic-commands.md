# ForeverJS basic commands

What is forever?

Forever is a process management tool for NodeJS. It servers two major functions&#x20;

1. File based logging of application execution.
2. Restarting the service upon crashes.

### Installation

```
  $ [sudo] npm install forever -g
```

#### Command Line Usage

You can use forever to run scripts continuously (whether it is written in node.js or not).

**Example**

```
// This command is to be run from the directory where the service is installed
forever start . 
```

### Important actions of Forever command

Following&#x20;

```
  actions:
    start               Start SCRIPT as a daemon
    stop                Stop the daemon SCRIPT by Id|Uid|Pid|Index|Script
    stopall             Stop all running forever scripts
    restart             Restart the daemon SCRIPT
    restartall          Restart all running forever scripts
    list                List all running forever scripts
    config              Lists all forever user configuration
    set <key> <val>     Sets the specified forever config <key>
    clear <key>         Clears the specified forever config <key>
    logs                Lists log files for all forever processes
    logs <script|index> Tails the logs for <script|index>
    columns add <col>   Adds the specified column to the output in `forever list`
    columns rm <col>    Removed the specified column from the output in `forever list`
    columns set <cols>  Set all columns for the output in `forever list`
    cleanlogs           [CAREFUL] Deletes all historical forever log files
```

