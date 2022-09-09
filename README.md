# DOKKU custom Procfile plugin
This plugin enables to define `Procfile` proccess config in `PROCFILE` environment variable, this helps seperating deploy environment config out of sourcecode reporsitory, thus respecting [config factor](https://12factor.net/config).

## Installation
```bash
dokku plugin:install https://github.com/hassanhe/dokku-custom-procfile-plugin.git
```

## Usage
set a environment var for a given app
```bash
dokku config:set <app> PROCFILE='web: <command>' 
```
### Multiline `Procfile`
use `echo -e` with `\n` for newlines like so
```bash
dokku config:set <app> PROCFILE="$(echo -e 'web: <command>\nrelease: <command>')"
```
## Uninstall
```bash
dokku plugin:uninstall custom-procfile-plugin
```
