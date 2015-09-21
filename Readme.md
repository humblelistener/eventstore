### Event store apparently didn't install properly on pure debian jessie
### Threw the following error

```
root@d175db83edfa:/# apt-get --reinstall install eventstore-oss
Reading package lists... Done
Building dependency tree
Reading state information... Done
0 upgraded, 0 newly installed, 1 reinstalled, 0 to remove and 0 not upgraded.
Need to get 17.8 MB of archives.
After this operation, 0 B of additional disk space will be used.
Get:1 https://apt-oss.geteventstore.com/ubuntu/ trusty/v3.2.1 eventstore-oss amd64 3.2.1 [17.8 MB]
Fetched 17.8 MB in 51s (348 kB/s)
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 76, <> line 1.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/x86_64-linux-gnu/perl/5.20.2 /usr/local/share/perl/5.20.2 /usr/lib/x86_64-linux-gnu/perl5/5.20 /usr/share/perl5 /usr/lib/x86_64-linux-gnu/perl/5.20 /usr/share/perl/5.20 /usr/local/lib/site_perl .) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7, <> line 1.)
debconf: falling back to frontend: Teletype
(Reading database ... 8249 files and directories currently installed.)
Preparing to unpack .../eventstore-oss_3.2.1_amd64.deb ...
eventstore: unrecognized service
Unpacking eventstore-oss (3.2.1) over (3.2.1) ...
Processing triggers for systemd (215-17+deb8u2) ...
Setting up eventstore-oss (3.2.1) ...
```
