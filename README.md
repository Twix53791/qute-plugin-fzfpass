# qute-plugin-fzfpass
Manage your stored passwords with pass and fzf in a popup window. For qutebrowser.

## Usage
Passwords are stored in `pass` with the format: domainname/login. For each url domain, multiple logins can be saved, associated with a pasword by `pass`. fzfpass is intended to be use with the script [qute-pass](https://github.com/qutebrowser/qutebrowser/blob/main/misc/userscripts/qute-pass) provided by qutebrowser allowing to insert the login informations on the webpages, according to the domain.

With fzfpass, you can :
- view passwords (potentially protected by a passphrase)
- change the password associated to one entry (pair domain/login)
- rename any number of entries (multiple selection is allowed), the domain or the login infos.
- delete any number of entries (multiple selection is allowed)
- add new entry for the current url
- add new login/password pair to any existing domain

## Installation

```
git clone https://github.com/Twix53791/qute-plugin-fzfpass/
cd qute-plugin-fzfpass
cp fzfpass-userscript ~/.config/qutebrowser/userscripts/
cp qute-plugin-fzfpass ~/config/qutebrowser/bin/
```

* **edit `fzfpass-userscript` to fit your config. I use for example `kitty` as a terminal, but maybe not you...**
* `qute-plugin-fzfpass` can be copied in any bin path, for example /usr/local/bin. I have created a bin folder in qutebrowser config I added to my bin path in .zshrc (or .bashrc), but you can use your own setup.

In `config.py`:
```
'P': 'spawn -u fzfpass-userscript',
'<ctrl-p>': ':set-cmd-text -s :spawn -u fzfpass-userscript quickadd',
```

#### Config
Edit the variables of `qute-plugin-fzfpass`.

### Structure
`fzfpass-userscript` run a termminal window (I recommand to make it floating for example in your window manager rules), running the command `qute-plugin-fzfpass` which displays the content of `pass` command.

## Demo

![](https://github.com/Twix53791/qute-plugin-fzfpass/blob/main/demo.gif)
