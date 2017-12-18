# slackr

### Requirements
 * bash compatible shell
 * sane install of python
 * sane install of curl

### Installation
 1. download and unpack the [archive](https://github.com/a-sync/slackr/archive/master.tar.gz)
 2. enter the unpacked directory and make [slackr](slackr) executable
 3. set [your webhook](https://my.slack.com/services/new/incoming-webhook/) URL in the WEBHOOK_URL variable of [slackr](slackr#L3)
 4. create a global symbolic link
```bash
curl -sL https://github.com/a-sync/slackr/archive/master.tar.gz | tar xz
cd slackr-master && chmod +x slackr
read -p "Enter webhook URL: " WHURL && sed -i "3s|.*|WEBHOOK_URL=\"$WHURL\"|" slackr
sudo ln -s "$(readlink -f slackr)" /usr/local/bin
```

### Usage
```
Usage: slackr [options] <text>

Options:
    -r <channel name|DM channel ID|member ID>
    -i <bot icon emoji>
    -n <bot name>
    -c <good|warning|danger|#hex color>
    -a <author name>
    -t <title text>
    -l <title link URL>
    -f <footer text>
    -w <webhook URL>

Examples:
    slackr some text
    slackr -c good -n friendlybot -i :cat: hello
    slackr -r general < logfile.txt
    ls -la /etc/ | slackr -r D024BE91L -f "$(history 1)"
    tail -n 10 /var/log/syslog | slackr -a "$(id -un) $(hostname -f)"
```
