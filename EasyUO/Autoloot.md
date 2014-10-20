Autoloot for EasyUO

set %loot DCI_POF_SJG_CUD_IJG_HSF_RVH_FZH_NZH_UJG_FWL_GEJ_FHJ
set %goldContainer LZZHMMD

sub loot
gosub loot
move %1 %2 1
gosub scan
return

sub scan
scan:
scanjournal
gosub checkHP
if Body in #sysmsg
 {
 gosub loot
 return
 goto scan
return



sub loot
set %lootOverTime #scnt + 15
finditem YFM G_3
if #findcnt >= 1
{
 set %body #findid
 set #lobjectid %body
 event macro 17 0
 while #contkind <> ASEB && #contsize <> 144_212 && %lootOverTime > #scnt
 wait 1
 wait 10
  if %lootOverTime <= #scnt
  {
  set %killed %killed + 1
  return
  }
 repeat
  {
   finditem %loot C_ , %body
   if #findcnt >= 1
   {
    exevent drag #findid #findstack
    exevent dropc %goldContainer
    wait 35
   }
  }
 until #findcnt = 0 || %lootOverTime < #scnt
ignoreitem %body 2
}
else
{
repeat
 {
  finditem %loot G_4
   if #findcnt >= 1
   {
    exevent drag #findid #findstack
    exevent dropc %goldContainer
    wait 25
   }
 }
until #findcnt = 0 || %lootOverTime < #scnt
}
return
