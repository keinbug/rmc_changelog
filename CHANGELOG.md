# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

## 2026-11-24 22:23 Uhr
**+3** neu · **~6** geändert · **-2** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_10_24_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_12_24_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-bridge/html/index.html`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "id": 11,
-            "backupDate": "21_54_19_11_2026",
-            "backupFile": "banlist_21_54_19_11_2026.json",
-            "backupTimestamp": 1795121677
-        },
-        {
-            "id": 11,
-            "backupDate": "21_56_19_11_2026",
-            "backupFile": "banlist_21_56_19_11_2026.json",
-            "backupTimestamp": 1795121802
```
`~ resources/[selfcode]/tms-bridge/README.md`
```diff
+### Ränge
+
+Beim Abgleich überträgt die Ressource auch alle Jobs mit ihren Rängen (ESX: `job_grades`, QBCore/Qbox: `Shared.Jobs`).
+Im MDT unter **Ränge & Rechte → Aus dem Spiel** übernimmst du die Ränge eines Jobs für eine Fraktion.
+
+### Mugshots
+
+Mit `Config.Mugshots = true` nimmt die Ressource einmal alle 24 Stunden das Kopfbild jedes Charakters auf, der online ist.
+Das Bild landet in der Datenbank des Panels und erscheint in der Akte. Auf dem Spielserver wird nichts gespeichert.
+Ohne Freigabe im Panel werden keine Bilder aufgenommen.
```
`~ resources/[selfcode]/tms-bridge/client.lua`
```diff
+-- ─── Mugshot ───────────────────────────────────────────────────────────────
+-- Der Server fordert höchstens einmal in 24 Stunden ein Bild an. Aufgenommen wird das Kopfbild des
+-- eigenen Charakters (wie im Pausemenü); die unsichtbare NUI-Seite wandelt es in ein JPEG um.
+
+local mugToken = nil
+
+RegisterNetEvent('tms-bridge:mugshot', function(token)
+  if mugToken then return end
+  mugToken = token
+  CreateThread(function()
```
`~ resources/[selfcode]/tms-bridge/config.lua`
```diff
+-- Mugshots: einmal alle 24 Stunden pro Charakter ein Kopfbild aufnehmen und an TMS senden.
+-- Gespeichert wird das Bild in der Datenbank des Panels. Gilt nur mit Freigabe im Panel (wie oben).
+Config.Mugshots = true
+
-Config.Notruf = false
+Config.Notruf = true
```
`~ resources/[selfcode]/tms-bridge/fxmanifest.lua`
```diff
-version '0.3.0'
+version '0.4.0'
+-- Unsichtbare Seite, die das Kopfbild des Charakters in ein JPEG umwandelt (Mugshots)
+ui_page 'html/index.html'
+files { 'html/index.html' }
+
```
`~ resources/[selfcode]/tms-bridge/server.lua`
```diff
+  -- Jobs mit ihren Rängen: ESX führt sie in der Datenbank, QBCore und Qbox in ihrer Konfiguration.
+  local okGrades = okVehicles and (function()
+    local out = {}
+    if layout == 'esx' then
+      local rows = query('SELECT g.job_name AS job, g.grade, g.label, j.label AS jobLabel FROM job_grades g LEFT JOIN jobs j ON j.name = g.job_name')
+      if not rows then return false end
+      for i = 1, #rows do
+        local r = rows[i]
+        if r.job ~= 'unemployed' then out[#out + 1] = { job = r.job, grade = tonumber(r.grade) or 0, label = r.label, jobLabel = r.jobLabel } end
+      end
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_54_19_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_56_19_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-24 21:23 Uhr
**+6** neu · **~0** geändert · **-0** gelöscht
`+ resources/[selfcode]/tms-bridge/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-bridge/client.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-bridge/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-bridge/endpoint.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-bridge/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-bridge/server.lua`
```diff
+ Neue Datei
```

## 2026-11-24 18:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/api_new/server/inventory.lua`
```diff
-    local ref
-        ref = owner and { id = id, owner = owner } or id
-    else
-        ref = (kind == 'trunk' and 'trunk' or 'glove') .. trim(id)
+        local ref = owner and { id = id, owner = owner } or id
+        local r = withTimeout(4000, function() return exports.ox_inventory:GetInventory(ref) end)
+        if r == nil then return nil, nil, 'ox_inventory hat das Inventar nicht rechtzeitig geladen' end
+        if r[1] and type(r[2]) == 'table' then return ref end
+        return nil
-    local r = withTimeout(4000, function() return exports.ox_inventory:GetInventory(ref) end)
```

## 2026-11-24 17:23 Uhr
**+2** neu · **~3** geändert · **-0** gelöscht
`+ resources/[selfcode]/api_new/fxmanifest.lua.bak-inventory`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/inventory.lua`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/inventory.lua',
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
-    Price     = 5000,
-    MaxAmount = 10,                 -- max. Stück pro Kauf
+    Price     = 12000,
+    MaxAmount = 5,                 -- max. Stück pro Kauf
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297
+{"webhooks":{"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"housing":{"url":"https://discord.com/api/webhooks/1570424984998912021/***","webhookId":"1570424984998912021","channelId":"1570424980183842916"
```

