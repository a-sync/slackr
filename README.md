# slackr

## Install
 * set your webhook url in the WEBHOOK_URL variable of **slackr**
 * make **slackr** executable with chmod +x
 * to make it globally available copy **slackr** to ~/bin/ or create a symbolic link to it

## Usage
```bash
slackr some text
ls -alF | slackr -r @smith
slackr -r #general < logfile.txt
slackr -c good -n friendlybot -i :cat: hello
```
