# slackr

### Requirements
    * bash compatible shell
    * sane install of python
    * sane install of curl

### Install
    * set [your webhook](https://my.slack.com/services/new/incoming-webhook/) url in the WEBHOOK_URL variable of [slackr](slackr)
    * make [slackr](slackr) executable with chmod +x
    * to make it globally available copy [slackr](slackr) to ~/bin/ or create a symbolic link to it
```bash
cd slackr

sed -i '3s|.*|WEBHOOK_URL="http://hooks.slack.com/T00000000/B00000000/XXXXXXXXXXXXXXXXXXXXXXXX"|' slackr

chmod +x slackr

sudo ln -s $(readlink -f slackr) /usr/local/bin
```

### Usage
```
Usage: slackr [options] <text>

Options:
    [-r <channel or @user>] 
    [-c <good|warning|danger|#hex color>] 
    [-n <bot name>] 
    [-i <bot icon emoji>] 
    [-f <footer text>] 

Examples:
    slackr some text
    slackr -r general < logfile.txt
    ls -alF | slackr -r @smith
    tail -n 10 /var/log/syslog | slackr -f "$(id -un) $(hostname -f)"
    slackr -c good -n friendlybot -i :cat: hello
```
