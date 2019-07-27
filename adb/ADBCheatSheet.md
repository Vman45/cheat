# CONFIG
### Include `adb` and other android tools on your path
In `Users/hugomatilla.bash_profile` add
`export PATH=$PATH:/Users/hugomatilla/Documents/AndroidSDKs/sdk/platform-tools`
`export PATH=$PATH:/Users/hugomatilla/Documents/AndroidSDKs/sdk/tools`

### My own adb location
`cd /Users/hugomatilla/Documents/AndroidSDKs/sdk/platform-tools`

# START
`adb shell`

# SERVER
### Kill server
`adb kill-server`

### Start server
`adb sart-server`

# FILES
### Sends files to device 
`adb push <computer.file.path> /sdcard/<device.path>`

### Retreive files from device 
`adb pull /sdcard/<device.path> <computer.file.path> `

# PACKAGES
### List all packages
`pm list packages`

### Uninstall
`pm uninstall file.name`

### Install
`pm install package.name`

# DEVICES
### List all connected devices
`adb devices`

### Clear data
`pm clear package.name`

# INTENTS
[am Command](https://developer.android.com/studio/command-line/shell.html#am)
### URI
`am start -a android.intent.action.VIEW -d https://github.com`

### Mime Type and and Extra string
`am start -a "android.intent.action.SEND" --es "android.intent.extra.TEXT" "Hello World" -t "text/plain"`

### Activity 
`am start -n "com.example.application/.MainActivity"`

### Service 
`am startservice -n "com.example.application/.BackgroundService`

### Broadcast with Action
`am broadcast -a "android.intent.action.PACKAGE_FIRST_LAUNCH" -d "com.example.application`

#### Notification
[stackoverflow](http://stackoverflow.com/questions/27800369/simulating-android-gcm)
`am broadcast -a com.google.android.c2dm.intent.RECEIVE -n <YOUR_PACKAGE_NAME>/<YOUR_RECEIVER_NAME (in the manifest)> -e "<EXTRA_KEY_1>" "<EXTRA_VALUE_1>" -e "<EXTRA_KEY_2>" "<EXTRA_VALUE_2>"`

# SQLITE
`cd data/data/<your-package-name>/databases/`

`sqlite3 <your-db-name>.db`

## Commands
### TABLES
`.tables`   
### SCHEMA
`.schema tablename`   
### QUERY
`SELECT * FROM tablename;`   
### HELP  
`.help`