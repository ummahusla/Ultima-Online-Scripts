Automatically start healing yourself with bandages if your health is lower then 100%. You can use this script for EasyUO.

```
Autoheal:
If #Hits < #Maxhits
Gosub Heal
Goto Autoheal
sub Heal
Set %TargetAntiLag #Scnt2 + 10
deletejournal
spook:
msg $.usebandage$
while #targcurs <> 1
{
wait 1

If %TargetAntiLag <= #scnt2
return
}
Scanjournal
if where_do_you_want_to_use in #journal && : notin #journal && event notin #journal
{
event macro 23 0
goto heal
}
goto spook
heal:
Set %HealTime #scnt2 + 40
deletejournal
Repeat
{
Scanjournal
If You_put_the_bloody in #journal && : notin #journal && event notin #journal
return
If You_fail in #journal && : notin #journal && event notin #journal
return
If cured in #journal && : notin #journal && event notin #journal
return
If You_gain in #journal && : notin #journal && event notin #journal
return
wait 5
}
until %HealTime <= #scnt2
Return
```
