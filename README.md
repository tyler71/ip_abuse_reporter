#### ip_abuse_reporter
Looks up whois abuse email and sends abuse report for list of ip addresses

List can be specified as the only argument or with -f
It should be a single list of ip addresses associated with some kind of spam

```
$ cat spam_list
109.174.xxx.xxx
109.184.xxx.xxx
109.71.xxx.xxx
109.95.xxx.xxx
115.249.xxx.xxx
```

```
$ ./ip_abuse_reporter -f spam_list
Reported abuse-mailbox@xxx.ru - 109.188.xxx.xxx 109.188.xxx.xxx 109.188.xxx.xxx
Reported abuse@xxx.ru - 109.174.xxx.xxx
Reported abuse@xxx.ru - 109.184.xxx.xxx
Reported abuse@xxx.net - 109.71.xxx.xxx 
Reported abuse@xxx.ru - 109.95.xxx.xxx
Reported abuse@xxx.com - 115.249.xxx.xxx
```

Dry run will not send emails but provide list of which ipaddresses will be sent to what email
```
$ ./ip_abuse_reporter -d -f spam_list
Will email abuse-mailbox@xxx.ru - 109.188.xxx.xxx 109.188.xxx.xxx 109.188.xxx.xxx
Will email abuse@xxx.ru - 109.174.xxx.xxx
Will email abuse@xxx.ru - 109.184.xxx.xxx
Will email abuse@xxx.net - 109.71.xxx.xxx 
Will email abuse@xxx.ru - 109.95.xxx.xxx
Will email abuse@xxx.com - 115.249.xxx.xxx
```
