# Ansible Role: uberspace-mail-spamfilter

This is part of the uberspace roles collection.

This is meant to be used on your [Uberspace](https://uberspace.de/).

Please be aware, that I'm neither part of the Uberspace team, nor am I associated to them other than having some Uberspaces myself.
This project was created, because I wanted to use the roles for myself and thought they were okay-ish enough to share them.


## What is this (from the uberspace manual)

We filter incoming mails with Rspamd which uses multiple filtering and statistical methods to generate a spam score, including (but not limited to) SPF, DMARC and DNS blacklists. Mails with a score greater than 15 get rejected. We are using Bayes filtering using the sqlite3 backend per server. To allow for some initial filtering we are retrieving example spam/ham databases provided by rspamd.com. We also autolearn ham and spam, what means that every mail with a negative score is auto-learned as ham, while every mail with a score higher than the rejection score is auto-learned as spam, given that the Bayes filter hasn’t already identified it as ham or spam.

You can find the documentation of the replaced tool `uberspace mail spamfolder` in the Uberspace Manual [here](https://manual.uberspace.de/mail-spam.html).

## Usage

| Variable | Choices/Default                            | Description                                              |
| :------: | :----------------------------------------- | :------------------------------------------------------- |
|  state   | <ul><li>present ✔</li><li>absent</li></ul> | "present" to enable the spamfolder, "absent" to disable it |

## Examples

### Enable Spamfilter

```yaml
- hosts: uberspace
  roles:
    - name: uberspace-mail-spamfilter
```

### Disable Spamfilter

```yaml
- hosts: uberspace
  roles:
    - name: uberspace-mail-spamfilter
      state: absent
```
