# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

## 2026-10-31 14:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
-        -- Nur diese ESX-Jobs dürfen den Reparaturkasten nutzen
-        AllowedJobs = {
-            police = true,
-            ambulance = true,
-            mechanic = true,
-        },
+        -- Keine Job-Beschränkung - jeder darf den Reparaturkasten nutzen
+        AllowedJobs = false,
```

## 2026-10-31 12:23 Uhr
**+0** neu · **~5** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_minijobs/client/admin.lua`
```diff
-                        TR.PutObjectOnGround(obj, coords.z)
+                        local gz = TR.FindGroundZ(coords.x, coords.y, coords.z, 200) or coords.z
+                        TR.PutObjectOnGround(obj, gz)
-        { type = 'input', label = 'Name', default = 'Downtown Müll', required = true },
+    local jobType = input[1]
+    local spec = JobTypes.Get(jobType)
+    local autoName = ('Minijob - %s'):format(spec and spec.label or jobType)
+
-        label = input[1],
-        type = input[2],
```
`~ resources/[selfcode]/rmc_minijobs/client/main.lua`
```diff
+    PlaceObjectOnGroundProperly(entity)
+    local finalCoords = GetEntityCoords(entity)
+    SetEntityCoordsNoOffset(entity, finalCoords.x, finalCoords.y, finalCoords.z, false, false, false)
```
`~ resources/[selfcode]/rmc_minijobs/client/placement.lua`
```diff
-        local obj = CreateObjectNoOffset(model, coords.x, coords.y, coords.z, false, false, false)
+        local gz = TR.FindGroundZ(coords.x, coords.y, coords.z, 200) or coords.z
+        local lift = TR.ModelBottomOffset(model)
+        local obj = CreateObjectNoOffset(model, coords.x, coords.y, gz + lift, false, false, false)
+
+            local coords = GetEntityCoords(ghost)
+            local arrowZ = coords.z + 2.5
+            DrawMarker(42, coords.x, coords.y, arrowZ, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.5, 0.5, 0.5, 255, 165, 0, 200, false, false, 2, false, nil, nil, false)
-        else
-            DrawMarker(1, hit.x, hit.y, gz - 0.95, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.7, 0.7, 0.28, 40, 140, 255, 160, false, false, 2, false, nil, nil, false)
```
`~ resources/[selfcode]/rmc_minijobs/client/runner.lua`
```diff
+local plantMarkers = {}
+    plantMarkers = {}
-    if asg.ready then
-        local job = Utils.FindMinijob(asg.jobId)
-        if job and job.company and Utils.HasCoords(job.company.coords) then
-            addPointBlip({ coords = job.company.coords, label = 'Zentrale' }, spec, true)
-        end
-    end
-    exports.ox_target:addLocalEntity(entity, {
-        {
```
`~ resources/[selfcode]/rmc_minijobs/shared/types.lua`
```diff
-            prop = { model = `prop_wateringcan`, bone = 28422, pos = vec3(0.0, 0.0, 0.0), rot = vec3(0.0, 0.0, 0.0) },
+            prop = { model = `prop_wateringcan`, bone = 28422, pos = vec3(0.05, 0.0, -0.05), rot = vec3(0.0, 0.0, 90.0) },
```

