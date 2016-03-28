# Mutt Configuration

(This is still a draft being updated)

This mutt config has evolved over quite some time. I have tidied it up a bit,
added comments and put it on github as it may be interesting for others. Some
features:

 - Uses Maildir
 - Supports multiple accounts
 - Fetchmail + procmail + spamassassin to get mail
 - msmtp to send mail
 - goobook for address lookup

Mail is stored locally (handy for laptop users). The way I like to deal with
mail is perhaps a bit different to most people, so be sure to optimise things
to suit your own environment if you decide to copy a fair part of it.

**NOTE:** Large parts of this config have been inspired, or shamelessly copied
from other people's configs. Instead of re-inventing the wheel, I've gone for
what works. I have found that looking at other peoples configurations on
github and via google is a great way to learn new ideas and optimise your
own config.

## Environment

This config uses `fetchmail`, `procmail`, `msmtp`, `goobook`, `spamassassin`,
`gnupg` and `urlview` to provide various required capabilities.

### Receiving mail

```
Gmail        }
Google Apps  }
Zoho         } --> fetchmail --> procmail --> Maildirs  <--> mutt
POP3         }                      ^
IMAP         }                      |
                                    +--> spamassassin
```

### Sending mail

```
mutt --> msmtp --> smtp
```

### Address book integration

```
mutt <--> goobook
```

## Install required dependencies

mutt
fetchmail
procmail
spamassassin
msmtp
goobook         (maybe use python-pip)
urlview

## Configuration

My actual mutt configuration, procmail config and mailcap file is in this
repo, however goobook, gnupg/ssh, fetchmail and msmtp are not since they
contain senstive info.

To assist, I have added a conf-examples directory which contains example
`.procmailrc and .fetchmailrc` files. They are commented reasonably well (I
hope) and could be used to get a head start configuring them for your own mail
providers.

```bash
./conf-examples/fetchmailrc-example
./conf-examples/msmtprc-example

```
You can copy these to `~/.fetcmailrc` and `~/.procmailrc`, configure them to
suit your environment and should be well on your way.

### Cloning the repo

If you clone this repo, I usually clone it to `~/.mutt-configs` in my home
directory.

```bash
git clone git@github.com:jaimetarrant/muttrc.git .mutt-configs
```

From here, there is a script located in the `util` directory called
`setup-symbolic-links` which, with some minimal configuration, will setup
symbolic links in your home directory to the configuration files located in
`~/.mutt-configs`.

The particular line you are looking for to make sure it works properly is
this one:

```bash
export LINKFILES="muttrc procmailrc mailcap"
```

Now, ofcourse you will need to make a lot of edits to the muttrc, and all
files contained in the pulled in repositories `./mutt/` directories. In
particular, don't forget to:

 - personalise the muttrc file
 - personalise the mailbox-and-addresses file
 - change the public key in the crypto file
 - look at and personalise all other files

## Quick Start using this config

(Not written yet)


## See also

List other good configs here



