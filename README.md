# plymouth-themes
This is a repository for making and consolidating plymouth themes primarily for use on the Rasbperry Pi

### Installing Plymouth on Raspbian Jessie Lite:

Plymouth should already be installed on the full Raspbian, but if you're using Raspian Lite then you'll need to go through the following steps to enable it:

```
sudo apt-get install plymouth plymouth-themes
```
Install Raspberry Pi Foundation Pixel splash

```
sudo apt-get install pix-plym-splash
```

Enable in /boot/cmdline.txt

add `quiet splash plymouth.ignore-serial-consoles` on the same line

and remove `plymouth.enable=0` if you're using retropie

## Using Plymouth

### List Themes:

```
plymouth-set-default-theme --list
```

### Set Default Theme:

```
sudo plymouth-set-default-theme yourtheme
```

### Test Theme:

```
sudo plymouthd
sudo plymouth --show-splash
sudo plymouth quit 
```

If you want a little more debugging while testing:
```
sudo plymouthd --debug --debug-file=/tmp/plymouth-debug-out ; sudo plymouth --show-splash ; for ((I=0;I<10;I++)); do sleep 1 ; sudo plymouth --update=event$I ; done ;sudo  plymouth --quit
```


### Adding a new theme

Add your new themes to:

```
/usr/share/plymouth/themes/
```
