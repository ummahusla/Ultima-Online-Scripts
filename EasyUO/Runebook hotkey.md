Recalls to the 1st rune in the runebook

```
set %RuneBook

set %HotKey

set %RuneNumberToBank

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

gosub Instalyze RuneNumberToBank 1

Start:

onhotkey %HotKey

gosub Recall

goto Start:

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

sub Recall

finditem %RuneBook

set #lobjectid #findid

wait1

while #contname <> generic_gump && #contsize <> 577_426

event macro 17 0

wait 5

if #charstatus = G

event macro 6 0

event macro 6 0

wait 1

click %x1 %y1

wait 5

return

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

sub Instalyze

if % . %1 <= 8

set %x . %2 260

else

set %x . %2 420

if % . %1 = 1 || % . %1 = 9

set %y . %2 260

if % . %1 = 2 || % . %1 = 10

set %y . %2 275

if % . %1 = 3 || % . %1 = 11

set %y . %2 290

if % . %1 = 4 || % . %1 = 12

set %y . %2 305

if % . %1 = 5 || % . %1 = 13

set %y . %2 320

if % . %1 = 6 || % . %1 = 14

set %y . %2 335

if % . %1 = 7 || % . %1 = 15

set %y . %2 350

if % . %1 = 8 || % . %1 = 16

set %y . %2 365

return

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
```
