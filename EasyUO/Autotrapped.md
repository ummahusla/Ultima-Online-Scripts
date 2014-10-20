Automatically use trapped when you are frozen.

```
AutoTraped:
scanjournal 1
If Frozen in #journal : notin #journal
{
msg $.usetraped$
deletejournal
wait 5
}
Goto AutoTraped
```
