# jobs

A ⟮job⟯ in computing is ⟮a thing to do⟯, generally ⟮scheduled⟯, and generally ⟮in the background without intervention⟯.
⟮Batch job⟯ is r⟮oughly synonymous⟯ to ⟮job⟯, though it ⟮more strongly implies⟯ ⟮the scheduled⟯ and ⟮in the background without intervention⟯ parts, and also the idea of ⟮there being quite a few things to process⟯.
⟮Batch processing⟯ is ⟮processing (batch) jobs⟯.
A ⟮set of jobs to be run together⟯ in ⟮a certain order⟯ is ⟮a job stream⟯.
A ⟮job⟯ in computing ⟮consists of⟯ ⟮one or more tasks/steps⟯.
A ⟮job scheduler⟯ is an application for ⟮controlling⟯ ⟮the scheduling⟯ of ⟮the execution⟯ of ⟮jobs⟯ (which is ⟮unattended⟯, ⟮in the  background⟯).
The ⟮job queue⟯ is ⟮where tasks are put⟯, and is what ⟮the job scheduler manages⟯.

## cron ＆ at

⟮cron⟯ and ⟮at⟯ are ⟮job schedulers⟯ for unix-likes.
⟮cron⟯ is for ⟮scheduling repeated tasks⟯, while ⟮at⟯ is for ⟮scheduling one-time tasks⟯.

### crontab

the ⟮job scheduler cron⟯ is ⟮configured by⟯ ⟮a crontab file⟯.
the ⟮crontab⟯ is interacted with by ⟮the crontab command⟯.


#### syntax

In cron, ⟮each job⟯ is defined by ⟮a line in the crontab⟯, which consists of ⟮times to execute a command⟯, and ⟮a command itself⟯.

```
crontab-line ::= (⟮‹time-specifier› ‹time-specifier› ‹time-specifier› ‹time-specifier› ‹time-specifier›⟯⟮|‹time-keyword›⟯) ⟮‹command›⟯
⟮time-specifier⟯ ::= ⟮* ||⟯ ⟮‹time-list›⟯
⟮time-list⟯ ::= ⟮‹time-item›⟯⟮{,‹time-item›}⟯
⟮time-item⟯ ::= ⟮‹time›-‹time›⟯⟮||(‹time›|*)/‹time›⟯⟮||‹time›⟯
```

#### time specifiers

cron time item|refers to
⟮*⟯|⟮all relevant time units⟯
⟮‹n›-‹m›⟯|⟮specifies a range of times n-m⟯
⟮*/‹n›⟯|⟮every nth unit⟯


*|*|*|*|*|‹command to execute›
⟮c+;s∞;minute (0-59)⟯|⟮c+;s∞;hour (0-23)⟯|⟮c+;s∞;day of month (1-31)⟯|⟮c+;s∞;month (1-12)⟯|⟮c+;s∞;day of week (0-6) (Sunday is 0)⟯


crontab job line example|does
⟮@reboot [command]⟯|⟮every time your computer reboots⟯
⟮30 2 * * * [command]⟯|⟮every day at 2:30 am⟯
⟮15 * * * * [command]⟯|⟮every hour (at :15⟯)
⟮0,10,20 * * * * [command]⟯|⟮every hour at :00, :10, :20⟯
⟮0 5-10 * * * [command]⟯|⟮every day at every hour between 5 and 10⟯
⟮0 0 2 * * [command]⟯|⟮every month on the 2nd at 00:00⟯
⟮0 * * * 1 [command]⟯|⟮every hour, but only on mondays⟯
⟮0 * * * * [command]⟯|⟮every hour (at :00⟯)
⟮*/5 * * * * [command]⟯|⟮12 times an hour (every 5 minutes⟯)
⟮* * * * * [command]⟯|⟮every minute always⟯

#### output

By default, ⟮the output⟯ of ⟮a cron job⟯ gets ⟮sent to your email⟯.
To ⟮change the email⟯ ⟮cron output gets sent to⟯, specify ⟮MAILTO=somemail.⟯
To ⟮change where⟯ cron output ⟮goes⟯, ⟮redirect it as per usual⟯.