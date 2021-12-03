# The fork
## Aliases
Forked from https://github.com/davoam/anydo-cli to add some alises.
After installing the CLI (the Original section), you can add the following lines to the `~/.bashrc`:

```
alias adols=ado list | sed -n '/TODAY/,/TOMORROW/p #View today's tasks: adols
alias adotd="ado add" #Add a task for today: adotd 'task name'
alias adotm="ado add -d tomorrow" #Add a task for tomorrow: adotm 'task name'
alias adosd="ado add -d someday" #Add a task for someday later: adosd 'task name'
```

### Details
**View today's tasks:**
- Command: `alias adols=ado list | sed -n '/TODAY/,/TOMORROW/p'`
- Usage: `adols`

**Add a task for today:**
- Command: `alias adotd="ado add"`
- Usage: `adotd 'buy bananas'`

**Add a task for tomorrow:**
- Command: `alias adotm="ado add -d tomorrow"`
- Usage: `adotm 'buy bananas'`

**Add a task for some day later:**
- Command: `alias adosd="ado add -d someday"`
- Usage: `adosd 'buy bananas'`

## Future Plans
**Add reminders in natural language**
- For example: `ado remind me to buy bananas tomorrow afternoon`

**Add routines**
- For example: `ado append routines for 3 days`

**Plans**
- For example: `ado plan a reading day for Friday`, or `ado plan some fun activities for Saturday`
----
# Original
## Any.do CLI (unofficial)
This CLI allows to list and add tasks.

### Demo
![any.do cli demo](demo.gif)

### Installation
```bash
npm install -g ado-cli 
```

### Usage
In order to use CLI you have to login. CLI does not store your credentials.
It just uses them to get token. 

In order to **login** you have to run the following command
```bash
ado login -e your_email -p your_password
```

#### List tasks 

```bash
ado list # output all tasks
```

#### Add tasks

```bash
ado add task_title
```
Example:
```bash
ado add 'buy cookies'
```
It is also possible to set due date (-d is shortcut for --due-date). Possible values for due date are tomorrow, upcoming, someday.
```bash
ado add -d tomorrow 'buy more cookies'
```
Add several tasks
```bash
ado add --due-date tomorrow 'buy oreo' 'buy kitkat'
```

### All available commands

| Command        | Options           | Description  |
| ------------- |:-------------:| -----:|
| login| --email --password | Login to Any.DO account|
| list||Display all incomplete tasks|
| add|--due-date(optional, by default will be today)|Add task|
| delete| |Choose task to delete|
| web||Open web version of Any.DO in default browser|

### Requirements
- nodejs