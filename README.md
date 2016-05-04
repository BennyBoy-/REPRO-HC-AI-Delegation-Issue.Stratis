Step to do it.
 
Make sure you have HC connected.
 
Join the game and using scroll wheel click on "Create AI Units on HC", this will spawn a 7 units group in front of the player (the group is first created on the server, then the units are created on the HC)

Wait a bit after the creation (~5-10sec) and pick one of the following action:
- DELETE HC AI Units from the Server (Last Group)
- DELETE HC AI Units from the Server (All Group)

Since the problem is random, you may want to do it a few time

You will see that some AI will stay on map and using ASM you will see that they are not on Server or HC. (They are ghosts)

From the logs perspective:

[HC AI Creation]

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
10:35:35 "REPRO(Headless Client:REPRO_HC_AI_DelegationDoCreate.sqf) HC [HC2_1] with id [4] is about to create units for group [R Delta 2-2]"
10:35:35 "REPRO(Headless Client:REPRO_HC_AI_DelegationDoCreate.sqf) HC [HC2_1] with id [4] has created AI unit [R Delta 2-2:1] in group [R Delta 2-2]"
10:35:35 "REPRO(Headless Client:REPRO_HC_AI_DelegationDoCreate.sqf) HC [HC2_1] with id [4] has created AI unit [R Delta 2-2:2] in group [R Delta 2-2]"
10:35:35 "REPRO(Headless Client:REPRO_HC_AI_DelegationDoCreate.sqf) HC [HC2_1] with id [4] has created AI unit [R Delta 2-2:3] in group [R Delta 2-2]"
10:35:35 soldier[I_Soldier_AR_F]:Some of magazines weren't stored in soldier Vest or Uniform?
10:35:35 "REPRO(Headless Client:REPRO_HC_AI_DelegationDoCreate.sqf) HC [HC2_1] with id [4] has created AI unit [R Delta 2-2:4] in group [R Delta 2-2]"
10:35:35 soldier[I_Soldier_LAT_F]:Some of magazines weren't stored in soldier Vest or Uniform?
10:35:35 soldier[I_Soldier_LAT_F]:Some of magazines weren't stored in soldier Vest or Uniform?
10:35:35 "REPRO(Headless Client:REPRO_HC_AI_DelegationDoCreate.sqf) HC [HC2_1] with id [4] has created AI unit [R Delta 2-2:5] in group [R Delta 2-2]"
10:35:35 soldier[I_Soldier_GL_F]:Some of magazines weren't stored in soldier Vest or Uniform?
10:35:35 "REPRO(Headless Client:REPRO_HC_AI_DelegationDoCreate.sqf) HC [HC2_1] with id [4] has created AI unit [R Delta 2-2:6] in group [R Delta 2-2]"
10:35:35 "REPRO(Headless Client:REPRO_HC_AI_DelegationDoCreate.sqf) HC [HC2_1] with id [4] has created AI unit [R Delta 2-2:7] in group [R Delta 2-2]"
10:35:35 "REPRO(Headless Client:REPRO_HC_AI_DelegationDoCreate.sqf) HC [HC2_1] with id [4] has created [7] units in group [R Delta 2-2]"
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

[SERVER AI DELETE]
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
10:35:40 "REPRO(Server:REPRO_SRV_AI_DelegationDelete): Removing units from [Server] with parameter [LastGroup]"
10:35:40 "REPRO(Server:REPRO_SRV_AI_DelegationCreate.sqf) About to remove units from group [R Delta 2-2], group is local -> [false], units left -> [1]"
10:35:40 "REPRO(Server:REPRO_SRV_AI_DelegationCreate.sqf) Removing unit [R Delta 2-2:1 REMOTE] from group [R Delta 2-2] via deleteVehicle, unit is local -> [false]"
10:35:40 "REPRO(Server:REPRO_SRV_AI_DelegationCreate.sqf) Checking for unit removal in group [R Delta 2-2], result is [R Delta 2-2:1 REMOTE]"
10:35:40 "REPRO(Server:REPRO_SRV_AI_DelegationCreate.sqf) About to remove group [R Delta 2-2] via deleteGroup, units left -> [1]"
10:35:40 "REPRO(Server:REPRO_SRV_AI_DelegationCreate.sqf) Checking for group removal [R Delta 2-2]"
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Notice that the HC "count units group" returns 7 members while the server is only aware of 1 member before the removal. 6 members got "lost"