## 2026-11-24 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"esx":{"webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370"},"hotdog":{"webhookId":"1474547103081566412","url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979"},"
+{"webhooks":{"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297
```

## 2026-11-24 00:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"poster":{"channelId":"1560007812342489120","webhookId":"1560007815156998144","url":"https://discord.com/api/webhooks/1560007815156998144/***"},"txadmin":{"channelId":"1552989823604756600","webhookId":"1552989826213617715","url":"https://discord.com/a
+{"webhooks":{"esx":{"webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370"},"hotdog":{"webhookId":"1474547103081566412","url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979"},"
```

## 2026-11-23 22:23 Uhr
**+2** neu · **~1** geändert · **-2** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_06_23_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_09_23_11_2026.json`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupFile": "banlist_21_51_18_11_2026.json",
-            "id": 11,
-            "backupDate": "21_51_18_11_2026",
-            "backupTimestamp": 1795035117
-        },
-        {
-            "backupFile": "banlist_21_54_18_11_2026.json",
-            "id": 11,
-            "backupDate": "21_54_18_11_2026",
-            "backupTimestamp": 1795035242
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_51_18_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_54_18_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-23 21:23 Uhr
**+0** neu · **~3** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"einreise":{"webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431"},"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"155738635222
+{"categoryId":"1551161549018759170","webhooks":{"poster":{"channelId":"1560007812342489120","webhookId":"1560007815156998144","url":"https://discord.com/api/webhooks/1560007815156998144/***"},"txadmin":{"channelId":"1552989823604756600","webhookId":"1552989826213617715","url":"https://discord.com/a
```
`~ resources/[selfcode]/rmc_core/server/discord_config.lua`
```diff
-    Token = '***TOKEN***',
+    Token = '***TOKEN***',
```
`~ server.cfg`
```diff
(Secrets — Inhalt unterdrückt)
```

## 2026-11-23 20:23 Uhr
**+0** neu · **~7** geändert · **-0** gelöscht
`~ resources/[oresmon]/0r-radio/client/events.lua`
```diff
-playerSpawned = false
-PlayerData = {}
-AddEventHandler('onResourceStart', function(resource)
-    if resource ~= GetCurrentResourceName() then
-        return
-    end
-    local startTime = GetGameTimer()
-    while not CoreReady do 
-        Citizen.Wait(100)
-        if GetGameTimer() - startTime > 5000 then
```
`~ resources/[oresmon]/0r-radio/server/server.lua`
```diff
-local SpawnedObjects = {}
-local UsedObjectIds = {}
-local PlayerChannels = {} -- Server-side fallback tracker for SaltyChat
-
-RegisterUseableItem2(Config.RadioItem)
-if Config.JammerSettings.available then
-    RegisterUseableItem(Config.JammerSettings.item_name)
-end
-
-RegisterNetEvent('0R-radio:server:SetPlayerChannel', function(channel)
```
`~ resources/[oresmon]/0r-radio/web/build/assets/index-8e4836f8.css`
```diff
+.members-list-anchor{position:absolute;top:0;bottom:0;left:29px;display:flex;align-items:center;pointer-events:none;z-index:120}.members-list-box{position:relative;pointer-events:auto;width:135px;max-height:185px;overflow:hidden;display:flex;flex-direction:column}.members-list-box>div{max-height:18
+.text-\[\#FFD60A\]{--tw-text-opacity:1;color:rgb(255 214 10/var(--tw-text-opacity))}
```
`~ resources/[oresmon]/0r-radio/web/build/assets/index-b4b884cd.js`
```diff
-`,e.getElementsByTagName("head")[0].appendChild(t)),e.body&&Yc(e.body,"react-draggable-transparent-selection")}function F2(e){if(e)try{if(e.body&&Xc(e.body,"react-draggable-transparent-selection"),e.selection)e.selection.empty();else{const t=(e.defaultView||window).getSelection();t&&t.type!=="Caret
+`,e.getElementsByTagName("head")[0].appendChild(t)),e.body&&Yc(e.body,"react-draggable-transparent-selection")}function F2(e){if(e)try{if(e.body&&Xc(e.body,"react-draggable-transparent-selection"),e.selection)e.selection.empty();else{const t=(e.defaultView||window).getSelection();t&&t.type!=="Caret
```
`~ resources/[oresmon]/0r-radio/web/src/components/MemberList/index.tsx`
```diff
+import "../Radio/index.css";
-        const position = localStorage.getItem("membersMenuPosition");
+        const position = localStorage.getItem("membersMenuPositionV3");
-        localStorage.removeItem("membersMenuPosition");
+        localStorage.removeItem("membersMenuPositionV3");
-        localStorage.setItem("membersMenuPosition", JSON.stringify({ x: data.x, y: data.y }));
+        localStorage.setItem("membersMenuPositionV3", JSON.stringify({ x: data.x, y: data.y }));
-        <>
+        <div className="members-list-anchor">
-                <Transition unmount={false} show={visible} as={Fragment} enter="transition-all duration-300 ease-out" enterFrom="bottom-[-70%] opacity-0" enterTo="bottom-[5vh] opacity-1" leave="transition-all duration-300 ease-in" leaveFrom="bottom-[5vh] opacity-1" leaveTo="bottom-[-70%] opacity-0"
```
`~ resources/[oresmon]/0r-radio/web/src/components/Radio/index.css`
```diff
+
+/* Members list: mittig links */
+.members-list-anchor{position:absolute;top:0;bottom:0;left:29px;display:flex;align-items:center;pointer-events:none;z-index:120}
+.members-list-box{position:relative;pointer-events:auto;width:135px;max-height:185px;overflow:hidden;display:flex;flex-direction:column}
+.members-list-box>div{max-height:185px}
+.members-list-box .overflow-auto{min-height:0}
+
```
`~ resources/[sprache]/saltychat/client/client_open.lua`
```diff
-function onRadioStart()
-
-end
-
-function onRadioEnd()
-
-end
-
-function skipRadioChecks()
-    local state = LocalPlayer.state
```

## 2026-11-23 18:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-23T09:01:08Z","webhooks":{"housing":{"url":"https://discord.com/api/webhooks/1570424984998912021/***","channelId":"1570424980183842916","webhookId":"1570424984998912021"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585
+{"webhooks":{"einreise":{"webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431"},"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"155738635222
```

## 2026-11-23 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-22T23:00:53Z","categoryId":"1551161549018759170","webhooks":{"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924552"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***
+{"updatedAt":"2026-11-23T09:01:08Z","webhooks":{"housing":{"url":"https://discord.com/api/webhooks/1570424984998912021/***","channelId":"1570424980183842916","webhookId":"1570424984998912021"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585
```

## 2026-11-23 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-22T17:00:43Z","webhooks":{"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"faction":{"url":"https://discord.com/api/webhooks/155116157319473165
+{"updatedAt":"2026-11-22T23:00:53Z","categoryId":"1551161549018759170","webhooks":{"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924552"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***
```

## 2026-11-22 22:22 Uhr
**+2** neu · **~1** geändert · **-2** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_04_22_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_06_22_11_2026.json`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1795294988,
-            "backupDate": "21_48_17_11_2026",
-            "id": 11,
-            "backupFile": "banlist_21_48_17_11_2026.json",
-            "backupTimestamp": 1794948490
-        },
-        {
-            "backupDate": "21_50_17_11_2026",
-            "id": 11,
-            "backupFile": "banlist_21_50_17_11_2026.json",
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_48_17_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_50_17_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-22 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979","webhookId":"1474547103081566412"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370","
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-22T17:00:43Z","webhooks":{"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"faction":{"url":"https://discord.com/api/webhooks/155116157319473165
```

## 2026-11-22 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"esx_useractions":{"webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252"},"esx_resources":{"webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557
+{"categoryId":"1551161549018759170","webhooks":{"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979","webhookId":"1474547103081566412"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370","
```

## 2026-11-22 03:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "type": "deposit",
+            "receiver_identifier": "char3:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "receiver_name": "Kendrik Walker",
+            "date": "2026/11/22 - 02:43:07",
+            "value": 200000,
+            "sender_identifier": "bank",
+            "sender_name": "Geldbörse",
+            "reason": "Einzahlung auf Bankkonto"
+        },
```

## 2026-11-22 01:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5": [
-        {
-            "receiver_identifier": "cd_garage",
-            "reason": "Fahrzeugrückgabegebühr",
-            "value": 500,
-            "sender_identifier": "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5",
-            "type": "withdraw",
-            "receiver_name": "cd_garage",
-            "date": "2026/11/19 - 18:53:23",
-            "sender_name": "Jasmin Anderson"
```

## 2026-11-22 00:22 Uhr
**+0** neu · **~6** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/client/hotdog.lua`
```diff
-local Npcs = {}            -- [npcId] = { ped, standId, label, arrived }
+local Npcs = {}            -- [npcId] = { ped, standId, label }  (nur beim Besitzer, er steuert die Figur)
+local Bubbles = {}         -- [npcId] = { netId, label }         (bei allen Spielern: Sprechblase)
+-- Vernetzte Figur löschen (holt sich vorher die Kontrolle, falls sie gewandert ist)
+local function deletePed(ped)
+    if not DoesEntityExist(ped) then return end
+    if not NetworkHasControlOfEntity(ped) then
+        NetworkRequestControlOfEntity(ped)
+        local deadline = GetGameTimer() + 1000
+        while not NetworkHasControlOfEntity(ped) and GetGameTimer() < deadline do Wait(50) end
```
`~ resources/[selfcode]/rmc_core/client/troll.lua`
```diff
+-- Höhe des Figuren-Mittelpunkts über den Füßen (Standard-Ped: ca. 1,0 m).
+-- Schweben verkleinerte Spieler noch leicht, in der Config Troll.ScaleGroundOffset erhöhen.
+local GROUND_OFFSET = tonumber(C.ScaleGroundOffset) or 1.0
+--- [ped] = zuletzt gesetzte (verschobene) Position, damit nie doppelt verschoben wird.
+local LastScaledPos = {}
+
+    LastScaledPos[ped or 0] = nil
+
+    -- Die Figur wird um ihren Mittelpunkt (Hüfte, ca. 1 m über den Füßen) skaliert.
+    -- Ohne Ausgleich schweben verkleinerte Spieler und vergrößerte stecken im Boden.
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+    -- Spaß-Effekte im Untermenü „Spaß-Effekte“ (Dauer in Sekunden)
+    Extras = {
+        BetrunkenSec = 45,        -- Torkeln, verschwommene Sicht
+        TanzzwangSec = 15,        -- Ziel muss tanzen
+        KuhregenCount = 8,        -- Anzahl Kühe, die vom Himmel fallen
+        KuhregenCleanupSec = 20,  -- danach werden die Kühe gelöscht
+        GlatteisSec = 25,         -- Fahrzeug des Ziels hat kaum Grip
+        MondschwerkraftSec = 30,  -- Ziel springt/fährt wie auf dem Mond
+        StolperfluchSec = 30,     -- Ziel stolpert alle paar Sekunden
+        FeuerwerkBursts = 12,     -- Anzahl Raketen über dem Ziel (für alle sichtbar)
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"willkommen":{"channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005"},"frak":{"channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/*
+{"webhooks":{"esx_useractions":{"webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252"},"esx_resources":{"webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557
```
`~ resources/[selfcode]/rmc_core/server/hotdog.lua`
```diff
+-- ============================================
+-- NPC-Zustand eines Stands beenden
+-- ============================================
+
+-- Blendet die Sprechblase bei allen Spielern aus und vergisst den Passanten.
+-- deletePed = true löscht die Figur serverseitig (wenn der Besitzer nicht mehr da ist).
+local function releaseNpc(s, deletePed)
+    local npc = s.npc
+    if not npc then return end
+    s.npc = nil
```
`~ resources/[selfcode]/rmc_core/server/troll.lua`
```diff
+    -- Spaß-Effekte
+    betrunken      = true,
+    tanzzwang      = true,
+    rakete         = true,
+    kuhregen       = true,
+    glatteis       = true,
+    mondschwerkraft = true,
+    stolperfluch   = true,
+    feuerwerk      = true,
+    erdbeben       = true,
```

## 2026-11-21 23:23 Uhr
**+6** neu · **~8** geändert · **-0** gelöscht
`+ backups/okokNotify-orig-2026-11-21/config.lua`
```diff
+ Neue Datei
```
`+ backups/okokNotify-orig-2026-11-21/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ backups/okokNotify-orig-2026-11-21/web/scripts.js`
```diff
+ Neue Datei
```
`+ backups/okokNotify-orig-2026-11-21/web/sound.mp3`
```diff
+ Neue Datei
```
`+ backups/okokNotify-orig-2026-11-21/web/styles.css`
```diff
+ Neue Datei
```
`+ backups/okokNotify-orig-2026-11-21/web/ui.html`
```diff
+ Neue Datei
```
`~ resources/[okok]/okokNotify/web/scripts.js`
```diff
-let Config
-
-const containerElement = document.getElementById('container')
-let containerElementTopOffset = 0
-
-let notifications = []
-
-function addNotification(title, message, time, type, playSound) {
-	containerElementTopOffset = container.getBoundingClientRect().top
-
```
`~ resources/[okok]/okokNotify/web/styles.css`
```diff
-html {
-	font-size: calc(16 / 19.2 * 1vw);
-}
-
-@media (min-aspect-ratio: 16 / 9) {
-	html {
-		font-size: calc(16 / 10.8 * 1vh);
-	}
-}
-
```
`~ resources/[okok]/okokNotify/web/ui.html`
```diff
-<!DOCTYPE html>
-<html>
-	<head>
-		<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
-		<link rel="stylesheet" href="styles.css">
-	</head>
-	<body>
-		<div id="container"></div>
-		
-		<script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>
```
`~ resources/[selfcode]/rmc_core/client/afk.lua`
```diff
-        if Config.ClientNotify then
-            Config.ClientNotify('AFK', 'Du bist jetzt AFK. Nutze /afk um wieder da zu sein.', 3000, 'info', true)
-        end
+        ESX.ShowNotification('Du bist jetzt AFK. Nutze /afk um wieder da zu sein.', 'info', 3000, 'AFK')
-        if Config.ClientNotify then
-            Config.ClientNotify('AFK', 'Du bist wieder da.', 3000, 'success', true)
-        end
+        ESX.ShowNotification('Du bist wieder da.', 'success', 3000, 'AFK')
```
`~ resources/[selfcode]/rmc_core/client/hotdog.lua`
```diff
-    rmc_core – Hotdog Stand (ehemals rmc_hotdog)
-    Platzierbarer Imbiss-Stand mit Bestellungen.
-]]
-
-ESX = exports["es_extended"]:getSharedObject()
-
-if not Config.Hotdog or not Config.Hotdog.Enabled then return end
-
-local cfg = Config.Hotdog
-local ESX = nil
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+-- /hotdog – Platzierbarer Imbiss-Stand mit Speisekarte, Warteschlange,
+-- NPC-Kunden, Ruf/Statistik und Zahlung bar oder auf Rechnung (okokBilling)
-    MaxStands = 2,
+    MaxStands = 2,              -- gleichzeitig auf dem ganzen Server
+    MinStandDistance = 6.0,     -- Mindestabstand zwischen zwei Ständen
+    -- Platzieren
+    MaxPlaceDistance = 12.0,    -- Server lehnt weiter entfernte Positionen ab
+    ConfirmPlaceKey = 191,      -- Enter
+    CancelPlaceKey = 177,       -- Rücktaste / ESC / Rechtsklick
-    ConfirmPlaceKey = 191,
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-21T20:02:45Z","webhooks":{"esx":{"webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370"},"staff":{"webhookId":"1552971123233394708","url":"https://discord.com/api/w
+{"categoryId":"1551161549018759170","webhooks":{"willkommen":{"channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005"},"frak":{"channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/*
```
`~ resources/[selfcode]/rmc_core/server/hotdog.lua`
```diff
-    rmc_core – Hotdog Stand (ehemals rmc_hotdog)
-    Platzierbarer Imbiss-Stand mit Bestellungen.
-]]
-
-if not Config.Hotdog or not Config.Hotdog.Enabled then return end
-
-local cfg = Config.Hotdog
-local ESX = nil
-local Stands = {}
-local StandIdCounter = 0
```

## 2026-11-21 22:23 Uhr
**+3** neu · **~4** geändert · **-2** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_01_21_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_03_21_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/marriage.lua`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1795208376,
+    "lastBackup": 1795294988,
+            "backupDate": "21_48_17_11_2026",
-            "backupDate": "21_45_16_11_2026",
-            "backupTimestamp": 1794861929,
-            "backupFile": "banlist_21_45_16_11_2026.json"
+            "backupFile": "banlist_21_48_17_11_2026.json",
+            "backupTimestamp": 1794948490
+            "backupDate": "21_50_17_11_2026",
-            "backupDate": "21_47_16_11_2026",
```
`~ resources/[selfcode]/api_new/README.md`
```diff
+
+## Heiraten (rmc_core, Standesamt)
+
+Liest die Hochzeiten über den Export `exports[rmc_core]:GetMarriages({ after, limit })` (Tabelle `bc_marriages`). Der Discord-Bot holt darüber neue Hochzeiten ab und postet sie.
+
+### Neueste Hochzeiten / nur neue seit einer ID
+```bash
+curl "$API/marriage/list?limit=20" -H "X-API-Key: $KEY"
+curl "$API/marriage/list?after=51" -H "X-API-Key: $KEY"
+```
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/marriage.lua',
```
`~ resources/[selfcode]/rmc_core/server/marry.lua`
```diff
-end, false)
+end, false)
+
+-- ============================================
+-- EXPORTS (für api_new / Discord-Bot)
+-- ============================================
+--- Hochzeiten auslesen, älteste zuerst.
+---   exports['rmc_core']:GetMarriages({ after = 51, limit = 20 })
+---   after = nur Ehen mit höherer ID (optional), limit = 1-100 (Standard 20)
+--- Rückgabe: { latest = <höchste ID>, marriages = { { id, partner1, partner2, timestamp, active } } }
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_45_16_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_47_16_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-21 21:23 Uhr
**+0** neu · **~36** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/client/adminjail.lua`
```diff
-    if lib and lib.notify then
-        lib.notify({
-            title = "RedMoon-City",
-            description = msg,
-            type = "inform",
-            duration = 6500,
-            position = "top-right",
-        })
+    if ESX and ESX.ShowNotification then
+        ESX.ShowNotification(msg, "info", 6500, "RedMoon-City")
```
`~ resources/[selfcode]/rmc_core/client/ausweis.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ type = typ or 'inform', description = msg })
```
`~ resources/[selfcode]/rmc_core/client/bell.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ description = msg, type = typ or 'inform' })
```
`~ resources/[selfcode]/rmc_core/client/carradio.lua`
```diff
-    lib.notify({ type = kind, title = 'Auto-Radio', description = msg })
+    ESX.ShowNotification(msg, kind, nil, 'Auto-Radio')
```
`~ resources/[selfcode]/rmc_core/client/clothing_strip.lua`
```diff
-    -- Immer sichtbar: ox_lib Notify (Server hat ox_lib als Abhängigkeit)
-    if lib and lib.notify then
-        lib.notify({
-            title = 'Kleidung',
-            description = line,
-            type = 'inform',
-            duration = durationMs,
-            position = 'top',
-        })
+    if ESX and ESX.ShowNotification then
```
`~ resources/[selfcode]/rmc_core/client/coords.lua`
```diff
-        lib.notify({ type = 'error', title = 'Coords', description = ('Modell "%s" konnte nicht geladen werden.'):format(modelName) })
+        ESX.ShowNotification(('Modell "%s" konnte nicht geladen werden.'):format(modelName), 'error', nil, 'Coords')
-        lib.notify({ type = 'error', title = 'Coords', description = ('Ped-Modell "%s" konnte nicht geladen werden.'):format(modelName) })
+        ESX.ShowNotification(('Ped-Modell "%s" konnte nicht geladen werden.'):format(modelName), 'error', nil, 'Coords')
-        lib.notify({ type = 'error', title = 'Coords', description = ('Ped-Modell "%s" konnte nicht geladen werden.'):format(modelName) })
+        ESX.ShowNotification(('Ped-Modell "%s" konnte nicht geladen werden.'):format(modelName), 'error', nil, 'Coords')
-        lib.notify({ type = 'error', title = 'Coords', description = ('Anim "%s" konnte nicht geladen werden.'):format(animDict) })
+        ESX.ShowNotification(('Anim "%s" konnte nicht geladen werden.'):format(animDict), 'error', nil, 'Coords')
-        lib.notify({ type = 'error', title = 'Coords', description = 'Passout3-Ped konnte nicht erstellt werden.' })
+        ESX.ShowNotification('Passout3-Ped konnte nicht erstellt werden.', 'error', nil, 'Coords')
```
`~ resources/[selfcode]/rmc_core/client/death_owner_notify.lua`
```diff
-    if lib and lib.notify then
+    if ESX and ESX.ShowNotification then
+        -- okokNotify rendert HTML: Zeilenumbruch per <br>, Spielernamen escapen
+        local function esc(s)
+            return (tostring(s or "?"):gsub("&", "&amp;"):gsub("<", "&lt;"):gsub(">", "&gt;"))
+        end
-            desc = ("Täter: %s (ID %s)\nOpfer: %s (ID %s)\nGrund: %s"):format(
-                entry.killerName or "?",
+            desc = ("Täter: %s (ID %s)<br>Opfer: %s (ID %s)<br>Grund: %s"):format(
+                esc(entry.killerName),
```
`~ resources/[selfcode]/rmc_core/client/discord_id.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ type = typ, description = msg, duration = 6000 })
```
`~ resources/[selfcode]/rmc_core/client/flatbed.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ type = typ or 'inform', description = msg })
```
`~ resources/[selfcode]/rmc_core/client/frakmenu.lua`
```diff
-    lib.notify({ title = 'Fraktion', description = msg, type = kind or 'inform' })
+    ESX.ShowNotification(msg, kind or 'info', nil, 'Fraktion')
```
`~ resources/[selfcode]/rmc_core/client/freecam.lua`
```diff
-        if lib and lib.notify then
-            lib.notify({ type = 'error', title = 'Foto', description = 'Upload ist deaktiviert.' })
-        end
+        ESX.ShowNotification('Upload ist deaktiviert.', 'error', nil, 'Foto')
-        if lib and lib.notify then
-            lib.notify({ type = 'error', title = 'Foto', description = 'screenshot-basic muss installiert und gestartet sein.' })
-        end
+        ESX.ShowNotification('screenshot-basic muss installiert und gestartet sein.', 'error', nil, 'Foto')
-            if lib and lib.notify then
-                lib.notify({ type = 'error', title = 'Foto', description = 'Upload zeitüberschritten.' })
```
`~ resources/[selfcode]/rmc_core/client/gps_tracker.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ type = typ or 'inform', description = msg })
```
`~ resources/[selfcode]/rmc_core/client/handysteuer.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ title = 'Handysteuer', description = msg, type = typ or 'inform' })
-        ESX.ShowNotification(msg, typ or 'info', 5000)
+        ESX.ShowNotification(msg, typ or 'info', 5000, 'Handysteuer')
```
`~ resources/[selfcode]/rmc_core/client/heli_drop.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ type = typ or 'inform', description = msg })
```
`~ resources/[selfcode]/rmc_core/client/hostage.lua`
```diff
-    lib.notify({
-        type = "error",
-        title = t("title"),
-        description = message,
-        position = "bottom"
-    })
+    ESX.ShowNotification(message, "error", nil, t("title"))
```
`~ resources/[selfcode]/rmc_core/client/jammer.lua`
```diff
-    lib.notify({ title = 'Störsender', description = msg, type = nType or 'inform' })
+    ESX.ShowNotification(msg, nType or 'info', nil, 'Störsender')
```
`~ resources/[selfcode]/rmc_core/client/kfzsteuer.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ title = 'KFZ-Steuer', description = msg, type = typ or 'inform' })
-        ESX.ShowNotification(msg, typ or 'info', 5000)
+        ESX.ShowNotification(msg, typ or 'info', 5000, 'KFZ-Steuer')
```
`~ resources/[selfcode]/rmc_core/client/mechanic_shop.lua`
```diff
-        lib.notify({ type = 'error', description = T.NpcGone })
+        ESX.ShowNotification(T.NpcGone, 'error')
-        lib.notify({ type = 'success', description = (T.Bought):format(res.amount, Config.ItemLabel, res.total) })
+        ESX.ShowNotification((T.Bought):format(res.amount, Config.ItemLabel, res.total), 'success')
-        lib.notify({ type = 'error', description = T[res.reason] })
+        ESX.ShowNotification(T[res.reason], 'error')
-        lib.notify({ type = 'error', description = T.Error })
+        ESX.ShowNotification(T.Error, 'error')
```
`~ resources/[selfcode]/rmc_core/client/naturkatastrophen.lua`
```diff
-        lib.notify({ type = 'error', description = SS.Notify })
+        ESX.ShowNotification(SS.Notify, 'error')
```
`~ resources/[selfcode]/rmc_core/client/pawn.lua`
```diff
-    lib.notify(data)
+    if type(data) ~= 'table' then return end
+    ESX.ShowNotification(data.description or '', data.type or 'info', data.duration, data.title)
```
`~ resources/[selfcode]/rmc_core/client/plz.lua`
```diff
-    if lib and lib.notify then
-        lib.notify({
-            title = 'PLZ',
-            description = msg,
-            type = typ or 'inform',
-        })
+    if ESX and ESX.ShowNotification then
+        ESX.ShowNotification(msg, typ or 'info', nil, 'PLZ')
```
`~ resources/[selfcode]/rmc_core/client/saltychat.lua`
```diff
-    lib.notify({
-        title = 'SaltyChat',
-        description = desc,
-        type = nType or 'inform',
-    })
+    ESX.ShowNotification(desc, nType or 'info', nil, 'SaltyChat')
```
`~ resources/[selfcode]/rmc_core/client/schutzweste.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ type = typ, description = msg })
```
`~ resources/[selfcode]/rmc_core/client/seatbelt.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ type = typ, description = msg })
```
`~ resources/[selfcode]/rmc_core/client/sit.lua`
```diff
-    lib.notify({ type = kind, title = 'Sitz', description = description })
+    ESX.ShowNotification(description, kind, nil, 'Sitz')
```
`~ resources/[selfcode]/rmc_core/client/strafzettel.lua`
```diff
-                    lib.notify({
-                        title = 'LSPD',
-                        description = 'Kein Kennzeichen gefunden.',
-                        type = 'error'
-                    })
+                    ESX.ShowNotification('Kein Kennzeichen gefunden.', 'error', nil, 'LSPD')
-                    lib.notify({
-                        title = 'LSPD',
-                        description = 'Ungültiger Betrag.',
-                        type = 'error'
```
`~ resources/[selfcode]/rmc_core/client/troll.lua`
```diff
-                lib.notify({
-                    title = 'Troll',
-                    description = ('%s → ID %s'):format(actionLabel, serverId),
-                    type = 'success',
-                })
+                ESX.ShowNotification(('%s → ID %s'):format(actionLabel, serverId), 'success', nil, 'Troll')
-        lib.notify({ title = 'Troll', description = 'Keine Spieler online.', type = 'inform' })
+        ESX.ShowNotification('Keine Spieler online.', 'info', nil, 'Troll')
-                lib.notify({
-                    title = 'Troll · Größe',
```
`~ resources/[selfcode]/rmc_core/client/troll_rc.lua`
```diff
-    lib.notify({ title = 'Troll · Fernsteuerung', description = msg, type = typ or 'inform' })
+    ESX.ShowNotification(msg, typ or 'info', nil, 'Troll · Fernsteuerung')
```
`~ resources/[selfcode]/rmc_core/client/vehicledamage.lua`
```diff
-    elseif lib and lib.notify then
-        lib.notify({ type = typ, description = msg })
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-21T17:39:10Z","webhooks":{"clothing_strip":{"channelId":"1551161585614061618","webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"bell":{"channelId":"1471556817061544068","webhookId":"1471556835994767400","url":"https://discord.
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-21T20:02:45Z","webhooks":{"esx":{"webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370"},"staff":{"webhookId":"1552971123233394708","url":"https://discord.com/api/w
```
`~ resources/[selfcode]/rmc_core/server/carradio.lua`
```diff
-    TriggerClientEvent('ox_lib:notify', src, { type = 'error', title = 'Auto-Radio', description = msg })
+    TriggerClientEvent('esx:showNotification', src, msg, 'error', nil, 'Auto-Radio')
```
`~ resources/[selfcode]/rmc_core/server/freecam_photo.lua`
```diff
-    TriggerClientEvent('ox_lib:notify', src, {
-        type = typ or 'inform',
-        title = title or 'Foto',
-        description = description or '',
-        duration = duration or 5000,
-    })
+    TriggerClientEvent('esx:showNotification', src, description or '', typ or 'info', duration or 5000, title or 'Foto')
```
`~ resources/[selfcode]/rmc_core/server/jammer.lua`
```diff
-    TriggerClientEvent('ox_lib:notify', src, {
-        title = 'Störsender',
-        description = msg,
-        type = nType or 'inform',
-    })
+    TriggerClientEvent('esx:showNotification', src, msg, nType or 'info', nil, 'Störsender')
```
`~ resources/[selfcode]/rmc_core/server/saltychat.lua`
```diff
-            TriggerClientEvent('ox_lib:notify', targetId, {
-                title = 'SaltyChat',
-                description = 'Du wurdest von einem Teammitglied aus dem Funk entfernt.',
-                type = 'inform',
-            })
+            TriggerClientEvent('esx:showNotification', targetId, 'Du wurdest von einem Teammitglied aus dem Funk entfernt.', 'info', nil, 'SaltyChat')
-        TriggerClientEvent('ox_lib:notify', adminId, {
-            title = 'SaltyChat',
-            description = 'Mithören beendet – Ziel hat den Server verlassen.',
-            type = 'inform',
```
`~ resources/[selfcode]/rmc_core/server/strafzettel.lua`
```diff
+-- okokNotify (via ESX) rendert HTML -> Freitext escapen
+local function escHtml(s)
+    return (tostring(s or ''):gsub('&', '&amp;'):gsub('<', '&lt;'):gsub('>', '&gt;'))
+end
+
+-- Config.Notify-Eintrag ({ title, description, type, duration }) als ESX-Notification senden
+local function notifyCfg(target, data)
+    if type(data) ~= 'table' then return end
+    local typ = data.type == 'inform' and 'info' or (data.type or 'info')
+    TriggerClientEvent('esx:showNotification', target, data.description or '', typ, data.duration, data.title)
```
`~ resources/[selfcode]/rmc_core/server/webhook_setup.lua`
```diff
-    if lib and lib.notify then
-        TriggerClientEvent('ox_lib:notify', src, {
-            title = 'Discord-Setup',
-            description = msg,
-            type = 'inform',
-        })
-    end
+    TriggerClientEvent('esx:showNotification', src, msg, 'info', nil, 'Discord-Setup')
```

## 2026-11-21 19:23 Uhr
**+2** neu · **~3** geändert · **-25** gelöscht
`+ resources/[selfcode]/api_new/fxmanifest.lua.bak-lifeinvader`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/lifeinvader.lua`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/api_new/README.md`
```diff
+
+---
+
+## Lifeinvader (rmc_lifeinvader)
+
+Liest die Werbungen aus der Tabelle `lifeinvader_ads`. Der Discord-Bot holt darüber neue Werbungen ab und postet sie.
+
+### Neueste Werbungen / nur neue seit einer ID
+```bash
+curl "$API/lifeinvader/ads?limit=20" -H "X-API-Key: $KEY"
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/lifeinvader.lua',
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","channelId":"1551161570439208960","webhookId":"1551161573194731652"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585
+{"updatedAt":"2026-11-21T17:39:10Z","webhooks":{"clothing_strip":{"channelId":"1551161585614061618","webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"bell":{"channelId":"1471556817061544068","webhookId":"1471556835994767400","url":"https://discord.
```
`− resources/[selfcode]/rmc_api/client/admin_actions.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/client/phone.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/config/api_key.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/config/sakura_lager.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/main.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/admin.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/banking.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/billing.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/boss.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/einreise.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/hotel.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/inventory.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/items.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/medical.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/multichar.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/phone.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/players.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/refunds.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/sakura_lager.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/server_info.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/txadmin.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/modules/txadmin_profile.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/utils/auth.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_api/server/utils/response.lua`
```diff
- Gelöscht
```

## 2026-11-21 18:23 Uhr
**+1** neu · **~7** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_housing/server/presets.lua`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/rmc_housing/client/creator.lua`
```diff
+-- Nach dem Setzen des Eingangs: fragen, ob die echte Haustür dauerhaft verschlossen werden soll (über rmc_doors).
+-- Bei Ja visiert der Admin die Tür an (vorher schließen). Angelegt wird die Sperre erst mit dem Objekt.
+local function pickHouseDoor()
+    local leaves = {}
+    for i = 1, 2 do
+        local r = Appliances.pickExisting({ maxDist = 10.0,
+            hint = (i == 1 and '[Zielen] Haustür anvisieren' or '[Zielen] Zweiten Türflügel anvisieren') .. '  \n[Mausrad] Objekt wechseln  \n[E] Auswählen  \n[BACKSPACE] Abbrechen' })
+        if not r then break end
+        if r.spot or not r.model or r.model == 0 then
+            Notify('Ziele direkt auf die Tür, bis sie umrandet ist.', 'error')
```
`~ resources/[selfcode]/rmc_housing/client/main.lua`
```diff
+-- Mehrere Wohnungen hinter einem Eingang: erst die Wohnung wählen, dann das normale Tür-Menü
+function BuildingMenu(list)
+    local opts = {}
+    for _, p in ipairs(list) do
+        local desc, icon = 'Vermietet', 'door-closed'
+        if p.role == 'owner' then desc, icon = 'Dein Zuhause', 'house-user'
+        elseif p.role == 'key' then desc, icon = 'Du hast einen Schlüssel', 'key'
+        elseif p.status == 'free' then desc, icon = ('Zu vermieten · %s $ / Woche'):format(ESX.Math.GroupDigits(p.rent)), 'file-signature' end
+        opts[#opts + 1] = { title = p.label, description = desc, icon = icon, arrow = true, onSelect = function() DoorMenu(p) end }
+    end
```
`~ resources/[selfcode]/rmc_housing/config.lua`
```diff
-            -- Regendusche: mehrere durchgehende Wasserstrahlen von oben, fest über der Dusch-Stelle (bei jeder Dusche gleich).
-            -- Sprüht das Wasser in die falsche Richtung: rot = vec3(0.0, 0.0, 0.0) und height = 1.2 setzen (Wasser auf Brusthöhe).
+            -- Regendusche: mehrere durchgehende Wasserstrahlen, fest an der Dusch-Stelle (bei jeder Dusche gleich).
-                levels  = { 2.15, 1.45, 0.75 }, -- Höhen, auf denen Wasser startet · mehrere Ebenen = Wasser reicht bis zum Boden
-                rot     = vec3(180.0, 0.0, 0.0), -- 180 = Strahl zeigt nach unten
-                scale   = 1.2,                 -- Stärke je Strahl
+                -- Höhen über dem Boden, auf denen Wasser startet. Der Effekt schießt von dort gut 2 m nach OBEN und fällt dann herunter.
+                -- Darum tief starten: zu hohe Werte (z. B. 1.45 / 2.15) drücken das Wasser durch die Decke ins Stockwerk darüber.
+                -- Kommt oben immer noch Wasser durch: scale kleiner stellen. Reicht es nicht bis zum Duschkopf: scale etwas größer.
+                levels  = { 0.0, 0.25 },
```
`~ resources/[selfcode]/rmc_housing/fxmanifest.lua`
```diff
+    'server/presets.lua',
```
`~ resources/[selfcode]/rmc_housing/server/admin.lua`
```diff
+-- Dauerhaft verschlossene Haustür (rmc_doors): der Name enthält die Objekt-ID, darüber wird sie beim Löschen wiedergefunden
+local function houseDoorName(pid) return ('Housing #%d Haustür'):format(pid) end
+
+local function lockHouseDoor(pid, leaves, entrance)
+    if type(leaves) ~= 'table' or #leaves == 0 then return end
+    if GetResourceState('rmc_doors') ~= 'started' then return false, 'rmc_doors läuft nicht.' end
+    local list = {}
+    for i = 1, math.min(#leaves, 2) do
+        local v = type(leaves[i]) == 'table' and vec(leaves[i])
+        local model = v and tonumber(leaves[i].model)
```
`~ resources/[selfcode]/rmc_housing/shared/interiors.lua`
```diff
-customApt('custom_apt_1', 'Custom Apartment 1 · Eclipse Towers', 'a', vec4(-786.8663, 315.7642, 217.6385, 0.0))
-customApt('custom_apt_2', 'Custom Apartment 2 · Eclipse Towers', 'c', vec4(-786.9563, 315.6229, 187.9136, 0.0))
-customApt('custom_apt_3', 'Custom Apartment 3 · Eclipse Towers', 'b', vec4(-774.0126, 342.0428, 196.6864, 0.0))
+customApt('custom_apt_1', 'Eclipse Towers · Penthouse Suite 1', 'a', vec4(-786.8663, 315.7642, 217.6385, 0.0))
+customApt('custom_apt_2', 'Eclipse Towers · Penthouse Suite 3', 'c', vec4(-786.9563, 315.6229, 187.9136, 0.0))
+customApt('custom_apt_3', 'Eclipse Towers · Penthouse Suite 2', 'b', vec4(-774.0126, 342.0428, 196.6864, 0.0))
```
`~ resources/[selfcode]/rmc_housing/web/app.js`
```diff
-    label: '', type: 'Wohnung', address: '', zone: '', entrance: null, garageOn: false, garage: null,
+    label: '', type: 'Wohnung', address: '', zone: '', entrance: null, lockDoor: null, garageOn: false, garage: null,
+      ${D.entrance ? `<div class="hint" style="display:flex;justify-content:space-between;align-items:center;gap:10px;margin-top:8px"><span>${Array.isArray(D.lockDoor) && D.lockDoor.length ? `Haustür wird dauerhaft verschlossen (${D.lockDoor.length === 2 ? 'Doppeltür' : '1 Tür'})` : 'Haustür bl
+  if (el.hasAttribute('data-unlock-door')) { D.lockDoor = null; queueSync(); return renderCreator(); }
+      if (el.dataset.pos === 'entrance') { // Eingang gesetzt: im Spiel fragen, ob die Haustür verschlossen werden soll
+        syncDraft(); hide();
+        return post('creator:askDoor', { draft: D });
+      }
```

## 2026-11-21 17:23 Uhr
**+8** neu · **~12** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_housing/client/doors.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_missions/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_missions/client/cutscene.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_missions/client/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_missions/client/missions.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_missions/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_missions/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_missions/server/main.lua`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/rmc_doors/server/main.lua`
```diff
+
+---------------------------------------------------------------------
+-- Exports für andere Scripts (z. B. rmc_housing): Türen anlegen / entfernen
+---------------------------------------------------------------------
+local function insertDoor(door)
+    local inserted = MySQL.insert.await('INSERT INTO rmc_doors (name, data) VALUES (?, ?)', {
+        door.name, encodeDoor(door),
+    })
+    local id = tonumber(type(inserted) == 'table' and (inserted.insertId or inserted[1]) or inserted)
+    if not id then return nil end
```
`~ resources/[selfcode]/rmc_housing/client/creator.lua`
```diff
+-- Vorschlag für Name / Adresse / Bezirk aus der Position (Standard: da, wo der Admin steht).
+-- GTA kennt keine Hausnummern: die Nummer wird fest aus den Koordinaten gebildet, dieselbe Tür ergibt immer dieselbe Nummer.
+RegisterNUICallback('creator:getAddress', function(d, cb)
+    local p = type(d) == 'table' and tonumber(d.x) and tonumber(d.y) and tonumber(d.z) and d or myPos()
+    local hash = GetStreetNameAtCoord(p.x + 0.0, p.y + 0.0, p.z + 0.0)
+    local street = hash ~= 0 and GetStreetNameFromHashKey(hash) or ''
+    local zone = GetLabelText(GetNameOfZone(p.x + 0.0, p.y + 0.0, p.z + 0.0))
+    if not zone or zone == 'NULL' then zone = '' end
+    local address = ''
+    if street ~= '' then
```
`~ resources/[selfcode]/rmc_housing/client/garage.lua`
```diff
+    RestoreMinimap()
+        HideMinimap()
```
`~ resources/[selfcode]/rmc_housing/client/interior.lua`
```diff
+            -- Gruppen (nur eins wählbar): ist nichts gewählt, gilt der Standard der Gruppe
+            local chosen = {}
+            for _, set in ipairs(int.entitySets or {}) do
+                if set.group and d.sets and d.sets[set.key] then chosen[set.group] = true end
+            end
+            for _, set in ipairs(int.entitySets or {}) do
+                if set.group and set.default and not chosen[set.group] then ActivateInteriorEntitySet(id, set.key) end
+            end
```
`~ resources/[selfcode]/rmc_housing/client/main.lua`
```diff
-function OpenMarket(selected)
+-- single = true (an der Haustür): nur das gewählte Objekt zeigen, nicht den ganzen Mietmarkt
+function OpenMarket(selected, single)
-    OpenNui({ action = 'open', screen = 'market', data = data, selected = selected })
+    if single then
+        local only = {}
+        for _, p in ipairs(data.properties) do
+            if p.id == selected then only[1] = p end
+        end
+        if not only[1] then return notify('Für dieses Objekt gibt es kein Angebot.', 'error') end
```
`~ resources/[selfcode]/rmc_housing/config.lua`
```diff
+        bunker = 800, clubhouse = 550, lab = 600, warehouse = 400,
+        hangar = 1200, facility = 1500, nightclub = 1100,
+-- Türen im Interior, die der Admin unter "Punkte bearbeiten" verschließen oder löschen kann
+Config.Doors = { max = 20 }
+
+-- Minimap ausblenden, solange man in einer Wohnung oder Hausgarage ist (beim Verlassen kommt sie zurück)
+Config.HideMinimapInside = true
+
```
`~ resources/[selfcode]/rmc_housing/fxmanifest.lua`
```diff
+    'client/doors.lua',
```
`~ resources/[selfcode]/rmc_housing/server/admin.lua`
```diff
+-- Verschlossene / gelöschte Türen im Interior: { model, x, y, z, h, mode = 'lock' | 'remove' }
+local function cleanDoors(list, spawn)
+    local out = {}
+    if type(list) ~= 'table' then return out end
+    for _, d in ipairs(list) do
+        local v = type(d) == 'table' and vec(d)
+        local model = v and tonumber(d.model)
+        if model and model ~= 0 and #out < Config.Doors.max
+            and #(vector3(v.x, v.y, v.z) - vector3(spawn.x, spawn.y, spawn.z)) <= 80.0 then
+            out[#out + 1] = { model = math.floor(model), x = v.x, y = v.y, z = v.z, h = (tonumber(d.h) or 0.0) + 0.0,
```
`~ resources/[selfcode]/rmc_housing/shared/interiors.lua`
```diff
+---------------------------------------------------------------------
+-- Story-Häuser & Motel (liegen in der Welt bzw. sind immer geladen, bob74_ipl räumt sie auf)
+---------------------------------------------------------------------
+static('motel',           'Motelzimmer',                    'lowend',  'house', 'lowend',  vec4(152.2605, -1004.471, -98.99999, 0.0))
+static('sp_michael',      'Villa · Rockford Hills',         'stilt',   'house', 'highend', vec4(-813.603, 179.474, 72.1548, 0.0))
+static('sp_franklin',     'Villa · 3671 Whispymound Drive', 'stilt',   'house', 'stilt1',  vec4(7.11903, 536.615, 176.028, 0.0))
+static('sp_franklin_aunt','Haus · Forum Drive',             'medium',  'house', 'medium',  vec4(-9.96562, -1438.54, 31.1015, 0.0))
+static('sp_trevor',       'Trailer · Sandy Shores',         'lowend',  'house', 'lowend',  vec4(1972.61, 3817.04, 33.4283, 0.0))
+static('sp_floyd',        'Apartment · Vespucci Beach',     'medium',  'house', 'medium',  vec4(-1150.703, -1520.713, 10.633, 0.0))
+static('sp_lester',       'Haus · El Burro Heights',        'lowend',  'house', 'lowend',  vec4(1273.9, -1719.305, 54.771, 0.0))
```
`~ resources/[selfcode]/rmc_housing/web/app.js`
```diff
-  if (m.screen === 'market') openMarket(m.data, m.selected);
+  if (m.screen === 'market') openMarket(m.data, m.selected, m.single);
-function openMarket(data, selected) {
+// single: an der Haustür geöffnet, es gibt nur dieses eine Objekt (ohne Liste, Suche und Filter)
+function openMarket(data, selected, single) {
+  S.mSingle = !!single;
+  $('#v-market').classList.toggle('single', S.mSingle);
+  $('#m-eyebrow').textContent = S.mSingle ? 'Mietangebot' : 'Immobilienbüro';
+  $('#m-title').textContent = S.mSingle ? ((list[0] || {}).label || 'Objekt') : 'Häuser & Wohnungen mieten';
+  if (S.mSingle) { // Suche/Filter vom letzten Besuch im Büro dürfen das Objekt nicht ausblenden
```
`~ resources/[selfcode]/rmc_housing/web/index.html`
```diff
-        <div><div class="eyebrow">Immobilienbüro</div><h2>Häuser &amp; Wohnungen mieten</h2></div>
+        <div><div class="eyebrow" id="m-eyebrow">Immobilienbüro</div><h2 id="m-title">Häuser &amp; Wohnungen mieten</h2></div>
```
`~ resources/[selfcode]/rmc_housing/web/style.css`
```diff
+
+/* Mietangebot an der Haustür: nur dieses eine Objekt, ohne Liste */
+#app #v-market.single{max-width:540px}
+#v-market.single .market{grid-template-columns:1fr;height:auto;max-height:calc(94vh - 84px)}
+#v-market.single .m-list{display:none}
```

## 2026-11-21 16:23 Uhr
**+0** neu · **~12** geändert · **-0** gelöscht
`~ resources/[devcore]/devcore_smoke/configs/config.lua`
```diff
-        ESX.ShowNotification(message, 2000, type) -- Default ESX Notify
+        ESX.ShowNotification(message, type or 'info', 5000) -- (text, notifyType, length)
```
`~ resources/[manuell_start]/ox_inventory/client.lua`
```diff
+	-- data.paymentMethod ('cash' | 'card') kommt vom Bar/Karte-Umschalter der NUI; der Server prueft die Angabe
```
`~ resources/[manuell_start]/ox_inventory/data/shops.lua`
```diff
+		allowCard = true, -- Kartenzahlung (Bank) erlaubt; false/entfernen = nur Bar
+		allowCard = true, -- Kartenzahlung (Bank) erlaubt; false/entfernen = nur Bar
+		allowCard = true, -- Kartenzahlung (Bank) erlaubt; false/entfernen = nur Bar
+        allowCard = true, -- Kartenzahlung (Bank) erlaubt; false/entfernen = nur Bar
+        allowCard = true, -- Kartenzahlung (Bank) erlaubt; false/entfernen = nur Bar
+        allowCard = true, -- Kartenzahlung (Bank) erlaubt; false/entfernen = nur Bar
+        allowCard = true, -- Kartenzahlung (Bank) erlaubt; false/entfernen = nur Bar
+        allowCard = true, -- Kartenzahlung (Bank) erlaubt; false/entfernen = nur Bar
+		allowCard = true, -- Kartenzahlung (Bank) erlaubt; false/entfernen = nur Bar
```
`~ resources/[manuell_start]/ox_inventory/locales/de.json`
```diff
+  "ui_pay_cash": "Bar",
+  "ui_pay_card": "Karte",
+  "shop_no_card": "Du hast keine Bank Karte dabei",
+  "shop_card_declined": "Kartenzahlung abgelehnt – nicht genug Guthaben auf dem Konto",
+  "paid_by_card": " (Karte)",
```
`~ resources/[manuell_start]/ox_inventory/locales/en.json`
```diff
+  "ui_pay_cash": "Cash",
+  "ui_pay_card": "Card",
+  "shop_no_card": "You don't have a bank card with you",
+  "shop_card_declined": "Card declined – insufficient bank balance",
+  "paid_by_card": " (card)",
```
`~ resources/[manuell_start]/ox_inventory/modules/shops/server.lua`
```diff
+			allowCard = properties.allowCard,
+		allowCard = shop.allowCard,
-local function canAffordItem(inv, currency, price)
+---Bankkonto des Spielers (ESX) fuer Kartenzahlung.
+local function getBankBalance(inv)
+	local player = server.GetPlayerFromId and server.GetPlayerFromId(inv.id)
+	local account = player and player.getAccount and player.getAccount('bank')
+
+	return player, account and account.money or 0
+end
```
`~ resources/[manuell_start]/ox_inventory/web/build/assets/index.css`
```diff
+
+.inventory-control .inventory-control-payment{display:flex;width:100%;gap:4px;padding:4px;box-sizing:border-box;background-color:#0c0c0c66;border-radius:4px}.inventory-control .inventory-control-payment-button{flex:1;color:#ffffff99;text-transform:uppercase;background-color:transparent;border:none;
```
`~ resources/[manuell_start]/ox_inventory/web/build/assets/index.js`
```diff
-`).replace(Md,``)}function Pd(e,t){return t=Nd(t),Nd(e)===t}function Z(e,t,n,r,a,o){switch(n){case`children`:typeof r==`string`?t===`body`||t===`textarea`&&r===``||Gt(e,r):(typeof r==`number`||typeof r==`bigint`)&&t!==`body`&&Gt(e,``+r);break;case`className`:kt(e,`class`,r);break;case`tabIndex`:kt(
+`).replace(Md,``)}function Pd(e,t){return t=Nd(t),Nd(e)===t}function Z(e,t,n,r,a,o){switch(n){case`children`:typeof r==`string`?t===`body`||t===`textarea`&&r===``||Gt(e,r):(typeof r==`number`||typeof r==`bigint`)&&t!==`body`&&Gt(e,``+r);break;case`className`:kt(e,`class`,r);break;case`tabIndex`:kt(
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-21T09:00:58Z","webhooks":{"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"basicneeds":{"url":"https://discord.com/api/webhooks/155297193186977
+{"categoryId":"1551161549018759170","webhooks":{"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","channelId":"1551161570439208960","webhookId":"1551161573194731652"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585
```
`~ resources/[selfcode]/rmc_housing/client/garage.lua`
```diff
+    ClearInside()
+    MarkInside(p.id, data.layout.entry, true)
```
`~ resources/[selfcode]/rmc_housing/client/main.lua`
```diff
+---------------------------------------------------------------------
+-- Merker "bin drinnen": übersteht Logout, Crash, Script- und Server-Neustart
+---------------------------------------------------------------------
+local INSIDE_KVP = 'rmch_inside'
+
+-- at = Position im Interior (Spawn), damit ein veralteter Merker später nicht greift
+function MarkInside(pid, at, garage)
+    SetResourceKvp(INSIDE_KVP, json.encode({ who = ESX.GetPlayerData().identifier, pid = pid, garage = garage == true,
+        x = at.x, y = at.y, z = at.z }))
+end
```
`~ resources/[selfcode]/rmc_housing/server/main.lua`
```diff
+WakePending = {}  -- [src] = propertyId (darf nach dem Login einmalig direkt im Haus aufwachen)
-    if mode ~= 'admin' and distTo(src, p.entrance) > 8.0 then
+    if mode == 'wake' then
+        -- nach dem Login im eigenen Zuhause aufwachen: nur mit Freigabe aus rmc_housing:recover, dafür ohne Tür-Abstand
+        if WakePending[src] ~= pid then return false, 'Aufwachen im Haus nicht möglich.' end
+        WakePending[src] = nil
+        mode = 'enter'
+    elseif mode ~= 'admin' and distTo(src, p.entrance) > 8.0 then
-lib.callback.register('rmc_housing:recover', function(src)
+-- Spieler hat sich im Interior ausgeloggt: zurück an die Tür.
```

## 2026-11-21 15:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/server/discord_config.lua`
```diff
-    Token = '***TOKEN***',
+    Token = '***TOKEN***',
```

## 2026-11-21 14:22 Uhr
**+0** neu · **~0** geändert · **-6** gelöscht
`− resources/[selfcode]/api_new/fxmanifest.lua.bak-refunds`
```diff
- Gelöscht
```
`− resources/[selfcode]/api_new/fxmanifest.lua.bak-rolesync`
```diff
- Gelöscht
```
`− resources/[selfcode]/api_new/fxmanifest.lua.bak-screen`
```diff
- Gelöscht
```
`− resources/[selfcode]/api_new/fxmanifest.lua.bak-txadmin`
```diff
- Gelöscht
```
`− resources/[selfcode]/api_new/settings.lua.bak-rolesync`
```diff
- Gelöscht
```
`− resources/[selfcode]/api_new/settings.lua.bak-txadmin`
```diff
- Gelöscht
```

## 2026-11-21 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-20T23:00:42Z","webhooks":{"faction":{"channelId":"1551161570439208960","webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"troll":{"channelId":"1552971103910236172","webhookId":"155297110750043
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-21T09:00:58Z","webhooks":{"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"basicneeds":{"url":"https://discord.com/api/webhooks/155297193186977
```

## 2026-11-21 00:22 Uhr
**+0** neu · **~3** geändert · **-0** gelöscht
`~ resources/[selfcode]/lb-tvcast/client/screen.lua`
```diff
+-- Geometrie: Fernseher finden, Form der Bildfläche erkennen, Zielmodus.
+--
+-- Die Form wird über die Kollision des Objekts ertastet: vom Startpunkt aus wird in alle
+-- vier Richtungen so weit gegangen, bis die Fläche endet (Kante, Stufe oder anderes Objekt).
-local PROBE = 0.8       -- so weit vor/hinter der vermuteten Fläche wird nach der echten Oberfläche gesucht
+local PROBE = 1.2         -- so weit vor/hinter der vermuteten Fläche wird nach der Oberfläche gesucht
-local COLUMNS = 10      -- Unterteilung bei gewölbten Flächen
+local COLUMNS = 10        -- Unterteilung bei gewölbten Flächen
+local EDGE_STEP = 0.05    -- Schrittweite beim Abtasten der Kanten
+local EDGE_TOLERANCE = 0.02 -- ab dieser Stufe gilt die Fläche als zu Ende
```
`~ resources/[selfcode]/lb-tvcast/config.lua`
```diff
-Config.ScreenInset = 0.06        -- Rand (Anteil), der bei erkannten TV-Modellen für den Rahmen abgezogen wird
+Config.ScreenFit   = 'contain'    -- 'contain' = Bild bleibt 16:9 und wird in die erkannte Fläche eingepasst
+                                  -- 'stretch' = Bild füllt die erkannte Fläche komplett (kann verzerren)
+Config.ScreenInset = 0.06       -- Rand (Anteil), der bei erkannten TV-Modellen für den Rahmen abgezogen wird
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557386346782265425","webhookId":"1557386349395583076"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","channelId":"15529898236
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-20T23:00:42Z","webhooks":{"faction":{"channelId":"1551161570439208960","webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"troll":{"channelId":"1552971103910236172","webhookId":"155297110750043
```

## 2026-11-20 23:23 Uhr
**+0** neu · **~8** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_housing/README.md`
```diff
-- **Dusche:** *Gerät aufstellen* → *Dusche* → *Bestehendes Objekt auswählen* → auf den **Boden der Dusche** zielen und „Diese Stelle“ mit `E` bestätigen.
-  Danach `ox_target` → *Duschen*: Die Figur läuft hin, zieht sich aus (nur `esx_skin`), duscht 20 Sek. und ist danach sauber (Blut/Dreck weg) und nass.
+- **Dusche:** *Gerät aufstellen* → *Dusche* → *Bestehendes Objekt auswählen*. Schritt 1: die **Bedien-Stelle** (ox_target) setzen, z. B. Armatur oder Wand. Schritt 2: die **Wasser-Stelle** setzen, also den Boden unter dem Duschkopf (max. 3 m von der Bedien-Stelle).
+  Danach `ox_target` → *Duschen*: Die Figur läuft zur Wasser-Stelle, duscht 20 Sek. unter der Regendusche und ist danach sauber (Blut/Dreck weg) und nass.
```
`~ resources/[selfcode]/rmc_housing/client/appliances.lua`
```diff
-local KIND_DESC = { oven = 'z. B. TK-Pizza backen', shower = 'Dusche im Bad anvisieren, dort wird geduscht' }
+local KIND_DESC = { oven = 'z. B. TK-Pizza backen', shower = 'Erst die Bedien-Stelle (ox_target), dann die Wasser-Stelle setzen' }
-            description = kind == 'shower' and 'Die Dusche im Bad anvisieren · „Diese Stelle“ = hier wird geduscht'
+            description = kind == 'shower' and 'Armatur oder Wand anvisieren · danach setzt du die Wasser-Stelle'
+    local r
-        local r = Appliances.pickExisting()
+        r = Appliances.pickExisting(kind == 'shower' and {
+            hint = 'Schritt 1/2 · Bedien-Stelle (ox_target)  \n[Zielen] Armatur / Wand anvisieren  \n[Mausrad] Objekt / „Diese Stelle“ wechseln  \n[E] Auswählen  \n[BACKSPACE] Abbrechen' } or nil)
-        return r
+    else
```
`~ resources/[selfcode]/rmc_housing/client/creator.lua`
```diff
-    if save and e.dirty then
+    if save then -- immer speichern: Admin-Punkte ersetzen dabei die eigenen Punkte des Mieters
-    opts[#opts + 1] = { title = Edit.dirty and 'Speichern & zurück' or 'Fertig & zurück', icon = 'floppy-disk', onSelect = function() stopEdit(true) end }
+    opts[#opts + 1] = { title = 'Speichern & zurück', icon = 'floppy-disk', description = 'Deine Punkte gelten danach für alle · eigene Punkte des Mieters werden ersetzt', onSelect = function() stopEdit(true) end }
-    if not lib.callback.await('rmc_housing:admin:preview', false, true) then return end
+    local okPrev, inside = lib.callback.await('rmc_housing:admin:preview', false, true, p.id)
+    if not okPrev then return end
+    if inside then Notify(('Du bist in der Dimension des Hauses · %d Spieler drin.'):format(inside), 'inform') end
```
`~ resources/[selfcode]/rmc_housing/client/main.lua`
```diff
-local function boot()
+-- restarted = true: das Script wurde neu gestartet (kein Login)
+local function boot(restarted)
-    -- im Interior ausgeloggt? -> zurück vor die Tür
+    -- im Interior ausgeloggt oder Script neu gestartet? -> zurück vor die Tür
-                notify('Du bist vor deiner Tür aufgewacht.', 'inform')
+                if restarted then
+                    ESX.ShowNotification('Du wurdest wegen eines Neustarts aus dem Haus entfernt.')
+                else
+                    notify('Du bist vor deiner Tür aufgewacht.', 'inform')
```
`~ resources/[selfcode]/rmc_housing/config.lua`
```diff
-        -- Dusche: am einfachsten "Bestehendes Objekt auswählen" → die Dusche im Bad anvisieren ("Diese Stelle").
+        -- Dusche: "Bestehendes Objekt auswählen" → erst die Bedien-Stelle (ox_target), dann die Wasser-Stelle (Boden unter dem Duschkopf) setzen.
-            undress = true,      -- zum Duschen ausziehen (nur mit Config.Clothing.provider = 'esx_skin'), danach wieder anziehen
+            undress = false,     -- zum Duschen ausziehen (nur mit Config.Clothing.provider = 'esx_skin'), danach wieder anziehen
-            particle = { dict = 'core', name = 'ent_sht_water', scale = 1.0, height = 1.1, interval = 350 }, -- Wasser über dem Kopf
+            -- Regendusche: mehrere durchgehende Wasserstrahlen von oben, fest über der Dusch-Stelle (bei jeder Dusche gleich).
+            -- Sprüht das Wasser in die falsche Richtung: rot = vec3(0.0, 0.0, 0.0) und height = 1.2 setzen (Wasser auf Brusthöhe).
+            particle = {
+                dict = 'core', name = 'ent_sht_water',
+                streams = 9,                   -- Anzahl Strahlen je Ebene (1 in der Mitte, Rest im Kreis) · mehr = mehr Wasser
```
`~ resources/[selfcode]/rmc_housing/server/admin.lua`
```diff
+    -- Admin-Punkte haben Vorrang: für jeden Punkt, den der Admin gesetzt hat, wird der eigene Punkt des Mieters gelöscht
+    local l, cleared = Leases[p.id], 0
+    if l and l.points then
+        for _, k in ipairs(POINT_KEYS) do
+            if points[k] and l.points[k] then l.points[k] = nil; cleared = cleared + 1 end
+        end
+        if cleared > 0 then Housing.saveLease(l) end
+    end
-    return true, 'Punkte gespeichert.'
+    return true, cleared > 0 and ('Punkte gespeichert. %d eigene(r) Punkt(e) des Mieters ersetzt.'):format(cleared) or 'Punkte gespeichert.'
```
`~ resources/[selfcode]/rmc_housing/server/appliances.lua`
```diff
+    elseif a.kind == 'shower' and type(a.water) == 'table' then
+        -- eigene Wasser-Stelle (Boden unter dem Duschkopf): dort steht man und dort kommt das Wasser herunter
+        local wx, wy, wz = tonumber(a.water.x), tonumber(a.water.y), tonumber(a.water.z)
+        if wx and wy and wz and #(vector3(wx, wy, wz) - vector3(x, y, z)) <= 3.0 then
+            out.water = { x = round(wx, 3), y = round(wy, 3), z = round(wz, 3) }
+        end
-        out[#out + 1] = { id = a.id, kind = a.kind, model = a.model, existing = a.existing, spot = a.spot, x = a.x, y = a.y, z = a.z, h = a.h,
+        out[#out + 1] = { id = a.id, kind = a.kind, model = a.model, existing = a.existing, spot = a.spot, x = a.x, y = a.y, z = a.z, h = a.h, water = a.water,
-    Showers[key] = { src = src, untilAt = os.time() + seconds + 4 }
-    Housing.forInside(pid, function(p) TriggerClientEvent('rmc_housing:shower', p, pid, a.id, src, true, seconds + 4) end)
```
`~ resources/[selfcode]/rmc_housing/server/main.lua`
```diff
+    while not Housing.ready do Wait(100) end
+
+    -- Script-Neustart: der Routing-Bucket bleibt erhalten und verrät, in welchem Objekt (Wohnung / Garage) der Spieler war
+    local bucket = GetPlayerRoutingBucket(src)
+    local hp, gp = Properties[bucket - Config.BucketOffset], Properties[bucket - Config.Garage.bucketOffset]
+    Inside[src], AdminInside[src], CamViewers[src] = nil, nil, nil
+    if bucket ~= 0 then SetPlayerRoutingBucket(src, 0) end
+    if hp then LastInside[x.identifier] = nil return hp.entrance end
+    if gp then LastInside[x.identifier] = nil return gp.garage or gp.entrance end
+
```
