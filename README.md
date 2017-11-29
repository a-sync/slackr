# slackr

### Requirements
 * bash compatible shell
 * sane install of python
 * sane install of curl

### Install
```bash
cd slackr
```
 * set [your webhook](https://my.slack.com/services/new/incoming-webhook/) url in the WEBHOOK_URL variable of [slackr](slackr#L3)
```bash
read -p "URL: " WHURL && sed -i '3s|.*|WEBHOOK_URL="${WHURL}"|' slackr
```
 * make [slackr](slackr) executable with chmod +x
```bash
chmod +x slackr
```
 * create a global symbolic link
```bash
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
