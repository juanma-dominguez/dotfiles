# Tips

### how to know config files

list open files

lsof -c r2 "iTerm" => check files every 2 seconds, we can find which config file is using iTerm.

### Export installed software

brew bundle dump --file="HOMEBREW_BUNDLE_FILE_PATH"

pip freeze

npm list -g --depth=0

mas list => list apple store aplications

### Mac Defaults

Defaults read => list all mac defaults config
Defaults read com.apple.SoftwareUpdate => read domain configuration
Defaults read com.apple.SoftwareUpdate ScheduleFrequency => read domain key configuration
