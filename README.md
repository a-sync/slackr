# slackr

### Requirements
 * bash compatible shell
 * sane install of python
 * sane install of curl

### Installation
 1. download and unpack the [archive](https://github.com/a-sync/slackr/archive/master.tar.gz)
 2. enter the unpacked directory and make [slackr](slackr) executable
 3. set [your webhook](https://my.slack.com/services/new/incoming-webhook/) url in the WEBHOOK_URL variable of [slackr](slackr#L3)
 4. create a global symbolic link
```bash
curl -sL https://github.com/a-sync/slackr/archive/master.tar.gz | tar xz
cd slackr-master && chmod +x slackr
read -p "Enter webhook url: " WHURL && sed -i "3s|.*|WEBHOOK_URL=\"$WHURL\"|" slackr
sudo ln -s "$(readlink -f slackr)" /usr/local/bin
```

### Usage
```
Usage: slackr [options] <text>

Options:
    [-r <channel or @user>] 
    [-i <bot icon emoji>] 
    [-n <bot name>] 
    [-c <good|warning|danger|#hex color>] 
    [-a <author name>]
    [-t <title>]
    [-l <title link url>]
    [-f <footer text>] 
    [-w <webhook url>]

Examples:
    slackr some text
    slackr -c good -n friendlybot -i :cat: hello
    slackr -r general < logfile.txt
    ls -la /etc/ | slackr -r @smith -f "$(history 1)"
    tail -n 10 /var/log/syslog | slackr -a "$(id -un) $(hostname -f)"
```
