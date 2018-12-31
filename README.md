# Zen rm

You will never delete files again by mistake !!!

`zrm` is a safe alternative to the `rm` command.

## Installation

To install `zrm`, enter the following command:

    $ sudo curl -L https://git.framasoft.org/grumpyf0x48/zen-rm/raw/master/.zrm -o $HOME/.zrm

or you can use wget instead:

    $ sudo wget https://git.framasoft.org/grumpyf0x48/zen-rm/raw/master/.zrm -O $HOME/.zrm

Then, add the following at the end of your `.bashrc` or `.zshrc` file:

```sh
if [ -f ~/.zrm ]; then
    . ~/.zrm
fi
```

You should then see a new alias defined in your next terminal session:

    $ alias | grep rm
    alias rm='zrm_rm'

## Sample use

    $ pyfourmond@charlie-watts:/tmp$ rm -fr *
    Starting command: /bin/rm '-fr' '--interactive=always' 'gpg-6I0M4t' 'gpg-wblG4t' 'pulse-PKdhtXMmr18n' 'ssh-u64Il7bcm5Lm' 'systemd-private-aecde8cab7894de08a6d2e1b09b38d7c-colord.service-htyvHK' 'systemd-private-aecde8cab7894de08a6d2e1b09b38d7c-cups.service-luv082' 'systemd-private-aecde8cab7894de08a6d2e1b09b38d7c-rtkit-daemon.service-3IpH3v' 'Temp-6f00589d-8b37-4739-be39-2bd5964e35bc'
    /bin/rm : descendre dans le répertoire « gpg-6I0M4t » ?
