# Important

This tut did on Kubuntu 18.04 (KDE)

## What do

Auto translate (with Google translate) selected text anywhere with press a key (ex. Ctr+Shift+T).

## How to

First-step, you have to install some packages:

```bash
sudo apt update
sudo apt install -y translate-shell xsel yad
```

Second-step, create a file with named ``translate-selected-text`` in $HOME dir with below content:

```bash
#!/usr/bin/env bash
echo "$(xsel -o | trans -b -no-ansi -u firefox -t vi)" | yad --title="Google Translate" --width=450 --height=300 --center --text-info --wrap
```

Third-step, move file just has created to /usr/local/bin/:

```bash
sudo mv translate-selected-text /usr/local/bin/
```

Finally-step, create a shortcut. In KDE Desktop environment, you access to **System settings** -> **Shortcuts** -> **Custom Shortcuts**, after create a shortcut with trigger shortcut is ``Ctrl+Shift+L`` and Action is command ``translate-selected-text``.

![screenshot1](https://github.com/tuanlh/notes/raw/master/images/sc_shortcut_setting_1.png)

![screenshot2](https://github.com/tuanlh/notes/raw/master/images/sc_shortcut_setting_2.png)


## Result

Screenshot:

![screenshot-result](https://github.com/tuanlh/notes/raw/master/images/sc_translate_result.png)
