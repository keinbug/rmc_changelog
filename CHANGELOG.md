# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

## 2026-10-26 23:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:726b2e82f8613191a738a5158a2b2cd5c7dbeea1": [
+    "char4:95e98569cca18ee079f5fe27ab54152ede42f277": [
-            "type": "interest_savings",
-            "reason": "Savings account interest payment (Period 27)",
-            "value": 3,
-            "receiver_identifier": "char2:726b2e82f8613191a738a5158a2b2cd5c7dbeea1",
+            "date": "2026/10/25 - 02:44:47",
+            "reason": "Savings account interest payment (Period 41)",
-            "date": "2026/07/05 - 09:20:38"
-        },
```

## 2026-10-26 21:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1792956769,
+    "lastBackup": 1793043395,
-            "backupTimestamp": 1792610209,
-            "backupFile": "banlist_21_16_21_10_2026.json",
-            "backupDate": "21_16_21_10_2026",
-            "id": 11
-        },
-        {
-            "backupTimestamp": 1792610334,
-            "backupFile": "banlist_21_18_21_10_2026.json",
```

## 2026-10-26 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"faction":{"webhookId":"1551161573194731652","channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"default":{"webhookId":"1551161552537653269","channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/**
+{"categoryId":"1551161549018759170","webhooks":{"me":{"webhookId":"1513950212480307490","channelId":"1513950191936344245","url":"https://discord.com/api/webhooks/1513950212480307490/***"},"adminjail":{"webhookId":"1551161578009796630","channelId":"1551161575690211428","url":"https://discord.com/api
```

## 2026-10-26 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-25T23:01:05Z","webhooks":{"poster":{"url":"https://discord.com/api/webhooks/1560007815156998144/***","webhookId":"1560007815156998144","channelId":"1560007812342489120"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"155298982621361771
+{"webhooks":{"faction":{"webhookId":"1551161573194731652","channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"default":{"webhookId":"1551161552537653269","channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/**
```

## 2026-10-26 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-25T17:00:55Z","categoryId":"1551161549018759170","webhooks":{"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200","webhookId":"1552971079239077968"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/**
+{"updatedAt":"2026-10-25T23:01:05Z","webhooks":{"poster":{"url":"https://discord.com/api/webhooks/1560007815156998144/***","webhookId":"1560007815156998144","channelId":"1560007812342489120"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"155298982621361771
```

## 2026-10-25 21:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1792870168,
+    "lastBackup": 1792956769,
-            "backupFile": "banlist_21_12_20_10_2026.json",
-            "backupTimestamp": 1792523567,
-            "id": 11,
-            "backupDate": "21_12_20_10_2026"
-        },
-        {
-            "backupFile": "banlist_21_14_20_10_2026.json",
-            "backupTimestamp": 1792523692,
```

## 2026-10-25 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-25T13:45:11Z","webhooks":{"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"poster":{"url":"https://discord.com/api/webhooks/1560007815156998144/***","channelId":"156000781234248
+{"updatedAt":"2026-10-25T17:00:55Z","categoryId":"1551161549018759170","webhooks":{"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200","webhookId":"1552971079239077968"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/**
```

## 2026-10-25 15:22 Uhr
**+0** neu · **~4** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/client/nitro.lua`
```diff
-      * Effekte nur für Fahrzeuge in der Nähe (RenderDistance / MaxVehicles), idle = Wait(500)
+      * Effekte nur für Fahrzeuge in der Nähe (RenderDistance / MaxVehicles), idle = kein Thread (nur State-Bag-Event)
+local ESX = exports['es_extended']:getSharedObject()
+local function notify(msg, typ) ESX.ShowNotification(msg, typ or 'info') end
+local tracked = {}  -- [veh] = { data, flames, sound, started, pts }
-        lib.notify({ title = 'Nitro', description = T.NoVehicle, type = 'error' })
+        notify(T.NoVehicle, 'error')
-        lib.notify({ title = 'Nitro', description = T.Blocked, type = 'error' })
+        notify(T.Blocked, 'error')
-        lib.notify({ title = 'Nitro', description = T.Empty, type = 'error' })
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
-    RefillNeedsDriver = true,
+    -- Einbau an der Motorhaube (nicht im Fahrzeug)
+    Install = {
+        HoodDistance = 1.6,            -- max. Abstand zum Motorhaube-Bone
+        SearchRadius = 6.0,            -- Fahrzeug-Suche um den Spieler
+        Duration     = 8000,           -- ms Einbau-Dauer
+        AnimDict     = 'mini@repair',
+        AnimName     = 'fixing_a_player',
+    },
+        TrailFade      = 500,          -- ms Ausblenden der Rücklicht-Spur nach dem Boost
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-25T13:14:19Z","webhooks":{"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374","webhookId":"1557386364578955274"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777
+{"updatedAt":"2026-10-25T13:45:11Z","webhooks":{"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"poster":{"url":"https://discord.com/api/webhooks/1560007815156998144/***","channelId":"156000781234248
```
`~ resources/[selfcode]/rmc_core/server/nitro.lua`
```diff
-    TriggerClientEvent('ox_lib:notify', src, { title = 'Nitro', description = msg, type = typ or 'inform' })
+    local xPlayer = ESX.GetPlayerFromId(src)
+    if xPlayer then xPlayer.showNotification(msg, (typ == nil or typ == 'inform') and 'info' or typ) end
-for item, amount in pairs(Cfg.RefillItems or {}) do
+-- Einbau per Item: nur zu Fuß an der Motorhaube (Client macht Animation, Server prüft + bucht ab)
+local installing = {}  -- [src] = item
+
+for item in pairs(Cfg.RefillItems or {}) do
-        local veh = Cfg.RefillNeedsDriver and getDriverVehicle(src) or GetVehiclePedIsIn(ped, false)
-        if not veh or veh == 0 then return notify(src, T.NoVehicle, 'error') end
```

## 2026-10-25 14:23 Uhr
**+3** neu · **~3** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_core/client/nitro.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/html/nitro/nitro.ogg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/server/nitro.lua`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+
+-- ============================================
+-- NITRO SYSTEM (client/nitro.lua + server/nitro.lua)
+-- erstellt von Sebbi | KeinBug
+-- Tank pro Fahrzeug (State Bag), Auffüllen per Item, Farben per /nitro
+-- ============================================
+Config.Nitro = {
+    Enabled        = true,
+    Debug          = false,
+
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-25T09:00:45Z","webhooks":{"esx_resources":{"channelId":"1557386346782265425","webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"esx_paycheck":{"channelId":"1557386352226598913","webhookId":"15
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-25T13:14:19Z","webhooks":{"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374","webhookId":"1557386364578955274"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777
```
`~ resources/[selfcode]/rmc_core/fxmanifest.lua`
```diff
-    'data/sits.json',
+    'data/sits.json',
+    'html/nitro/nitro.ogg',
```

## 2026-10-25 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-25T01:45:01Z","categoryId":"1551161549018759170","webhooks":{"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252","webhookId":"1557386342755991582"},"willkommen":{"url":"https://discord.com/api/webhooks/155116159
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-25T09:00:45Z","webhooks":{"esx_resources":{"channelId":"1557386346782265425","webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"esx_paycheck":{"channelId":"1557386352226598913","webhookId":"15
```

## 2026-10-25 03:22 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c": [
-        {
-            "reason": "Fahrzeugrückgabegebühr",
-            "date": "2026/10/19 - 16:25:37",
-            "receiver_name": "cd_garage",
-            "value": 500,
-            "sender_name": "Misaki Lee",
-            "receiver_identifier": "cd_garage",
-            "sender_identifier": "char1:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
-            "type": "withdraw"
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"faction":{"channelId":"1551161570439208960","webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"esx_useractions":{"channelId":"1557386339866120252","webhookId":"1557386342755991582","url":"https://disc
+{"updatedAt":"2026-10-25T01:45:01Z","categoryId":"1551161549018759170","webhooks":{"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252","webhookId":"1557386342755991582"},"willkommen":{"url":"https://discord.com/api/webhooks/155116159
```

## 2026-10-25 02:23 Uhr
**+0** neu · **~0** geändert · **-187** gelöscht
`− resources/[oresmon]/rm_hackerv/.fxap`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/client/client.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/client/custom_hack.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/client/dispatch.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/client/functions.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/client/hacks.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/html/ui.html`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/server/data.json`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/server/server.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/shared/cfg.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/shared/language.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/shared/utils.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/stream/hacker_v.ytd`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/stream/prop_ig_phone1.ytd`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_hackerv/stream/prop_police_phone.ydr`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_stream/.fxap`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_stream/client.lua`
```diff
- Gelöscht
```
`− resources/[oresmon]/rm_stream/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/.fxap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/_manifest.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/mlo_ranch_grg.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/mlo_ranch_grg_col.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/mlo_ranch_grg_milo_.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/mlo_ranch_grg_shell.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/prop_ch_025c_g_door_01b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_blends.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_blends2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_cabinets.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_ceil.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_dirt.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_door.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_frames.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_light2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_tool.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/stables.ymt`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/vanila/_manifest.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/vanila/apa_ch2_03c_interior_v_ranch_milo_.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/vanila/v_int_56.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/vanila/v_ranch.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ybn/ch2_03c_0.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ybn/ch2_03c_2.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ybn/hi@ch2_03c_0.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ybn/mlo_gravestone_col.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ycd/gs_fire_ycd.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydd/ch2_03c_slod1_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_emissive_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_fountain_water_ripples.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_gate_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_glue_02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_hedge_fur_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_hedge_fur_03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_hedge_fur_04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_ranch004.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_ranch006.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_ranchgrnd_water_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_removed_doors.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_removedwins.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_rnchgrnd01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_rnchgrndov1.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_wall_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_wall_ivy.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_bar_equ.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_constr.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_dt.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_fireplace.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_gardnght.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_lampy.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_pool_l.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_roof_window.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_slidedoors.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_terr_l.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_text.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_detail.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_floor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_lights.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_shower_screen.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_window.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter2_norm.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_ceiling.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_cloth.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_door.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_norm.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_shelf.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_window.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_fire_uv.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_fireplace_glass.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_frame.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_norm.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_plant.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_stairs.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_stairs_glass.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_carpet.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_library.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_lights.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_norm.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_piano.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_window.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_art.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_cabinets.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_chairs.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_detail.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_l.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_stool.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_table.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_window_l.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_window_r.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_books.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_cabinet.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_ceiling.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_chill.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_fireplace.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_frames.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_light_night.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_shelf.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_wall.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_window.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_ceiling.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_deco.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_desk.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_fireplace.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_gallery.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_library.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_table.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_windows.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_panic_room.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_panic_window.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_chand.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_dvere.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_glass.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_sunlight.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_windows.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door4.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door5.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door6.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_bath.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_doorframe.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_doorframe2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_doorframe3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_guest1.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_guest2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_main.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_main_art.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_main_cloth.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_chill.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_gate_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_gate_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_station.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_window_e.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_window_w.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_wine_constr.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_wine_glass.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_wine_shelf.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_wine_shelf_detail.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/mlo_gravestone_shell.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/yukonvodaranch.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_critical_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_long_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_strm_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_strm_1.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_strm_2.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_occl_07.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/gravestone_bar.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/gravestone_construction_stm.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/gravestone_garden_east.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/gravestone_stm.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/mlo_gravestone_milo_.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/vw_distlodlights_medium024.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/vw_distlodlights_small003.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/vw_lodlights_medium024.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/vw_lodlights_small003.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/yukon_ymap.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytd/gravestone_high.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytd/gravestone_txd.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytd/ranchsaferoom.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytyp/cityhills_02_metadata_012_strm.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytyp/gravestone_dt.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytyp/mlo_gravestone.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytyp/yukon_ytyp.ytyp`
```diff
- Gelöscht
```

## 2026-10-25 02:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[oresmon]/rm_hackerv/server/data.json`
```diff
-[{"cooldowns":{"unlock":1790288626,"location_vehicle":0,"crash":1790288778,"trafficLights":1790270949,"control":1790288882,"location_player":0,"tv":0,"parkmeter":1790278782,"steal_cash":1790291249,"botnet":0,"atm":1790275271,"fake_dispatch":1790172475},"botnet":1500000,"identifier":"char3:5d9a7aa1b
+[{"identifier":"char3:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c","cooldowns":{"parkmeter":1790278782,"crash":1790288778,"location_player":0,"tv":0,"atm":1790275271,"fake_dispatch":1790172475,"unlock":1790288626,"botnet":0,"steal_cash":1790291249,"location_vehicle":0,"trafficLights":1790270949,"contr
```

## 2026-10-25 00:22 Uhr
**+0** neu · **~4** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/client/death_owner_notify.lua`
```diff
-    Zeigt die Benachrichtigung für Owner an, wenn ein Spieler stirbt.
-    Hört clientseitig auf baseevents (nicht serverseitig – "not safe for net" vermeiden).
+    Live-Toast bei Tod + /th Historie (Täter → Opfer).
+local function resolveKillerServerId(entity)
+    if not entity or entity == 0 or not DoesEntityExist(entity) then return nil end
+    if not IsEntityAPed(entity) or not IsPedAPlayer(entity) then return nil end
+    for _, playerIdx in ipairs(GetActivePlayers()) do
+        if GetPlayerPed(playerIdx) == entity then
+            local sid = GetPlayerServerId(playerIdx)
+            if sid and sid > 0 then return sid end
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+-- /th zeigt die letzten Tode klar als Täter → Opfer.
-    NotifySubject = "Spieler verstorben",
+    NotifySubject = "Kill / Tod",
+    -- %s = Täter-Name, Täter-ID, Opfer-Name, Opfer-ID, Grund
+    NotifyMessageKilled = "%s (ID %s) hat %s (ID %s) getötet · %s",
+    -- %s = Opfer-Name, Opfer-ID, Grund (kein Spieler-Täter)
+    NotifyMessageDied = "%s (ID %s) ist gestorben · %s",
+    -- Fallback falls alte Keys noch referenziert werden
+    -- /th – letzte Tode als Menü (Täter → Opfer)
+    HistoryCommand = "th",
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"esx_jobs":{"channelId":"1557386361172918374","url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274"},"willkommen":{"channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/15511615978530490
+{"categoryId":"1551161549018759170","webhooks":{"faction":{"channelId":"1551161570439208960","webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"esx_useractions":{"channelId":"1557386339866120252","webhookId":"1557386342755991582","url":"https://disc
```
`~ resources/[selfcode]/rmc_core/server/death_owner_notify.lua`
```diff
-    Wenn ein Spieler stirbt, erhalten alle mit der Rolle "Owner" eine Benachrichtigung
-    mit dem Namen des Verstorbenen und der Todesursache.
+    Wenn ein Spieler stirbt, erhalten Staff eine klare Benachrichtigung (Täter → Opfer).
+    /th zeigt die letzten Tode als Historie.
+local function getHistoryGroups()
+    local g = C.HistoryGroups
+    if type(g) == "table" then
+        return g
+    end
+    return getNotifyGroups()
```

## 2026-10-24 23:23 Uhr
**+2** neu · **~5** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_core/client/mechanic_shop.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/server/mechanic_shop.lua`
```diff
+ Neue Datei
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "reason": "Einzahlung auf Bankkonto",
+            "date": "2026/10/24 - 23:06:30",
+            "receiver_name": "Tatsuya Lee",
+            "value": 5782,
+            "sender_identifier": "bank",
+            "receiver_identifier": "char4:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "sender_name": "Geldbörse",
+            "type": "deposit"
+        },
```
`~ resources/[oresmon]/rm_hackerv/server/data.json`
```diff
-[{"botnet":1500000,"cooldowns":{"botnet":0,"tv":0,"location_vehicle":0,"fake_dispatch":1790172475,"location_player":0,"control":1790288882,"parkmeter":1790278782,"unlock":1790288626,"steal_cash":1790291249,"trafficLights":1790270949,"atm":1790275271,"crash":1790288778},"identifier":"char3:5d9a7aa1b
+[{"cooldowns":{"unlock":1790288626,"location_vehicle":0,"crash":1790288778,"trafficLights":1790270949,"control":1790288882,"location_player":0,"tv":0,"parkmeter":1790278782,"steal_cash":1790291249,"botnet":0,"atm":1790275271,"fake_dispatch":1790172475},"botnet":1500000,"identifier":"char3:5d9a7aa1b
```
`~ resources/[oresmon]/rm_hackerv/shared/cfg.lua`
```diff
-    ['phoneJobs'] = {'sakura'}, -- Jobs for allow use hacker phone (un-comment if you want works with jobs)
+    ['phoneJobs'] = {'rosa_nera'}, -- Jobs for allow use hacker phone (un-comment if you want works with jobs)
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+
+
+-- ====== MECHANIC NPC-VERKAUF (rep_kasten) ======
+-- Wie Pawn: NPC steht nur, je nach ActiveWhen, abhängig davon ob Mechaniker online sind.
+-- Geld vom Käufer geht aufs Gesellschaftskonto (esx_addonaccount).
+Config.MechanicShop = {
+    Job        = 'mechanic',
+    Society    = 'society_mechanic',
+    PayAccount = 'bank',            -- 'bank' oder 'money' (Bargeld) – wird beim Käufer abgezogen
+    -- 'no_job_online' = NPC nur wenn KEIN Mechaniker online ist (genau wie Pawn)
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"sperrzone":{"webhookId":"1552971115209564220","url":"https://discord.com/api/webhooks/1552971115209564220/***","channelId":"1552971110457286766"},"poster":{"webhookId":"1560007815156998144","url":"https://discord.com/api/webhooks/1560007815156998144/***","channelId":"15600078123424891
+{"categoryId":"1551161549018759170","webhooks":{"esx_jobs":{"channelId":"1557386361172918374","url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274"},"willkommen":{"channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/15511615978530490
```

## 2026-10-24 22:23 Uhr
**+7** neu · **~8** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_halloween/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/html/sounds/distant.mp3`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/html/sounds/heartbeat.mp3`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/html/sounds/moan.mp3`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/html/sounds/scream.mp3`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/html/sounds/whisper.mp3`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/scares.lua`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
+    "lastBackup": 1792870168,
-            "backupDate": "21_10_19_10_2026",
-            "backupTimestamp": 1792437006,
-            "id": 11,
-            "backupFile": "banlist_21_10_19_10_2026.json"
-        },
-        {
-            "backupDate": "21_12_19_10_2026",
-            "backupTimestamp": 1792437131,
-            "id": 11,
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "reason": "Überweisung an Sparkonto",
+            "date": "2026/10/24 - 22:21:53",
+            "receiver_name": "Salome Blackwood",
+            "value": 259062,
+            "sender_identifier": "char3:95e98569cca18ee079f5fe27ab54152ede42f277",
+            "receiver_identifier": "char3:95e98569cca18ee079f5fe27ab54152ede42f277",
+            "sender_name": "Salome Blackwood",
+            "type": "transfer_to_savings"
+        },
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"esx_test":{"webhookId":"1557386332483887194","channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"versicherung":{"webhookId":"1535733186921898004","channelId":"1535733166138990602","url":"https://discord.com/api/webhooks/1535733186921898
+{"webhooks":{"sperrzone":{"webhookId":"1552971115209564220","url":"https://discord.com/api/webhooks/1552971115209564220/***","channelId":"1552971110457286766"},"poster":{"webhookId":"1560007815156998144","url":"https://discord.com/api/webhooks/1560007815156998144/***","channelId":"15600078123424891
```
`~ resources/[selfcode]/rmc_halloween/client.lua`
```diff
+    TriggerEvent('rmc_halloween:digStarted')
```
`~ resources/[selfcode]/rmc_halloween/config.lua`
```diff
-    volume   = 0.6,   -- 0.0 - 1.0
+    volume   = 0.4,   -- 0.0 - 1.0
-Config.EventDuration = 30   -- Minuten bis das Event automatisch endet (0 = nie)
+Config.EventDuration = 30   -- Minuten Fallback: Event endet spaetestens dann (0 = nie)
+
+-- Genau so viele goldene Kuerbisse pro Event. Sind alle gefunden -> Event endet automatisch
+Config.GoldenPumpkins = 2
+Config.EndDelay       = 15  -- Sekunden nach dem letzten goldenen Kuerbis bis zum Ende
-    model         = 'g_m_m_zombie_05',
+    model         = 'u_m_y_zombie_01',
```
`~ resources/[selfcode]/rmc_halloween/fxmanifest.lua`
```diff
-client_script 'client.lua'
+client_scripts { 'client.lua', 'scares.lua' }
```
`~ resources/[selfcode]/rmc_halloween/html/index.html`
```diff
+  else if (d.action === 'sfx') {
+    const s = new Audio(d.src);
+    s.volume = Math.max(0, Math.min(1, d.volume ?? 0.5));
+    s.play().catch(()=>{});
+  }
```
`~ resources/[selfcode]/rmc_halloween/server.lua`
```diff
-local Event = { active = false, zone = nil, flashUntil = 0, pumpkins = {}, nextId = 0, zombies = {}, stats = {}, cooldowns = {}, endAt = 0 }
+local ghostLoop
+local Event = { goldenFound = {}, ghosts = {}, active = false, zone = nil, flashUntil = 0, pumpkins = {}, nextId = 0, zombies = {}, stats = {}, cooldowns = {}, endAt = 0 }
-local function spawnPumpkin()
+local function spawnPumpkin(golden)
-    local golden = math.random(100) <= Config.Pumpkins.golden.chance
+    golden = golden == true
+-- ===== Geister =====
+local function spawnGhost()
+    local p = randomPointInZone()
```

## 2026-10-24 21:23 Uhr
**+6** neu · **~1** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_halloween/client.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/html/index.html`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/html/sounds/halloween.mp3`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_halloween/server.lua`
```diff
+ Neue Datei
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char4:ed00a18aa373b82fda2a51a5f23d0c0567f13db9": [
+    "char1:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c": [
-            "type": "loan_payment",
-            "date": "2026/06/05 - 22:49:32",
-            "sender_name": "",
-            "sender_identifier": "char4:ed00a18aa373b82fda2a51a5f23d0c0567f13db9",
-            "reason": "Kreditablösung: Executive Loan",
-            "receiver_name": "Bank (Kreditablösung)",
-            "receiver_identifier": "bank",
-            "value": 21200
```

## 2026-10-24 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"support":{"channelId":"1552971099317211136","webhookId":"1552971101741654046","url":"https://discord.com/api/webhooks/1552971101741654046/***"},"einreise":{"channelId":"1552971085937381431","webhookId":"1552971088328392714","url":"https://discord.com
+{"webhooks":{"esx_test":{"webhookId":"1557386332483887194","channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"versicherung":{"webhookId":"1535733186921898004","channelId":"1535733166138990602","url":"https://discord.com/api/webhooks/1535733186921898
```

## 2026-10-24 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-24T01:01:16Z","webhooks":{"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664","webhookId":"1557386337580220497"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***"
+{"categoryId":"1551161549018759170","webhooks":{"support":{"channelId":"1552971099317211136","webhookId":"1552971101741654046","url":"https://discord.com/api/webhooks/1552971101741654046/***"},"einreise":{"channelId":"1552971085937381431","webhookId":"1552971088328392714","url":"https://discord.com
```

## 2026-10-24 03:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-23T22:08:37Z","webhooks":{"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715","channelId":"1552989823604756600"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/**
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-24T01:01:16Z","webhooks":{"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664","webhookId":"1557386337580220497"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***"
```

## 2026-10-24 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"lager":{"channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879"},"default":{"channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269"
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-23T22:08:37Z","webhooks":{"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715","channelId":"1552989823604756600"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/**
```

## 2026-10-23 22:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupTimestamp": 1792350407,
-            "backupDate": "21_06_18_10_2026",
-            "id": 11,
-            "backupFile": "banlist_21_06_18_10_2026.json"
-        },
-        {
-            "backupTimestamp": 1792350532,
-            "backupDate": "21_08_18_10_2026",
-            "id": 11,
-            "backupFile": "banlist_21_08_18_10_2026.json"
```
`~ resources/[selfcode]/rmc_tablet/config.lua`
```diff
-    enabled = true,
+    enabled = false,
```

## 2026-10-23 20:23 Uhr
**+0** neu · **~3** geändert · **-3** gelöscht
`~ resources/[selfcode]/rmc_api/config/api_key.lua`
```diff
-Config.PlaytimeCoins = {
-    Enabled = true,
-    IntervalMs = 30 * 60 * 1000,  -- 30 Minuten zwischen zwei Collects
-    CheckEveryMs = 60 * 1000,     -- Online-Spieler alle 60s prüfen
-    MinAmount = 1,                -- mindestens 1 Coin
-    MaxAmount = 1,
-    BotWebhookUrl = 'http://88.99.28.143:3000/api/webhook',
-    BotWebhookSecret = 'fa88f376407d8ced79b85cf6c27635cf280c82673e',
-    Debug = false,
-}
```
`~ resources/[selfcode]/rmc_api/fxmanifest.lua`
```diff
-    'server/modules/economy.lua',
-    'server/modules/coinshop.lua',
+-- Client-Side für Admin-Aktionen (Skin, Heal, Freeze) + Phone
-    'client/coinshop.lua',
-    -- 'ox_lib',            (für Hotel-Confirm, Kündigung und Coin-Shop)
-    -- 'ox_target',         (für Coin-Shop NPC)
+    -- 'ox_lib',            (für Hotel-Confirm und Kündigung)
```
`~ resources/[selfcode]/rmc_api/server/main.lua`
```diff
-    -- Playtime-Coins (automatisch, nur online)
-    { method = 'GET',  path = '/economy/playtime',                    handler = function(req, res) EconomyModule.status(req, res) end },
-    { method = 'GET',  path = '/economy/playtime/:id',                handler = function(req, res, p) EconomyModule.playerStatus(req, res, p[1]) end },
-    { method = 'POST', path = '/economy/playtime/tick',               handler = function(req, res) EconomyModule.tickHttp(req, res) end },
-    { method = 'POST', path = '/economy/playtime/collect',            handler = function(req, res) EconomyModule.collect(req, res) end },
-
```
`− resources/[selfcode]/rmc_api/client/coinshop.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/coinshop.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/economy.lua`
```diff
- Gelöscht
```

## 2026-10-23 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"marriage":{"channelId":"1467556343492640830","url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901"},"esx_test":{"channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887
+{"webhooks":{"lager":{"channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879"},"default":{"channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269"
```

## 2026-10-23 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"esx_paycheck":{"channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816"},"esx":{"channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"15573863269515920
+{"webhooks":{"marriage":{"channelId":"1467556343492640830","url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901"},"esx_test":{"channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887
```

## 2026-10-23 06:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-22T22:00:51Z","webhooks":{"adminjail":{"channelId":"1551161575690211428","url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630"},"frak":{"channelId":"1552971094267527169","url":"https://discord.com/
+{"webhooks":{"esx_paycheck":{"channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816"},"esx":{"channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"15573863269515920
```

## 2026-10-23 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"15511615500966993
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-22T22:00:51Z","webhooks":{"adminjail":{"channelId":"1551161575690211428","url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630"},"frak":{"channelId":"1552971094267527169","url":"https://discord.com/
```

## 2026-10-22 22:23 Uhr
**+2** neu · **~0** geändert · **-0** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_20_22_10_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_22_22_10_2026.json`
```diff
+ Neue Datei
```

## 2026-10-22 21:23 Uhr
**+0** neu · **~1** geändert · **-2** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupDate": "21_02_17_10_2026",
-            "id": 11,
-            "backupFile": "banlist_21_02_17_10_2026.json",
-            "backupTimestamp": 1792263757
-        },
-        {
-            "backupDate": "21_04_17_10_2026",
-            "id": 11,
-            "backupFile": "banlist_21_04_17_10_2026.json",
-            "backupTimestamp": 1792263882
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_02_17_10_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_04_17_10_2026.json`
```diff
- Gelöscht
```

## 2026-10-22 18:23 Uhr
**+167** neu · **~1** geändert · **-125** gelöscht
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/.fxap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/_manifest.ymf`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/mlo_ranch_grg.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/mlo_ranch_grg_col.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/mlo_ranch_grg_milo_.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/mlo_ranch_grg_shell.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/prop_ch_025c_g_door_01b.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_blends.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_blends2.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_cabinets.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_ceil.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_dirt.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_door.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_frames.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_light.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_light2.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/garage/ranch_gr_tool.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/stables.ymt`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/vanila/_manifest.ymf`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/vanila/apa_ch2_03c_interior_v_ranch_milo_.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/vanila/v_int_56.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/vanila/v_ranch.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ybn/ch2_03c_0.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ybn/ch2_03c_2.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ybn/hi@ch2_03c_0.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ybn/mlo_gravestone_col.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ycd/gs_fire_ycd.ycd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydd/ch2_03c_slod1_children.ydd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_emissive_a.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_fountain_water_ripples.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_gate_01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_glue_02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_hedge_fur_01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_hedge_fur_03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_hedge_fur_04.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_ranch004.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_ranch006.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_ranchgrnd_water_01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_removed_doors.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_removedwins.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_rnchgrnd01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_rnchgrndov1.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_wall_01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/ch2_03c_wall_ivy.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_bar_equ.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_constr.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_dt.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_fireplace.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_gardnght.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_lampy.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_pool_l.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_roof_window.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_slidedoors.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_terr_l.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gravestone_text.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_detail.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_floor.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_lights.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_shower_screen.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_bath_window.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter2_norm.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_ceiling.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_cloth.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_door.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_norm.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_shelf.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_enter_window.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_fire_uv.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_fireplace_glass.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_frame.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_norm.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_plant.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_stairs.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hall_stairs_glass.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_carpet.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_library.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_lights.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_norm.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_piano.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_hallway_window.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_art.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_cabinets.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_chairs.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_detail.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_l.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_stool.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_table.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_window_l.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_kitchen_window_r.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_books.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_cabinet.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_ceiling.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_chill.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_fireplace.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_frames.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_light.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_light_night.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_shelf.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_wall.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_living_window.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_ceiling.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_deco.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_desk.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_fireplace.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_gallery.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_library.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_table.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_office_windows.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_panic_room.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_panic_window.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_chand.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_dvere.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_glass.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_sunlight.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_podkrovi_windows.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door2.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door3.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door4.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door5.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_prop_gs_door6.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_bath.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_doorframe.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_doorframe2.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_doorframe3.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_guest1.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_guest2.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_main.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_main_art.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_up_main_cloth.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_chill.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_gate_a.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_gate_b.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_light.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_station.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_window_e.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_waiting_window_w.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_wine_constr.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_wine_glass.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_wine_shelf.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/gs_wine_shelf_detail.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/mlo_gravestone_shell.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ydr/yukonvodaranch.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_critical_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_long_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_strm_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_strm_1.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_03c_strm_2.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/apa_ch2_occl_07.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/gravestone_bar.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/gravestone_construction_stm.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/gravestone_garden_east.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/gravestone_stm.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/vw_distlodlights_medium024.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/vw_distlodlights_small003.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/vw_lodlights_medium024.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/vw_lodlights_small003.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ymap/yukon_ymap.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytd/gravestone_high.ytd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytd/gravestone_txd.ytd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytd/ranchsaferoom.ytd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytyp/cityhills_02_metadata_012_strm.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytyp/gravestone_dt.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytyp/mlo_gravestone.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/ykn_gravestone_garage/stream/ytyp/yukon_ytyp.ytyp`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-22T08:01:26Z","webhooks":{"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617","webhookId":"1512475306554953789"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","c
+{"webhooks":{"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"15511615500966993
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/.fxap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/_manifest.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/bushes_txt.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_12.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_bchrks_5.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_land01b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_pier_endmain01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_pier_stilts.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_slod1b_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_occl_00.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_occl_01.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_occl_02.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_occl_03.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/changer_ch1_malpier29.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/changer_ch1_malpier29.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_11.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_11_critical_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_11_long_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_11_strm_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_12_critical_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_12_long_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_12_strm_2.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hi@ch1_11_0.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/maiq_yakuza.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_back_exterior.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_back_exterior_dec.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_block.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes05.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes06.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_dirt_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_dirt_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_dirt_c.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_dirt_d.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_ext_door_l.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_ext_door_r.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_exteriorlight.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_faketowerinterior.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_main.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_main02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_main03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal05.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal06.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal07.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal08.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal09.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal10.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal11.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal12.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_place.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_place.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_place.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_place.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_sakuraflower.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_sakuratree.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza_props.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_bigframe.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_bombscreen.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_bosschair.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_floorlamp_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_glassdoor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_gongo.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_katana01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_katana02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_katana03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_katana04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_metalframe.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_mirror01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_mirror02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_mirror03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_mirror04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r01details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r01details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r02details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r02details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r03details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r03details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r04details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r04details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r05details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r05details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r05details03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r06details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r06details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r06details03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r07details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r07details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r07details03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r08details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r08details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details02.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r10details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r10details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r10details03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r11details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r11details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r11details03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r12details01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r12details02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r12details03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_redlight.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_shell.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_shell02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_sidedoor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_sidedoor_ext_l.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_sidedoor_ext_r.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_smallframe.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_wingchun.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/yakuza_doors.ytyp`
```diff
- Gelöscht
```