## 2026-10-31 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-30T23:00:48Z","categoryId":"1551161549018759170","webhooks":{"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284","channelId":"1551520126367572008"},"basicneeds":{"url":"https://discord.com/api/webhooks/15529719318
+{"categoryId":"1551161549018759170","webhooks":{"me":{"channelId":"1513950191936344245","url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490"},"adminjail":{"channelId":"1551161575690211428","url":"https://discord.com/api/webhooks/1551161578009796630/***"
```

## 2026-10-31 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"staff":{"channelId":"1552971120460828763","webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***"},"sperrzone":{"channelId":"1552971110457286766","webhookId":"1552971115209564220","url":"https://discord.com/
+{"updatedAt":"2026-10-30T23:00:48Z","categoryId":"1551161549018759170","webhooks":{"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284","channelId":"1551520126367572008"},"basicneeds":{"url":"https://discord.com/api/webhooks/15529719318
```

## 2026-10-30 22:23 Uhr
**+4** neu · **~0** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_test_trash/Lang.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_test_trash/client/client.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_test_trash/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_test_trash/fxmanifest.lua`
```diff
+ Neue Datei
```

## 2026-10-30 21:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "id": 11,
-            "backupFile": "banlist_20_30_25_10_2026.json",
-            "backupDate": "20_30_25_10_2026",
-            "backupTimestamp": 1792956644
-        },
-        {
-            "id": 11,
-            "backupFile": "banlist_20_32_25_10_2026.json",
-            "backupDate": "20_32_25_10_2026",
-            "backupTimestamp": 1792956769
```

## 2026-10-30 20:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/sits.json`
```diff
-[{"id":"sit_1791572244_8861","label":"Sit Chair 4","anim":"base","dict":"timetable@ron@ig_3_couch","y":-420.7482,"x":1225.8873,"h":255.6565,"z":68.0417},{"id":"sit_1791572300_6917","label":"Sit Chair 2","anim":"ig_5_p3_base","dict":"timetable@ron@ig_5_p3","y":-419.3795,"x":1226.4694,"h":271.1957,"z
+[{"x":1225.8873,"id":"sit_1791572244_8861","z":68.0417,"label":"Sit Chair 4","dict":"timetable@ron@ig_3_couch","anim":"base","h":255.6565,"y":-420.7482},{"x":1226.4694,"id":"sit_1791572300_6917","z":68.0817,"label":"Sit Chair 2","dict":"timetable@ron@ig_5_p3","anim":"ig_5_p3_base","h":271.1957,"y":
```

## 2026-10-30 18:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c": [
+    "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5": [
-            "receiver_identifier": "cd_garage",
-            "receiver_name": "cd_garage",
-            "sender_name": "Timo Anderson",
+            "receiver_identifier": "bank",
+            "sender_name": "Bonnie Parker",
+            "reason": "Auszahlung vom Bankkonto",
+            "type": "withdraw",
+            "date": "2026/10/28 - 01:26:09",
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-30T09:01:24Z","categoryId":"1551161549018759170","webhooks":{"esx_resources":{"channelId":"1557386346782265425","url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076"},"join":{"channelId":"1448120760391565352","url":"https://discord.
+{"categoryId":"1551161549018759170","webhooks":{"staff":{"channelId":"1552971120460828763","webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***"},"sperrzone":{"channelId":"1552971110457286766","webhookId":"1552971115209564220","url":"https://discord.com/
```

## 2026-10-30 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"chopshop":{"webhookId":"1552971074814218312","channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***"},"esx_test":{"webhookId":"1557386332483887194","channelId":"1557386329686413342","url":"https://discord.co
+{"updatedAt":"2026-10-30T09:01:24Z","categoryId":"1551161549018759170","webhooks":{"esx_resources":{"channelId":"1557386346782265425","url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076"},"join":{"channelId":"1448120760391565352","url":"https://discord.
```

## 2026-10-30 01:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "receiver_identifier": "bank",
+            "receiver_name": "Geldbörse",
+            "sender_name": "Akio Kuroda",
+            "type": "withdraw",
+            "reason": "Auszahlung vom Bankkonto",
+            "sender_identifier": "char3:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "value": 10000,
+            "date": "2026/10/30 - 00:24:57"
+        },
```

## 2026-10-29 23:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-            "sender_name": "Timo Anderson",
-            "reason": "Fahrzeugrückgabegebühr",
-            "value": 500,
-            "sender_identifier": "char2:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "sender_name": "Timo Anderson",
+            "reason": "Fahrzeugrückgabegebühr",
+            "sender_identifier": "char2:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "value": 500,
-            "sender_name": "Timo Anderson",
-            "reason": "Fahrzeugrückgabegebühr",
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046","channelId":"155297109931721
+{"categoryId":"1551161549018759170","webhooks":{"chopshop":{"webhookId":"1552971074814218312","channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***"},"esx_test":{"webhookId":"1557386332483887194","channelId":"1557386329686413342","url":"https://discord.co
```

## 2026-10-29 21:22 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupFile": "banlist_21_27_24_10_2026.json",
-            "backupDate": "21_27_24_10_2026",
-            "backupTimestamp": 1792870043
-        },
-        {
-            "backupFile": "banlist_21_29_24_10_2026.json",
-            "backupDate": "21_29_24_10_2026",
-            "id": 11,
-            "backupTimestamp": 1792870168
-        },
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9": [
-        {
-            "receiver_name": "cd_garage",
-            "receiver_identifier": "cd_garage",
-            "reason": "Fahrzeugrückgabegebühr",
-            "sender_name": "Jayden Anderson",
-            "date": "2026/09/16 - 20:15:27",
-            "value": 500,
-            "type": "withdraw",
-            "sender_identifier": "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9"
```

## 2026-10-29 18:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c": [
+    "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9": [
-            "value": 500,
-            "date": "2026/10/06 - 21:19:34",
+            "receiver_identifier": "cd_garage",
+            "sender_name": "Jayden Anderson",
+            "date": "2026/09/16 - 20:15:27",
+            "value": 500,
+            "type": "withdraw",
+            "sender_identifier": "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9"
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357
+{"webhooks":{"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046","channelId":"155297109931721
```

## 2026-10-29 13:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-29T09:00:48Z","webhooks":{"default":{"channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269"},"afk":{"channelId":"1512475286229356617","url":"https://discord.com/api
+{"categoryId":"1551161549018759170","webhooks":{"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357
```

## 2026-10-29 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"ausbluten":{"webhookId":"1552971079239077968","url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200"},"afk":{"webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617"
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-29T09:00:48Z","webhooks":{"default":{"channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269"},"afk":{"channelId":"1512475286229356617","url":"https://discord.com/api
```

## 2026-10-29 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","channelId":"1552971103910236172","webhookId":"1552971107500433498"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068","webhookId":"1471556835994767400"},"
+{"webhooks":{"ausbluten":{"webhookId":"1552971079239077968","url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200"},"afk":{"webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617"
```

## 2026-10-28 21:22 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
+            "backupFile": "banlist_21_27_24_10_2026.json",
+            "backupDate": "21_27_24_10_2026",
-            "backupFile": "banlist_21_23_23_10_2026.json",
-            "backupTimestamp": 1792783401,
-            "backupDate": "21_23_23_10_2026"
+            "backupTimestamp": 1792870043
+            "backupFile": "banlist_21_29_24_10_2026.json",
+            "backupDate": "21_29_24_10_2026",
-            "backupFile": "banlist_21_25_23_10_2026.json",
-            "backupTimestamp": 1792783526,
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9": [
-        {
-            "sender_identifier": "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9",
-            "sender_name": "Jayden Anderson",
-            "date": "2026/09/16 - 20:15:27",
-            "type": "withdraw",
-            "receiver_name": "cd_garage",
-            "value": 500,
-            "receiver_identifier": "cd_garage",
-            "reason": "Fahrzeugrückgabegebühr"
```

## 2026-10-28 18:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-28T15:51:19Z","webhooks":{"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***"
+{"webhooks":{"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","channelId":"1552971103910236172","webhookId":"1552971107500433498"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068","webhookId":"1471556835994767400"},"
```

## 2026-10-28 17:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-28T09:01:09Z","categoryId":"1551161549018759170","webhooks":{"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-28T15:51:19Z","webhooks":{"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***"
```

## 2026-10-28 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-27T23:00:55Z","webhooks":{"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653
+{"updatedAt":"2026-10-28T09:01:09Z","categoryId":"1551161549018759170","webhooks":{"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***
```

## 2026-10-28 02:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "sender_identifier": "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5",
+            "sender_name": "Bonnie Parker",
+            "date": "2026/10/28 - 01:26:09",
+            "receiver_name": "Geldbörse",
+            "receiver_identifier": "bank",
+            "value": 5000,
+            "type": "withdraw",
+            "reason": "Auszahlung vom Bankkonto"
+        },
```

## 2026-10-28 01:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char4:ed00a18aa373b82fda2a51a5f23d0c0567f13db9": [
+    "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9": [
-            "value": 21200,
-            "receiver_name": "Bank (Kreditablösung)",
+            "sender_identifier": "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9",
+            "sender_name": "Jayden Anderson",
+            "date": "2026/09/16 - 20:15:27",
+            "type": "withdraw",
+            "receiver_name": "cd_garage",
+            "value": 500,
```

## 2026-10-28 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-27T17:00:46Z","categoryId":"1551161549018759170","webhooks":{"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552","channelId":"1448120760391565352"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***",
+{"updatedAt":"2026-10-27T23:00:55Z","webhooks":{"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653
```

## 2026-10-27 22:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "value": 300,
+            "receiver_name": "Bank (Kartenkauf)",
+            "date": "2026/10/27 - 22:01:14",
+            "sender_identifier": "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5",
+            "sender_name": "Bonnie Parker",
+            "reason": "Kartenkauf: Gold Card",
+            "type": "card_purchase",
+            "receiver_identifier": "bank"
+        },
```

## 2026-10-27 21:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1793043395,
-            "backupFile": "banlist_21_20_22_10_2026.json",
-            "backupDate": "21_20_22_10_2026",
-            "backupTimestamp": 1792696848
+            "backupFile": "banlist_21_23_23_10_2026.json",
+            "backupTimestamp": 1792783401,
+            "backupDate": "21_23_23_10_2026"
-            "backupFile": "banlist_21_22_22_10_2026.json",
-            "backupDate": "21_22_22_10_2026",
-            "backupTimestamp": 1792696973
```

## 2026-10-27 19:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "value": 1000,
+            "receiver_name": "Geldbörse",
+            "date": "2026/10/27 - 19:11:10",
+            "sender_identifier": "char3:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "sender_name": "Cole Maddox",
+            "reason": "Auszahlung vom Bankkonto",
+            "type": "withdraw",
+            "receiver_identifier": "bank"
+        },
```

## 2026-10-27 18:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char4:dcdd8750773c33c2ce3ff658853fe0c909367dba": [
-        {
-            "sender_name": "Dr. Vincent Fischer",
-            "receiver_name": "cd_garage",
-            "sender_identifier": "char4:dcdd8750773c33c2ce3ff658853fe0c909367dba",
-            "reason": "Fahrzeugrückgabegebühr",
-            "type": "withdraw",
-            "date": "2026/10/18 - 18:10:21",
-            "receiver_identifier": "cd_garage",
-            "value": 500
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-27T09:00:34Z","webhooks":{"faction":{"channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652"},"support":{"channelId":"1552971099317211136","url":"https://discord.com/api/webhooks/1552971101741654046/*
+{"updatedAt":"2026-10-27T17:00:46Z","categoryId":"1551161549018759170","webhooks":{"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552","channelId":"1448120760391565352"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***",
```

## 2026-10-27 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"lager":{"webhookId":"1551161582942158879","channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***"},"chopshop":{"webhookId":"1552971074814218312","channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***
+{"updatedAt":"2026-10-27T09:00:34Z","webhooks":{"faction":{"channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652"},"support":{"channelId":"1552971099317211136","url":"https://discord.com/api/webhooks/1552971101741654046/*
```

## 2026-10-27 06:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"lager":{"webhookId":"1551161582942158879","url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455"},"default":{"webhookId":"1551161552537653269","url":"https://discord.com/api/webhooks/1551161552537653269/***","channelId":"1551161550096699392"
+{"webhooks":{"lager":{"webhookId":"1551161582942158879","channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***"},"chopshop":{"webhookId":"1552971074814218312","channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***
```

## 2026-10-27 02:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char4:95e98569cca18ee079f5fe27ab54152ede42f277": [
+    "char4:dcdd8750773c33c2ce3ff658853fe0c909367dba": [
+        {
+            "sender_name": "Dr. Vincent Fischer",
+            "receiver_name": "cd_garage",
+            "sender_identifier": "char4:dcdd8750773c33c2ce3ff658853fe0c909367dba",
+            "reason": "Fahrzeugrückgabegebühr",
+            "type": "withdraw",
+            "date": "2026/10/18 - 18:10:21",
+            "receiver_identifier": "cd_garage",
```
