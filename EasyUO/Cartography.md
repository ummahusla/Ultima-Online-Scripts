Cartohraphy script for EasyUO
```
scanjournal
_Cartography:
finditem XVH C_ , #backpackid
if #findcnt = 0
halt
set #lobjectid #findid
event macro 17 0
wait 10
gosub check
goto _Cartography

sub check
set %lag1 #scnt + 10
_check:
if #contname = objpicker_gump
{
gosub make
return
}
if #contname = Course_gump
{
gosub drop
return
}
if #scnt > %lag1
{
click 63 60 d
return
}
wait 10
goto _check
return

sub make
contpos 0 0
click 63 60 d
wait 20
set %lag2 #scnt + 10
deletejournal
_scan:
for %i 1 5
{
scanjournal %i
if you_put in #journal || unusable_map in #journal
return
if #scnt > %lag2
{
click 63 60 d
return
}
}
goto _scan
return

sub drop
_drop:
finditem #lobjectid C_ , #backpackid
if #findcnt = 0
return
exevent drag #findid #findstack
exevent dropg #charposx #charposy #charposz
wait 15
goto _drop
return
```
