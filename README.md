# Zen rm

You will never delete files again by mistake !!!

`zrm` is a safe alternative to the `rm` command for `Bash`.

## Why

Using an alias for the `rm` command like this:

```sh
alias rm='rm -i'
```

is completely useless because it will not prevent you from entering:

```sh
rm -f important_file
```

and then the file will be removed without any confirmation because the `-f` flag is the last one on the command line !

## Installation

To install `zrm`, enter the following command:

```sh
curl -L https://git.framasoft.org/grumpyf0x48/zen-rm/raw/master/.zrm -o $HOME/.zrm
```

or you can use wget instead:

```sh
wget https://git.framasoft.org/grumpyf0x48/zen-rm/raw/master/.zrm -O $HOME/.zrm
```

Then, add the following at the end of your `.bashrc` file:

```sh
if [ -f ~/.zrm ]; then
    . ~/.zrm
fi
```

You should then see a new alias defined in your next terminal session:

```sh
alias | grep rm
alias rm='zrm_rm'
```

## Sample use

```sh
cd /tmp
rm -fr *
Starting command: /bin/rm '-fr' '--interactive=always' 'gpg-6I0M4t' 'gpg-wblG4t' 'pulse-PKdhtXMmr18n' 'ssh-u64Il7bcm5Lm' 'systemd-private-aecde8cab7894de08a6d2e1b09b38d7c-colord.service-htyvHK' 'systemd-private-aecde8cab7894de08a6d2e1b09b38d7c-cups.service-luv082' 'systemd-private-aecde8cab7894de08a6d2e1b09b38d7c-rtkit-daemon.service-3IpH3v' 'Temp-6f00589d-8b37-4739-be39-2bd5964e35bc'
/bin/rm : descendre dans le répertoire « gpg-6I0M4t » ?
```

## Configuration

Zen rm can be configured with the following variables set in the `.zrm` file:

- **zrm_interactive_mode** corresponds to the `--interactive` flag of the `rm` command
- **zrm_echo** allows to display the command before executing it

## License

Copyright (C) Pierre-Yves Fourmond.

Zen rm is free software, distributed under the terms of the [GNU](https://www.gnu.org) General Public License as published by the [Free Software Foundation](https://www.fsf.org), version 3 of the License (or any later version). For more information, see the file [LICENSE](LICENSE.md).

Copying and distribution of this file, with or without modification, are permitted in any medium without royalty provided the copyright notice and this notice are preserved. This file is offered as-is, without any warranty.

<a href="https://www.gnu.org/licenses/gpl-3.0.en.html" title="General Public License" target="_blank"><img src="https://www.gnu.org/graphics/gplv3-with-text-84x42.png" /></a>
