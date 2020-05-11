# esx_wanted
 
Police wanted With DISCORD and GCPHONE records.

# Video:
[![Wanted](https://i.imgur.com/kocnx1B.png)](https://www.youtube.com/watch?v=xNXcUa15gng)

### Requirements
* Police Job
  * [esx_policejob](https://github.com/ESX-Org/esx_policejob)
  
## Download & Installation
### Manually
- Download https://github.com/Ivannnmmn/esx_wanted
- Put it in the `[esx]` directory

## Installation
- Add this to your server.cfg:
```
start esx_wanted
```
- Change `Config`
- Add SQL

## Command
- `/wanted [ID] [Time] [Reason]` Add Wanted
- `/unwanted [ID]` UnWanted

## Add to esx_policejob
![Image](https://i.imgur.com/UEdxmbC.png)
- esx_policejob > client > main
```LUA
	ESX.UI.Menu.Open('default', GetCurrentResourceName(), 'police_actions', {
			title    = 'Police',
			align    = 'top-left',
			elements = {
				{label = _U('citizen_interaction'), value = 'citizen_interaction'},
				{label = _U('vehicle_interaction'), value = 'vehicle_interaction'},
				{label = _U('object_spawner'), value = 'object_spawner'},
				{label = "Wanted",               value = 'wanted_menu'}  -- This
		}}, function(data, menu)
			if data.current.value == 'wanted_menu' then		-- This
				TriggerEvent("esx_wanted:openWantedMenu")
			end												-- end
			if data.current.value == 'citizen_interaction' then
				local elements = {
					{label = _U('id_card'), value = 'identity_card'},
					{label = _U('search'), value = 'search'},
					{label = _U('handcuff'), value = 'handcuff'},
```