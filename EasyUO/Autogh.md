Automatically drinks Greater Heal if your health drops lower then 90 HP. You can change 90 HP variable to what ever you want.

```
if #HITS =< 90
{
msg $.drink heal$
wait 10
set 0 #scnt + %HpotionTime
goto AutoGH
}
```
