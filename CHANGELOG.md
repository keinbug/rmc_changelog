# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

## 2026-11-11 20:23 Uhr
**+0** neu · **~5** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char4:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c": [
-        {
-            "value": 2500,
-            "sender_name": "Coco Black",
-            "sender_identifier": "char4:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
-            "date": "2026/11/03 - 03:14:08",
-            "type": "withdraw",
-            "reason": "Fahrzeugrückgabegebühr",
-            "receiver_identifier": "cd_garage",
-            "receiver_name": "cd_garage"
```
`~ resources/[selfcode]/rmc_aduty/config/sv_config.lua`
```diff
-sv_config = {}
-
-sv_config.general = {
-    language = "de",
-    events = {
-        ["esx:playerLoaded"] = "esx:playerLoaded",
-        ["esx:setJob"] = "esx:setJob"
-    }
-}
-
```
`~ resources/[selfcode]/rmc_aduty/server/server.lua`
```diff
+local apiIdentCache = {}      -- [source] = letzter bekannter char-Identifier (für Log beim Disconnect)
+local screenshotToken = 0
+
+-- ============================================================
+-- Log-API (v1-api.rmc-rp.de)
+-- ============================================================
+
+--- Sendet einen Log an die Log-API. Läuft nur serverseitig.
+--- @param src number
+--- @param xPlayer table|nil
```
`~ resources/[selfcode]/rmc_minijobs/client/admin.lua`
```diff
+    ghostGeneration = 0,
+    TR.Editor.ghostGeneration = (TR.Editor.ghostGeneration or 0) + 1
+-- Läuft im Hintergrund, damit das Menü sofort aufgeht.
+    local generation = TR.Editor.ghostGeneration
+    local points = job.points or {}
-    for i = 1, #(job.points or {}) do
-        local point = job.points[i]
-        local coords = point.coords
-        if coords then
-            if spec.spawnPed then
```
`~ resources/[selfcode]/rmc_minijobs/client/main.lua`
```diff
+local companyGeneration = 0
+
+-- Blips sofort, Peds im Hintergrund: blockiert Menüs/Callbacks nicht mehr.
+    companyGeneration = companyGeneration + 1
+    local generation = companyGeneration
+
+    local pending = {}
-                local ped = TR.SpawnStandingPed(modelName, pedCoords, pedCoords.w or 0.0)
-                if ped ~= 0 then
-                    TR.State.world.peds[#TR.State.world.peds + 1] = ped
```

## 2026-11-11 19:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_minijobs/client/admin.lua`
```diff
-TR = TR or {}
-TR.Editor = {
-    session = false,
-    preview = false,
-    jobId = nil,
-    ghosts = {},
-    zones = {},
-    worldTargets = {},
-}
-
```
`~ resources/[selfcode]/rmc_minijobs/client/main.lua`
```diff
-ESX = exports['es_extended']:getSharedObject()
-TR = TR or {}
-
-TR.State = {
-    ready = false,
-    dutyJobId = nil,
-    assignment = nil,
-    stats = nil,
-    jobVehicle = 0,
-    hatchOpen = false,
```

## 2026-11-11 18:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"versicherung":{"url":"https://discord.com/api/webhooks/1535733186921898004/***","channelId":"1535733166138990602","webhookId":"1535733186921898004"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924
+{"updatedAt":"2026-11-11T17:01:19Z","categoryId":"1551161549018759170","webhooks":{"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169","webhookId":"1552971096847028264"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***",
```

## 2026-11-11 14:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"lager":{"channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879"},"frak":{"channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264"},"
+{"webhooks":{"versicherung":{"url":"https://discord.com/api/webhooks/1535733186921898004/***","channelId":"1535733166138990602","webhookId":"1535733186921898004"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924
```

## 2026-11-11 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"doors":{"channelId":"1559665845330907296","webhookId":"1559665847771988080","url":"https://discord.com/api/webhooks/1559665847771988080/***"},"chopshop":{"channelId":"1552971071882399744","webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***
+{"webhooks":{"lager":{"channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879"},"frak":{"channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264"},"
```

## 2026-11-10 22:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
+    "lastBackup": 1794342324,
-            "backupFile": "banlist_21_06_05_11_2026.json",
-            "backupTimestamp": 1793909199,
-            "backupDate": "21_06_05_11_2026",
-            "id": 11
-        },
-        {
-            "backupFile": "banlist_21_08_05_11_2026.json",
-            "backupTimestamp": 1793909324,
-            "backupDate": "21_08_05_11_2026",
```

## 2026-11-10 21:23 Uhr
**+2** neu · **~4** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_core/client/frakmenu.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/server/frakmenu.lua`
```diff
+ Neue Datei
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "sender_name": "Geldbörse",
+            "reason": "Einzahlung auf Kartenkonto",
+            "sender_identifier": "bank",
+            "date": "2026/11/10 - 20:50:57",
+            "type": "deposit",
+            "receiver_name": "Fabi Huber",
+            "receiver_identifier": "char1:726b2e82f8613191a738a5158a2b2cd5c7dbeea1",
+            "value": 160000
+        },
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+        midnight_elite = {
+            label = 'Midnight Elite',
+            blipColor = 27,      -- Lila
+            sprite = 1,
+            vehicleSprite = 225,
+        },
+-- ====== FRAKTIONS-MENÜ (/fraktion) ======
+-- GPS ein/aus, Mitglieder online mit Rang + Telefonnummer (kopierbar),
+-- Wegpunkt zu Kollegen (nur wenn beide GPS an haben).
+-- Erlaubte Jobs = Config.FrakGps.Jobs (Label kommt auch von dort).
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664","webhookId":"1557386337580220497"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","channelId":"1552971099317211
+{"webhooks":{"doors":{"channelId":"1559665845330907296","webhookId":"1559665847771988080","url":"https://discord.com/api/webhooks/1559665847771988080/***"},"chopshop":{"channelId":"1552971071882399744","webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***
```
`~ resources/[selfcode]/rmc_core/server/frakgps.lua`
```diff
+-- Für /fraktion (server/frakmenu.lua): ist das GPS dieses Spielers gerade an?
+function IsFrakGpsActive(src)
+    return active[tonumber(src) or -1] ~= nil
+end
+
```

## 2026-11-10 20:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9": [
-        {
-            "value": 500,
-            "reason": "Fahrzeugrückgabegebühr",
-            "type": "withdraw",
-            "date": "2026/09/16 - 20:15:27",
-            "receiver_identifier": "cd_garage",
-            "sender_identifier": "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9",
-            "receiver_name": "cd_garage",
-            "sender_name": "Jayden Anderson"
```

## 2026-11-10 18:23 Uhr
**+0** neu · **~1** geändert · **-202** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"}
+{"categoryId":"1551161549018759170","webhooks":{"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664","webhookId":"1557386337580220497"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","channelId":"1552971099317211
```
`− resources/[osp]/osp_ambulance/.fxap`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/ESX ITEMS DATABASE.sql`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/README.txt`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/carvariations.meta`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/client_open.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/dead.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/ecg.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/fractures.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/incoming.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/job.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/laststand.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/main.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/stationary.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/stretcher.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/client/wheelchair.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/config/fractures.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/config/general.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/config/locations.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/config/medications.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/config/shop.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/config/vehicles.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/config/weapons.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/config/webhook.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/config/wounds.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/handling.meta`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/ecg.js`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/fracture1.wav`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/fracture2.wav`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/guide.html`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_left.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_left_b.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_left_f.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_left_fracture.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_left_h.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_left_l.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_left_m.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_left_s.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_left_t.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_right.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_right_b.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_right_f.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_right_fracture.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_right_h.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_right_l.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_right_m.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_right_s.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/arm_right_t.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/background.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/head.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/head_b.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/head_f.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/head_fracture.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/head_h.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/head_l.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/head_m.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/head_s.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_left.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_left_b.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_left_f.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_left_fracture.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_left_h.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_left_l.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_left_m.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_left_s.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_left_t.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_right.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_right_b.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_right_f.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_right_fracture.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_right_h.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_right_l.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_right_m.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_right_s.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/leg_right_t.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/neck.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/spine.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/torso.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/torso_b.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/torso_f.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/torso_fracture.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/torso_h.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/torso_l.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/torso_m.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/img/torso_s.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/incoming.html`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/incoming.js`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/index.html`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/inject.wav`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/jquery.min.js`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/rapidheartbeat.wav`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/slowheartbeat.wav`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/stationary.html`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/stationary.js`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/test.html`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/ui.html`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/visualEffects.html`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/xray.html`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/html/xray.wav`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/armcast.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/armsplint.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/bandage.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/blood250ml.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/blood500ml.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/bodybag.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/castsaw.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/crutch.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/ecg.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/elastic_bandage.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/epinephrine.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/field_dressing.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/ifak.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/legcast.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/legsplint.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/morphine.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/neckbrace.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/neckcast.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/packing_bandage.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/pager.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/painkillers.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/propofol.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/quick_clot.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/revivekit.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/saline250ml.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/saline500ml.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/sewing_kit.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/stretcher.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/tourniquet.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/inventoryImages/wheelchair.png`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/al.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/ar.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/cs.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/da.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/de.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/el.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/en.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/es.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/et.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/fi.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/fr.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/he.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/hr.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/hu.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/id.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/it.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/lt.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/nl.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/no.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/pl.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/pt-br.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/pt.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/ro.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/ru.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/sk.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/sl.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/sv.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/th.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/tr.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/zh-cn.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/lang/zh-tw.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/server/server.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/server/server_open.lua`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/sound/audiodirectory/ambulance_sounds.awc`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/sound/audiodirectory/ambulance_sounds.awc.xml`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/sound/data/ambulance_sounds.dat54.rel`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/sound/data/ambulance_sounds.dat54.rel.xml`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/combicarrier2.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/ems_props.ytyp`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/fernocot.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/fernotexture.ytd`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/lifepak15.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/loweredfernocot.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/loweredstrykergurney.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/lucas2.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/lucas3.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/prop_ld_bomb.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/sittingfernocot.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/sittingstrykergurney.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/strykergurney.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[emsprops]/strykertexture.ytd`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[wheelchair]/iak_wheelchair.yft`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[wheelchair]/iak_wheelchair.ytd`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[wheelchair]/iak_wheelchair_hi.yft`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[wheelchair]/v_med_crutch01.ydr`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/[props]/[wheelchair]/v_med_crutch01.ytyp`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_ekg1.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_ekg2.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_ekg3.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_incoming1.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_incoming2.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_stationary1.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_stationary2.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_stationary3.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_stationary4.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_stationary5.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_stationary6.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/stream/generic_texture_renderer_xray1.gfx`
```diff
- Gelöscht
```
`− resources/[osp]/osp_ambulance/vehicles.meta`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_jj/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_jj/stream/hei_dt1_rd1.ymap`
```diff
- Gelöscht
```

## 2026-11-10 10:22 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38": [
-        {
-            "reason": "Savings account interest payment (Period 42)",
-            "date": "2026/11/02 - 10:01:02",
-            "type": "interest_savings",
-            "sender_name": "Savings Interest",
-            "sender_identifier": "bank",
-            "value": 3,
-            "receiver_identifier": "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38",
-            "receiver_name": "Savings Account"
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-09T23:01:03Z","webhooks":{"sozialstunden":{"webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"1552971081491419187"},"basicneeds":{"webhookId":"1552971931869777932","url":"https://di
+{"webhooks":{"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"}
```

## 2026-11-10 00:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+            "reason": "Fahrzeugrückgabegebühr",
+            "sender_identifier": "char1:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "date": "2026/11/09 - 23:24:21",
+            "receiver_name": "cd_garage",
+            "sender_name": "Coco Rossi",
+            "type": "withdraw",
+            "receiver_identifier": "cd_garage",
+            "value": 500
+        },
+        {
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-09T17:00:52Z","webhooks":{"frak":{"channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264"},"esx_paycheck":{"channelId":"1557386352226598913","url":"https://discord.c
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-09T23:01:03Z","webhooks":{"sozialstunden":{"webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"1552971081491419187"},"basicneeds":{"webhookId":"1552971931869777932","url":"https://di
```

## 2026-11-09 22:23 Uhr
**+2** neu · **~0** geändert · **-0** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_20_09_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_22_09_11_2026.json`
```diff
+ Neue Datei
```

## 2026-11-09 21:23 Uhr
**+0** neu · **~3** geändert · **-2** gelöscht
`~ resources/[brutal]/brutal_ambulancejob/config.lua`
```diff
-
-Hi, thank you for buying our script, We are very grateful!
-
-For help join our Discord server:     https://discord.gg/85u2u5c8q9
-More informations about the script:   https://docs.brutalscripts.com
-
-Config = {
-    Core = 'ESX',  -- 'ESX' / 'QBCORE' | Other core setting on the 'core' folder.
-    Inventory = 'ox_inventory', -- 'ox_inventory' / 'qb_inventory' / 'quasar_inventory' / 'chezza_inventory' / 'codem_inventory' / 'core_inventory' / 'origen_inventory' / 'ps-inventory' / 'tgiann-inventory' // Custom can be add in the cl_utils.lua!!!
-    Billing = 'okokBilling', -- 'brutal_billing' / 'okokBilling' / 'esx_billing' / 'jaksam_billing' / 'codem_billing' / 'quasar_billing' | false = immediate deduction from the player's bank account
```
`~ resources/[brutal]/brutal_ambulancejob/sv_utils.lua`
```diff
-        TriggerClientEvent('brutal_ambulancejob:client:DefaultNotify', text)
+        TriggerClientEvent('brutal_ambulancejob:client:DefaultNotify', source, text)
-end
+end
+
+-- ============================================================
+-- Admin-Revive Benachrichtigung
+-- Die Befehls-Logik liegt in der verschluesselten server/commands.lua.
+-- Daher wird hier (sv_utils.lua laedt VOR server/*.lua) der Revive-Command
+-- beim Registrieren umschlossen: Alle Revive-Events, die waehrend der
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupTimestamp": 1793822614,
-            "backupDate": "21_03_04_11_2026",
-            "id": 11,
-            "backupFile": "banlist_21_03_04_11_2026.json"
-        },
-        {
-            "backupTimestamp": 1793822739,
-            "backupDate": "21_05_04_11_2026",
-            "id": 11,
-            "backupFile": "banlist_21_05_04_11_2026.json"
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_03_04_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_05_04_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-09 20:23 Uhr
**+36** neu · **~2** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_housing/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/appliances.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/camera.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/clothing.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/creator.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/interior.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/admin.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/appliances.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/billing.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/db.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/outfits.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/shared/interiors.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/app.js`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/aqua.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/highend.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/lowend.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/medium.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/modern.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/mono.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/moody.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/office_ice.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/office_rich.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/office_warm.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/penthouse.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/regal.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/seductive.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/sharp.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/stilt1.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/stilt2.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/vibrant.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/index.html`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/style.css`
```diff
+ Neue Datei
```
`~ resources/[jaksam_scripte]/robberies_creator/current_config.json`
```diff
-{"client":{"targetingScript":"none","clNpcMugging":{"cooldownOnMugging":15,"canMakeFollow":false},"gasMaskClothId":38,"npcMuggingKeys":{"keyToMug":47,"keyToFollow":74,"keyToGoAway":20}},"server":{"drill":{"loseOnUse":true,"name":"drill","requiredForCargoRobbery":true},"cargoRobbery":{"probabilityPo
+{"shared":{"modules":{"textui":"ox_lib","dispatch":"codesign","progressbar":"ox_lib","logs":"jaksam"},"isNpcMuggingEnabled":true,"secondsToMug":45,"locale":"de"},"server":{"specificWebhooks":[],"maxMinutesDifferenceForCargoRobberies":10,"drill":{"requiredForCargoRobbery":true,"loseOnUse":true,"name
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "reason": "Auszahlung vom Bankkonto",
+            "sender_identifier": "char1:95e98569cca18ee079f5fe27ab54152ede42f277",
+            "date": "2026/11/09 - 19:51:57",
+            "sender_name": "Mellie Anderson",
+            "type": "withdraw",
+            "value": 2000,
+            "receiver_identifier": "bank",
+            "receiver_name": "Geldbörse"
+        },
```

## 2026-11-09 19:23 Uhr
**+0** neu · **~3** geändert · **-0** gelöscht
`~ resources/[manuell_start]/ox_inventory/data/items.lua`
```diff
+	["tk_pizza"] = {
+		label = "Tiefkühl Pizza",
+		weight = 10,
+		stack = true,
+		close = true,
+	},
+
+	["kaffeebohnen"] = {
+		label = "Kaffeebohne",
+		weight = 1000,
```
`~ resources/[manuell_start]/ox_inventory/data/shops.lua`
```diff
+			{ name = 'tk_pizza', price = 11 },
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-            "receiver_identifier": "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38",
-            "value": 3,
+            "type": "interest_savings",
-            "receiver_name": "Savings Account",
-            "type": "interest_savings"
+            "value": 3,
+            "receiver_identifier": "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38",
+            "receiver_name": "Savings Account"
-            "receiver_identifier": "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38",
-            "value": 3,
```

## 2026-11-09 18:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"poster":{"webhookId":"1560007815156998144","channelId":"1560007812342489120","url":"https://discord.com/api/webhooks/1560007815156998144/***"},"esx":{"webhookId":"1557386326951592027","channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***"},"
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-09T17:00:52Z","webhooks":{"frak":{"channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264"},"esx_paycheck":{"channelId":"1557386352226598913","url":"https://discord.c
```

## 2026-11-09 14:23 Uhr
**+103** neu · **~0** geändert · **-0** gelöscht
`+ resources/[manuell_start]/ox_inventory/web/images/kaffeebohnen.png`
```diff
+ Neue Datei
```
`+ resources/[manuell_start]/ox_inventory/web/images/tk_pizza.png`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/.fxap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/1.png`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/2.png`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/3.png`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/README.txt`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/apa_ch2_10_6.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/server.lua`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/sp_manifest.ymt`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/MajestyMansionManifest.ymf`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_baselegno.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_bbq.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_cancello_l.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_cancello_r.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_coll.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_colonna.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_colonnaesterna.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_cornici.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_coso.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_cucina.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_esterno.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_esterno_coll.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_esterno_ymap.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_gazebo.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_lavandino.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_libri.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_luce.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_mensolabagno.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_mensolavetro.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_mobile12.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_muroesterno.ytd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_piantagenerale.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_piscina.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_piscina_acqua.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_piscina_acqua_coll.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_portaentrata_r.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_portagenerale.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_props.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room04.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room04_mobile.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room04_tavolino.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room05.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room06.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room07.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room08.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room08_armadio.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room08_porta.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room09.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room10.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room10_murales.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room11.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room12.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room13.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14_armadio.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14_letto.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14_scaffale.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14_tavolino.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room15.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room15_divanetto.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_rotonda.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_sassi.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_serranda.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_setsedie.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_shell.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_socket.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_socket2.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_specchio.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_specchio2.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradaesterna.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradina.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradina2.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradina3.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradina4.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_tappeto.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_tavololampada.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_terrenoesterno.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_texture.ytd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_ymap.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_ytyp.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_4.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_6.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_critical_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_long_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_long_1.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_strm_1.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_strm_2.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ba_curtain2.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/bh1_36_gatefrm_iref.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_10_grass_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_10_land_04.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_rdprops_ch2_rd_wire074.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_rdprops_ch2_rd_wire075.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_rdprops_ch2_rd_wire109.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_rdprops_ch2_rd_wire110.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch_chint02_mirror_frame.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/vinewood_hills.ymt`
```diff
+ Neue Datei
```

## 2026-11-09 10:22 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-09T00:46:20Z","webhooks":{"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617","webhookId":"1512475306554953789"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744"
+{"webhooks":{"poster":{"webhookId":"1560007815156998144","channelId":"1560007812342489120","url":"https://discord.com/api/webhooks/1560007815156998144/***"},"esx":{"webhookId":"1557386326951592027","channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***"},"
```
`~ resources/[selfcode]/rmc_core/server/webhook.lua`
```diff
-
-local function firstWebhookUrl()
-    local keys = { "willkommen", "me", "afk", "bell", "hotdog" }
-    for i = 1, #keys do
-        local url = GetWebhookLinkRaw and GetWebhookLinkRaw(keys[i]) or nil
-        if url and url ~= "" then return url end
-    end
-    return nil
-end
-
```

## 2026-11-09 02:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"freecam_photo":{"webhookId":"1551520132319412284","channelId":"1551520126367572008","url":"https://discord.com/api/webhooks/1551520132319412284/***"},"marriage":{"webhookId":"1467556382038429901","channelId":"1467556343492640830","url":"https://disco
+{"updatedAt":"2026-11-09T00:46:20Z","webhooks":{"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617","webhookId":"1512475306554953789"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744"
```

## 2026-11-08 23:23 Uhr
**+0** neu · **~3** geändert · **-34** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-08T20:12:21Z","webhooks":{"sozialstunden":{"channelId":"1552971081491419187","webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***"},"basicneeds":{"channelId":"1417917687723724872","webhookId":"1552971931869777932","url":"https://dis
+{"categoryId":"1551161549018759170","webhooks":{"freecam_photo":{"webhookId":"1551520132319412284","channelId":"1551520126367572008","url":"https://discord.com/api/webhooks/1551520132319412284/***"},"marriage":{"webhookId":"1467556382038429901","channelId":"1467556343492640830","url":"https://disco
```
`~ server.cfg`
```diff
(Secrets — Inhalt unterdrückt)
```
`~ server.cfg.bkp`
```diff
(Secrets — Inhalt unterdrückt)
```
`− resources/[selfcode]/rmc_housing/README.md`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/client/camera.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/client/clothing.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/client/creator.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/client/interior.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/client/main.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/config.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/server/admin.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/server/billing.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/server/db.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/server/main.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/server/outfits.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/shared/interiors.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/app.js`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/aqua.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/highend.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/lowend.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/medium.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/modern.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/mono.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/moody.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/office_ice.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/office_rich.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/office_warm.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/penthouse.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/regal.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/seductive.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/sharp.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/stilt1.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/stilt2.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/img/vibrant.jpg`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/index.html`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_housing/web/style.css`
```diff
- Gelöscht
```

## 2026-11-08 22:23 Uhr
**+36** neu · **~1** geändert · **-0** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_16_08_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_18_08_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/camera.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/clothing.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/creator.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/interior.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/admin.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/billing.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/db.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/outfits.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/shared/interiors.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/app.js`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/aqua.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/highend.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/lowend.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/medium.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/modern.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/mono.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/moody.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/office_ice.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/office_rich.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/office_warm.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/penthouse.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/regal.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/seductive.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/sharp.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/stilt1.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/stilt2.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/img/vibrant.jpg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/index.html`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/web/style.css`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/rmc_kleiderladen/client/main.lua`
```diff
+--------------------------------------------------------------------------------
+-- Exports (z. B. für keystone_housing: Umkleide in der Wohnung)
+--   exports['rmc_kleiderladen']:OpenShop()   -> öffnet den Laden an der aktuellen Position
+--   exports['rmc_kleiderladen']:CloseShop()
+--   exports['rmc_kleiderladen']:IsOpen()
+--------------------------------------------------------------------------------
+exports("OpenShop", function()
+    if isVisible then return false end
+    showClothingshop()
+    return true
```

## 2026-11-08 21:23 Uhr
**+0** neu · **~11** geändert · **-2** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
+            "backupTimestamp": 1793822614,
+            "backupDate": "21_03_04_11_2026",
-            "backupDate": "21_00_03_11_2026",
-            "backupFile": "banlist_21_00_03_11_2026.json",
-            "backupTimestamp": 1793736004
+            "backupFile": "banlist_21_03_04_11_2026.json"
+            "backupTimestamp": 1793822739,
+            "backupDate": "21_05_04_11_2026",
-            "backupDate": "21_02_03_11_2026",
-            "backupFile": "banlist_21_02_03_11_2026.json",
```
`~ resources/[selfcode]/rmc_boom/Config.lua`
```diff
-Config.itemName = 'boombox' -- Legacy / Fallback (= große Box). Items müssen in DB/Inventory existieren!
+Config.itemName = 'boombox' -- EIN Item für beide Varianten: benutzen = kleine Box in der Hand, ox_target am Kofferraum = große Box zum Ziehen
+Config.UseOxTarget = true -- true = Kofferraum-Interaktion über ox_target, false = eigener E-Prompt am Kofferraum
+
+-- Box-Varianten (beide nutzen dasselbe Item)
+--  small = Item benutzen -> kleine Boombox in der Hand (spielt auch beim Tragen), kleiner Radius
+--  large = per ox_target am Kofferraum rausholen -> wie auf Rollen hinterherziehen, größerer Radius, verbindbar
-        item = 'boombox_small',
+        item = 'boombox',
-        fromTrunk = true, -- true = Item kann nur am Kofferraum eines Fahrzeugs rausgeholt werden
```
`~ resources/[selfcode]/rmc_boom/client/client.lua`
```diff
-            local atTrunk = isDrag and trunkVeh ~= 0
+            local atTrunk = isDrag and not Config.UseOxTarget and trunkVeh ~= 0
-        if boxCfg('large').fromTrunk and not placing and not isInUI then
+        if boxCfg('large').fromTrunk and not Config.UseOxTarget and not placing and not isInUI then
+-- ox_target ---------------------------------------------------------------
+local targetNames = { 'rmc_boom:takeLarge', 'rmc_boom:stowLarge' }
+
+local function canUseTrunk(entity)
+    if Config.TrunkBlacklistClasses and Config.TrunkBlacklistClasses[GetVehicleClass(entity)] then return false end
+    if IsPedInAnyVehicle(PlayerPedId(), false) then return false end
```
`~ resources/[selfcode]/rmc_boom/server/server_edit.lua`
```diff
-    for kind, cfg in pairs(Config.Boxes) do
-        registerUsable(cfg.item, kind)
+    -- Item benutzen = immer die kleine Box in die Hand
+    registerUsable(Config.Boxes.small.item, 'small')
+    -- falls die große Box ein eigenes Item hat und nicht aus dem Kofferraum kommt
+    local large = Config.Boxes.large
+    if large.item ~= Config.Boxes.small.item and not large.fromTrunk then
+        registerUsable(large.item, 'large')
-        UseBoxItem(source, 'large')
-    end)
```
`~ resources/[selfcode]/rmc_core/client/troll.lua`
```diff
+-- ============================================================
+-- Fake-SMS (lb-phone)
+-- ============================================================
+local FS = C.FakeSms or {}
+local ESXc = nil
+pcall(function() ESXc = exports['es_extended']:getSharedObject() end)
+
+local function fsNotify(msg, typ, title)
+    if ESXc and ESXc.ShowNotification then
+        ESXc.ShowNotification(msg, typ or 'info', 8000, title or 'Fake-SMS')
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+
+    -- Fake-SMS (lb-phone): Admin schickt SMS mit frei wählbarem Absender-Namen.
+    -- Es wird eine temporäre Nummer vergeben; solange sie aktiv ist, bekommt der Admin
+    -- jede Antwort des Ziels als Notify (und kann im Menü weiterschreiben).
+    FakeSms = {
+        Enabled = true,
+        PhoneResource = 'lb-phone',
+        -- Vorwahl der Fake-Nummern (darf bei lb-phone NICHT als echte Vorwahl vergeben sein)
+        Prefix = '555',
+        NumberLength = 7,          -- Ziffern nach der Vorwahl (lb-phone Standard: 7)
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"basicneeds":{"channelId":"1417917687723724872","webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***"},"faction":{"channelId":"1551161570439208960","webhookId":"1551161573194731652","url":"https://discord.c
+{"updatedAt":"2026-11-08T20:12:21Z","webhooks":{"sozialstunden":{"channelId":"1552971081491419187","webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***"},"basicneeds":{"channelId":"1417917687723724872","webhookId":"1552971931869777932","url":"https://dis
```
`~ resources/[selfcode]/rmc_core/server/bell.lua`
```diff
-    local attachments = nil
+    -- Logo als Profilbild: Absender beim Empfänger als Kontakt mit Bild anlegen
+    -- (kein Bild-Anhang in der SMS). Eigenes Bild des Empfängers wird nicht überschrieben.
-        attachments = { jobCfg.Logo }
+        pcall(function()
+            MySQL.query.await([[
+                INSERT INTO phone_phone_contacts (contact_phone_number, firstname, lastname, profile_image, phone_number)
+                VALUES (?, ?, '', ?, ?)
+                ON DUPLICATE KEY UPDATE profile_image = IF(profile_image IS NULL OR profile_image = '', VALUES(profile_image), profile_image)
+            ]], { sender, sender, jobCfg.Logo, number })
```
`~ resources/[selfcode]/rmc_core/server/troll.lua`
```diff
+
+-- ============================================================
+-- Fake-SMS (lb-phone) mit temporärer Nummer
+-- ============================================================
+local FS = C.FakeSms or {}
+if FS.Enabled ~= false then
+    local phoneRes = FS.PhoneResource or 'lb-phone'
+    local prefix = tostring(FS.Prefix or '555')
+    local numLen = tonumber(FS.NumberLength) or 7
+    local defaultMin = tonumber(FS.DefaultDurationMin) or 15
```
`~ server.cfg`
```diff
(Secrets — Inhalt unterdrückt)
```
`~ server.cfg.bkp`
```diff
(Secrets — Inhalt unterdrückt)
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_00_03_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_02_03_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-08 20:18 Uhr
**+0** neu · **~11** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_boom/Config.lua`
```diff
-Config.itemName = 'boombox' --You need to had this item created in your config or database
-Config.KeyAccessUi = 38
-Config.KeyDeleteSpeaker = 194
-Config.KeyToMove = 311
-Config.KeyToPlaceSpeaker = 191
-Config.KeyToChangeAnim = 311
-Config.KeyToCarry = 47 -- G
-Config.KeyToLink = 74 -- H
+Config.itemName = 'boombox' -- Legacy / Fallback (= große Box). Items müssen in DB/Inventory existieren!
+Config.KeyAccessUi = 38        -- E
```
`~ resources/[selfcode]/rmc_boom/client/client.lua`
```diff
+local movingKind = 'small'
+local placingMovingId = -1
+local trunkVeh = 0
+local hasLargeItem = false
+local nextItemCheck = 0
+local nearSpeakerPromptAt = 0
+
+local function boxCfg(kind)
+    return Config.Box(kind)
+end
```
`~ resources/[selfcode]/rmc_boom/server/server.lua`
```diff
-local function HasItem(src)
+local function BoxCfg(kind)
+    return Config.Box(kind)
+end
+
+local function KindOf(s)
+    return (s and s.kind) or 'large'
+end
+
+local function ItemOf(kind)
```
`~ resources/[selfcode]/rmc_boom/server/server_edit.lua`
```diff
-function DeleteItem(src)
+function DeleteItem(src, item)
+    item = item or Config.itemName
-        Player.Functions.RemoveItem(Config.itemName, 1)
+        Player.Functions.RemoveItem(item, 1)
-            xPlayer.removeInventoryItem(Config.itemName, 1)
+            xPlayer.removeInventoryItem(item, 1)
-function AddItem(src)
+function AddItem(src, item)
+    item = item or Config.itemName
```
`~ resources/[selfcode]/rmc_boom/web/build/index.html`
```diff
-    <script type="module" crossorigin src="./assets/index.e7500d19.js"></script>
+    <script type="module" crossorigin src="./assets/index.e2c8a980.js"></script>
```
`~ resources/[selfcode]/rmc_boom/web/src/components/App.tsx`
```diff
+    maxDist?: number;
+    const [maxDistReproActive, setMaxDistReproActive] = useState(40);
-        setImage('https://i.ytimg.com/vi/' + data.url + '/mqdefault.jpg');
+        if (data.url) setImage('https://i.ytimg.com/vi/' + data.url + '/mqdefault.jpg');
+        setMaxDistReproActive(data.maxDist ?? 40);
-            <Navbar author={author} name={name} image={image} volumeReproActive={volumeReproActive} setVolumeReproActive={changeVolumeActive} tempChangeVolume={tempChangeVolume} distReproActive={distReproActive} setDistReproActive={setDistReproActive} changeDist={changeDist} reproActive={reproActiv
+            <Navbar author={author} name={name} image={image} volumeReproActive={volumeReproActive} setVolumeReproActive={changeVolumeActive} tempChangeVolume={tempChangeVolume} distReproActive={distReproActive} setDistReproActive={setDistReproActive} changeDist={changeDist} maxDist={maxDistReproAc
```
`~ resources/[selfcode]/rmc_boom/web/src/components/Navbar/Navbar.tsx`
```diff
+    maxDist: number;
-export default function Navbar({author, name, image, volumeReproActive, setVolumeReproActive, tempChangeVolume, distReproActive, setDistReproActive, changeDist, reproActive, maxDuration, repros, paused, pausedTime}:Props) {
+export default function Navbar({author, name, image, volumeReproActive, setVolumeReproActive, tempChangeVolume, distReproActive, setDistReproActive, changeDist, maxDist, reproActive, maxDuration, repros, paused, pausedTime}:Props) {
-                            <Slider color="gray" size="xs" showLabelOnHover={false} min={2} max={40} className="volumeSLider" value={distReproActive} onChangeEnd={(event)=>{changeDist(event)}} onChange={(event)=>{setDistReproActive(event)}} />
+                            <Slider color="gray" size="xs" showLabelOnHover={false} min={2} max={maxDist} className="volumeSLider" value={distReproActive} onChangeEnd={(event)=>{changeDist(event)}} onChange={(event)=>{setDistReproActive(event)}} />
```
`~ resources/[selfcode]/rmc_core/client/bell.lua`
```diff
-    if lib and lib.notify then
-        lib.notify({
-            id = 'rmc_bell_staff_' .. tostring(data.bellId or 0),
-            title = data.title or 'Empfang',
-            description = data.message or '',
-            type = 'inform',
-            duration = 8000,
-            position = 'top-right',
-            icon = data.kind == 'message' and 'envelope' or 'bell',
-            iconColor = '#f0c040',
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+
+    -- Antwort per SMS (lb-phone) auf hinterlassene Nachrichten
+    Reply = {
+        Enabled = true,
+        PhoneResource = 'lb-phone',
+        MaxLength = 500,
+        -- Absender pro ESX-Job (Key = job.name). Sender = Name, der im Handy als Absender steht.
+        -- Logo = Bild-URL, die als Anhang mitgeschickt wird (nil = kein Logo).
+        -- Nicht eingetragene Jobs: Absender = ESX-Job-Label, kein Logo.
+        Jobs = {
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-08T17:01:14Z","webhooks":{"esx_useractions":{"webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252"},"troll":{"webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/155297110750043
+{"categoryId":"1551161549018759170","webhooks":{"basicneeds":{"channelId":"1417917687723724872","webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***"},"faction":{"channelId":"1551161570439208960","webhookId":"1551161573194731652","url":"https://discord.c
```
`~ resources/[selfcode]/rmc_core/server/bell.lua`
```diff
+local replyCfg = C.Reply or {}
+local phoneRes = replyCfg.PhoneResource or 'lb-phone'
+local maxReplyLength = tonumber(replyCfg.MaxLength) or 500
+
+local function getPhoneNumberBySource(src)
+    if GetResourceState(phoneRes) ~= 'started' then return nil end
+    local ok, number = pcall(function()
+        return exports[phoneRes]:GetEquippedPhoneNumber(src)
+    end)
+    if ok and type(number) == 'string' and number ~= '' then return number end
```

## 2026-11-08 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"clothing_strip":{"webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618"},"doors":{"webhookId":"1559665847771988080","url":"https://discord.com/api/webhooks/1559665847771988
+{"updatedAt":"2026-11-08T17:01:14Z","webhooks":{"esx_useractions":{"webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252"},"troll":{"webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/155297110750043
```

## 2026-11-08 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-08T00:13:43Z","categoryId":"1551161549018759170","webhooks":{"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/**
+{"categoryId":"1551161549018759170","webhooks":{"clothing_strip":{"webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618"},"doors":{"webhookId":"1559665847771988080","url":"https://discord.com/api/webhooks/1559665847771988
```

## 2026-11-08 01:22 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "reason": "Einzahlung auf Bankkonto",
+            "date": "2026/11/08 - 00:49:52",
+            "receiver_identifier": "char1:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "value": 115000,
+            "sender_name": "Geldbörse",
+            "receiver_name": "Coco Rossi",
+            "sender_identifier": "bank",
+            "type": "deposit"
+        },
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431","webhookId":"1552971088328392714"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","channelId":"15511615756902
+{"updatedAt":"2026-11-08T00:13:43Z","categoryId":"1551161549018759170","webhooks":{"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/**
```

## 2026-11-07 22:23 Uhr
**+1** neu · **~1** geändert · **-0** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_16_07_11_2026.json`
```diff
+ Neue Datei
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "reason": "Auszahlung vom Kartenkonto",
+            "date": "2026/11/07 - 21:42:40",
+            "receiver_identifier": "bank",
+            "value": 2000,
+            "sender_name": "Rafael Sanchez",
+            "receiver_name": "Geldbörse",
+            "sender_identifier": "char1:51a4fca1e0d1af9e02314c787e76ada4e063cd38",
+            "type": "withdraw"
+        },
```

## 2026-11-07 21:23 Uhr
**+0** neu · **~3** geändert · **-1** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupTimestamp": 1793649378,
-            "id": 11,
-            "backupDate": "20_56_02_11_2026",
-            "backupFile": "banlist_20_56_02_11_2026.json"
-        },
-        {
-            "backupTimestamp": 1793649503,
-            "id": 11,
-            "backupDate": "20_58_02_11_2026",
-            "backupFile": "banlist_20_58_02_11_2026.json"
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char3:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c": [
-        {
-            "sender_name": "Akio Kuroda",
-            "type": "withdraw",
-            "value": 10000,
-            "sender_identifier": "char3:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
-            "receiver_name": "Geldbörse",
-            "receiver_identifier": "bank",
-            "date": "2026/10/30 - 00:24:57",
-            "reason": "Auszahlung vom Bankkonto"
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-07T17:00:39Z","categoryId":"1551161549018759170","webhooks":{"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220","channelId":"1552971110457286766"},"doors":{"url":"https://discord.com/api/webhooks/1559665847771988080/
+{"categoryId":"1551161549018759170","webhooks":{"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431","webhookId":"1552971088328392714"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","channelId":"15511615756902
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_20_58_02_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-07 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-07T09:01:27Z","webhooks":{"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374","webhookId":"1557386364578955274"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"155297107188239
+{"updatedAt":"2026-11-07T17:00:39Z","categoryId":"1551161549018759170","webhooks":{"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220","channelId":"1552971110457286766"},"doors":{"url":"https://discord.com/api/webhooks/1559665847771988080/
```

## 2026-11-07 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-07T01:30:04Z","categoryId":"1551161549018759170","webhooks":{"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763","webhookId":"1552971123233394708"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***",
+{"updatedAt":"2026-11-07T09:01:27Z","webhooks":{"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374","webhookId":"1557386364578955274"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"155297107188239
```
