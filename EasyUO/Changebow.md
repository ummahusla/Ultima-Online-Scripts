This script allows you to set 2 bow's id and swap these bows via pressing one button. It's very useful against Luxor's or other top class monsters. I'm using it to drain all stamina from monsters with Dread Bow and after swap with Arian for 3-4 shots. The script will only for for <strong>Archers</strong>

```
;------ BOW ----------
set %bow1 QLQXLMD ; Dread
set %bow2 YLRTLMD ; Arian
set %HotKey f6 ; HotKey Bow 1
set %HotKey2 f7 ; HotKey Bow 2
 
 
 
 
;---------- Set ----------
set %bow TOH
 
Loop:
onhotkey %HotKey
{
gosub bow
}
onhotkey %HotKey2
{
gosub bow2
}
goto Loop
 
sub bow
finditem %bow C_ , #backpackid
set #lobjectID #findid
event macro 17 0
return
 
 
sub bow2
finditem %bow2 C_ , #backpackid
set #lobjectID #findid
event macro 17 0
return
```
