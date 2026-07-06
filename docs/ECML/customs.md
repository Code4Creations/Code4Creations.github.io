# How to create custom missions
## Creating a new mission:
<b>1.</b> Inside the Mods folder, go into the Missions folder.<br>
<b>2.</b> Create a new mission file, name it in any way you want and end it with ".xml".<br>
!!! info "Mission naming syntax"
    Our naming syntax was CM_ for custom missions and GM_ for game missions but you can ignore it.
<b>3.</b> Open the file in your text editor of choice and paste the following template:<br>
```xml title="CM_MissionTemplate.xml"
<?xml version="1.0" encoding="UTF-8"?>
<Mission>
	<MissionID></MissionID>
	<Scene></Scene>
	<RadioMessage></RadioMessage>
	<MissionID2></MissionID2>
	<MissionMarked></MissionMarked>
	<FalseAlarm></FalseAlarm>
	<HasVictim></HasVictim>
	<VictimPanicking></VictimPanicking>
	<VictimState></VictimState>
	<HowInjured></HowInjured>
	<DrunkVictim></DrunkVictim>
	<ShowVictimOnMap></ShowVictimOnMap>
	<HasCuriousNPC></HasCuriousNPC>
	<SuspectDescription></SuspectDescription>
	<NoDetails></NoDetails>
	<HasCriminal></HasCriminal>
	<ChanceToCooperate></ChanceToCooperate>
	<CriminalPanicking></CriminalPanicking>
	<CriminalState></CriminalState>
	<HowInjured2></HowInjured2>
	<DrunkCriminal></DrunkCriminal>
	<HasStolenGoods></HasStolenGoods>
	<HasMeleeWeapon></HasMeleeWeapon>
	<HoldsMeleeWeapon></HoldsMeleeWeapon>
	<HasGun></HasGun>
	<HoldsGun></HoldsGun>
	<WontMove></WontMove>
	<HasDrugs></HasDrugs>
	<IsDrugDealer></IsDrugDealer>
	<IsWanted></IsWanted>
</Mission>
```
<b>4.</b> Fill in the gaps in the xml file based on those tips:
=== "MissionID"
    ID (from the list below) that dictates what kind of crime has been or is beeing commited and at what kind of place (in the game the places are specified by the crime).
    ??? "Mission IDs"
        `0` - none<br>
        `1` - directDrunk<br>
        `2` - directThief<br>
        `3` - directVandalism<br>
        `4` - directAssault<br>
        `5` - directInjuredPerson<br>
        `6` - directAccessory<br>
        `7` - directBurglary<br>
        `8` - directRobbery<br>
        `9` - directDrugPossession<br>
        `10` - directDrugTrafficking<br>
        `11` - directKidnapping<br>
        `12` - directMurder<br>
        `13` - directDrugManufactoring<br>
        `14` - directShoplifting<br>
        `15` - directAccident
=== "Scene"
    The scene in which the crime is able to take place (leave empty if it can happen in every scene).
    ??? "Scenes"
        `MapCenter`<br>
        `MapSouth`<br>
        `MapNorth`<br>
        `MapNorthWest`<br>
        `MapWest`<br>
        `MapEast`<br>
        `MapNorthEast`
=== "RadioMessage"
    The radio message that plays when the mission starts (ID from the list below).
    ??? "Mission IDs"
        `0` - none<br>
        `1` - directDrunk<br>
        `2` - directThief<br>
        `3` - directVandalism<br>
        `4` - directAssault<br>
        `5` - directInjuredPerson<br>
        `6` - directAccessory<br>
        `7` - directBurglary<br>
        `8` - directRobbery<br>
        `9` - directDrugPossession<br>
        `10` - directDrugTrafficking<br>
        `11` - directKidnapping<br>
        `12` - directMurder<br>
        `13` - directDrugManufactoring<br>
        `14` - directShoplifting<br>
        `15` - directAccident
=== "MissionID2"
    ID (from the list below) that dictates what kind of criminal appears at the scene of crime.
    ??? "Mission IDs"
        `0` - none<br>
        `1` - directDrunk<br>
        `2` - directThief<br>
        `3` - directVandalism<br>
        `4` - directAssault<br>
        `5` - directInjuredPerson<br>
        `6` - directAccessory<br>
        `7` - directBurglary<br>
        `8` - directRobbery<br>
        `9` - directDrugPossession<br>
        `10` - directDrugTrafficking<br>
        `11` - directKidnapping<br>
        `12` - directMurder<br>
        `13` - directDrugManufactoring<br>
        `14` - directShoplifting<br>
        `15` - directAccident
=== "MissionMarked"
    `true` or `false` (should the mission be marked on the map and in the world).
=== "FalseAlarm"
    `true` or `false` (is mission a false alarm, false alarm missions make you just check out the place).
=== "HasVictim"
    `true` or `false` (self explanatory).
=== "VictimPanicking"
    `true` or `false` (panicking victims run away on sight).
=== "VictimState"
    The state of the victim when seen (pick on from the list below).
    ??? "NPC States"
        `0` - none<br>
        `1` - _Criminal_SetOnTheLoose();<br>
        `2` - _Criminal_SetRunAwayFromVictim();<br>
        `3` - _Criminal_StartRobbingVictim();<br>
        `4` - _SetDEAD();<br>
        `5` - _SetINCAPACITATED();<br>
        `6` - _SetINJURED(-1f);<br>
        `7` - _Victim_SetWithFear();<br>
        `8` - _Victim_StartToBeenRobbed();<br>
        `9` - _Victim_StartToKeepStanding();
=== "HowInjured"
    If the state is injured, how injured (how much HP does the Victim have).
=== "DrunkVictim"
    `true` or `false` (self explanatory).
=== "ShowVictimOnMap"
    `true` or `false` (should the victim appear on the minimap).
=== "HasCuriousNPC"
    `true` or `false` (curious NPCs have info about the crime - SuspectDescription).
=== "SuspectDescription"
    Self explanatory.
=== "NoDetails"
    `true` or `false` (dictates whether the suspect has a description).
=== "HasCriminal"
    `true` or `false` (self explanatory).
=== "ChanceToCooperate"
    `0` - `100` the chance (percentage) for the criminal to cooperate with police.
=== "CriminalPanicking"
    `true` or `false` (panicking criminals run away on sight).
=== "CriminalState"
    The state of the criminal when seen (pick on from the list below).
    ??? "NPC States"
        `0` - none<br>
        `1` - _Criminal_SetOnTheLoose();<br>
        `2` - _Criminal_SetRunAwayFromVictim();<br>
        `3` - _Criminal_StartRobbingVictim();<br>
        `4` - _SetDEAD();<br>
        `5` - _SetINCAPACITATED();<br>
        `6` - _SetINJURED(-1f);<br>
        `7` - _Victim_SetWithFear();<br>
        `8` - _Victim_StartToBeenRobbed();<br>
        `9` - _Victim_StartToKeepStanding();
=== "HowInjured2"
    If the state is injured, how injured (how much HP does the Criminal have).
!!! warning "From DrunkCriminal to IsWanted"
    All of these are self explanatory `true` or `false`.
<b>5.</b> Save the file if it looks like the example on the following page and have fun playing the game with your custom mission loaded!