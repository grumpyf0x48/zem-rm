# Zen rm

You will never delete files again by mistake !!!

`zrm` is a safe alternative to the `rm` command for `Bash`.

## Why

Using an alias for the `rm` command like this:

```console
alias rm='rm -i'
```

is completely useless because it will not prevent you from entering:

```console
rm -f important_file
```

which will remove the file without any confirmation because the `-f` flag is the last one on the command line :disappointed: !

## Installation

To install `zrm`, enter the following command:

```console
curl -L https://raw.githubusercontent.com/grumpyf0x48/zem-rm/master/.zrm -o $HOME/.zrm
```

or you can use wget instead:

```console
wget https://raw.githubusercontent.com/grumpyf0x48/zem-rm/master/.zrm -O $HOME/.zrm
```

Then, add the following at the end of your `.bashrc` file:

```console
if [ -f ~/.zrm ]; then
    . ~/.zrm
fi
```

using:

```console
echo '[ -f ~/.zrm ] && . ~/.zrm' | tee -a ${HOME}/.bashrc
```

You should then see a new alias defined in your next terminal session:

```console
alias | grep rm
alias rm='zrm_rm'
```

## Sample use

```console
cd some_folder
rm -fr *
Starting command: /bin/rm '-fr' '--interactive=always' 'gpg-6I0M4t' 'gpg-wblG4t' 'pulse-PKdhtXMmr18n'
/bin/rm : remove directory «gpg-6I0M4t» ?
```

## Configuration

Zen rm can be configured with the following variables set in the `.zrm` file.

### Customizing interactive mode

**zrm_interactive_mode** corresponds to the `--interactive` flag of the `rm` command.

### Displaying executed command

**zrm_echo** allows to display the `rm` command before executing it.

### Bypassing the alias creation

It is also possible to bypass the creation of the `rm` alias, which can be useful in a Shell profile.

To do this, all you need is define a function named **zrm_bypassed**, returning **true** when the alias should not be
created.

For example:

```console
zrm_bypassed() {
    [[ $(pwd) = *runtime* ]]
}
```

## License

Copyright (C) Pierre-Yves Fourmond.

Zen rm is free software, distributed under the terms of the [GNU](https://www.gnu.org) General Public License as published by the [Free Software Foundation](https://www.fsf.org), version 3 of the License (or any later version). For more information, see the file [LICENSE](LICENSE.md).

Copying and distribution of this file, with or without modification, are permitted in any medium without royalty provided the copyright notice and this notice are preserved. This file is offered as-is, without any warranty.

<a href="https://www.gnu.org/licenses/gpl-3.0.en.html" title="General Public License" target="_blank"><img src="https://www.gnu.org/graphics/gplv3-with-text-84x42.png" /></a>
