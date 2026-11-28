# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

## 2026-11-28 15:23 Uhr
**+2** neu · **~6** geändert · **-8** gelöscht
`+ resources/[lb]/lb-phone/migrate_fixed_numbers.sql`
```diff
+ Neue Datei
```
`+ resources/[lb]/lb-phone/server/custom/frameworks/esx/nameNumbers.lua`
```diff
+ Neue Datei
```
`~ resources/[brutal]/brutal_ambulancejob/sv_utils.lua`
```diff
-local YourWebhook = 'https://discord.com/api/webhooks/1433556978243862619/***'  -- help: https://docs.brutalscripts.com/site/others/discord-webhook
-
-function GetWebhook()
-    return YourWebhook
-end
-
-function notification(source, title, text, time, type)
-    if Config.BrutalNotify then
-        TriggerClientEvent('brutal_notify:SendAlert', source, title, text, time, type)
-    else
```
`~ resources/[lb]/lb-phone/client/custom/frameworks/esx/esx.lua`
```diff
+        if not Config.Item.Unique then
+            AwaitCallback("nameNumber:sync")
+        end
+
+if not Config.Item.Unique then
+    AwaitCallback("nameNumber:sync") -- hand over the number of a deleted character with the same name before the phone loads
+end
+
```
`~ resources/[lb]/lb-phone/client/custom/frameworks/esx/item.lua`
```diff
+-- Reload the phone when the player receives a phone item again (no relog needed)
+if Config.Item.Require and not Config.Item.Unique then
+    local hadPhoneItem
+    local reloading = false
+
+    CreateThread(function()
+        while not FrameworkLoaded do
+            Wait(500)
+        end
+
```
`~ resources/[lb]/lb-phone/config/config.lua`
```diff
-Config.Item.Unique = true -- should each phone be unique? https://docs.lbscripts.com/phone/configuration/#unique-phones
+Config.Item.Unique = false -- should each phone be unique? https://docs.lbscripts.com/phone/configuration/#unique-phones
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-28T09:00:37Z","webhooks":{"esx_chat":{"webhookId":"1557386337580220497","channelId":"1557386335512305664","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"doors":{"webhookId":"1559665847771988080","channelId":"15596658453309
+{"webhooks":{"doors":{"webhookId":"1559665847771988080","channelId":"1559665845330907296","url":"https://discord.com/api/webhooks/1559665847771988080/***"},"lager":{"webhookId":"1551161582942158879","channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***"},
```
`~ resources/[selfcode]/rmc_core/server/ausbluten.lua`
```diff
+-- ox_inventory:GetInventoryItems() liefert Items nach Slot-Nummer (z.B. [1], [2], [5], [9]).
+-- Solche Tabellen haben Lücken: # und ipairs brechen am ersten leeren Slot ab.
+-- Aus der DB kommen alte Einträge evtl. als Objekt ({"1":..,"5":..}) oder mit null-Lücken.
+-- Hier wird alles in eine lückenlose Liste { {name, count, metadata}, ... } umgewandelt.
+local function NormalizeItems(items)
+    local list = {}
+    if type(items) ~= 'table' then return list end
+
+    local keys = {}
+    for k in pairs(items) do keys[#keys + 1] = k end
```
`− resources/[selfcode]/tms-refund/README.md`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-refund/client/main.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-refund/config.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-refund/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-refund/install.sql`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-refund/server/bot.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-refund/server/bot_config.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-refund/server/main.lua`
```diff
- Gelöscht
```

## 2026-11-28 14:23 Uhr
**+8** neu · **~2** geändert · **-0** gelöscht
`+ resources/[selfcode]/tms-refund/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-refund/client/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-refund/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-refund/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-refund/install.sql`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-refund/server/bot.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-refund/server/bot_config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-refund/server/main.lua`
```diff
+ Neue Datei
```
`~ resources/[brutal]/brutal_ambulancejob/config.lua`
```diff
-    DeathTime = 900, -- time til respawn is available
-    WaitTime = 100,   -- time til the player bleeds out
+    DeathTime = 2, -- time til respawn is available
+    WaitTime = 2,   -- time til the player bleeds out
```
`~ resources/[brutal]/brutal_ambulancejob/sv_utils.lua`
```diff
-local YourWebhook = 'https://discord.com/api/webhooks/1433556978243862619/***'  -- help: https://docs.brutalscripts.com/site/others/discord-webhook
-
-function GetWebhook()
-    return YourWebhook
-end
-
-function notification(source, title, text, time, type)
-    if Config.BrutalNotify then
-        TriggerClientEvent('brutal_notify:SendAlert', source, title, text, time, type)
-    else
```

## 2026-11-28 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"txadmin":{"channelId":"1552989823604756600","webhookId":"1552989826213617715","url":"https://discord.com/api/webhooks/1552989826213617715/***"},"esx_useractions":{"channelId":"1557386339866120252","webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/15573863427559
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-28T09:00:37Z","webhooks":{"esx_chat":{"webhookId":"1557386337580220497","channelId":"1557386335512305664","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"doors":{"webhookId":"1559665847771988080","channelId":"15596658453309
```

## 2026-11-28 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-27T17:01:14Z","webhooks":{"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913"},"joinleave":{"webhookId":"1570427416076091415","url":"https://discord.com/api/webhooks/15704274160760
+{"webhooks":{"txadmin":{"channelId":"1552989823604756600","webhookId":"1552989826213617715","url":"https://discord.com/api/webhooks/1552989826213617715/***"},"esx_useractions":{"channelId":"1557386339866120252","webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/15573863427559
```

## 2026-11-27 23:23 Uhr
**+2** neu · **~0** geändert · **-0** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_19_27_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_21_27_11_2026.json`
```diff
+ Neue Datei
```

## 2026-11-27 22:23 Uhr
**+0** neu · **~2** geändert · **-2** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-        {
-            "backupTimestamp": 1795381456,
-            "backupDate": "22_04_22_11_2026",
-            "backupFile": "banlist_22_04_22_11_2026.json",
-            "id": 11
-        },
-        {
-            "backupTimestamp": 1795381581,
-            "backupDate": "22_06_22_11_2026",
-            "backupFile": "banlist_22_06_22_11_2026.json",
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9": [
+    "char4:95e98569cca18ee079f5fe27ab54152ede42f277": [
-            "sender_identifier": "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9",
-            "date": "2026/09/16 - 20:15:27",
-            "receiver_identifier": "cd_garage",
-            "sender_name": "Jayden Anderson",
-            "reason": "Fahrzeugrückgabegebühr",
-            "type": "withdraw",
-            "receiver_name": "cd_garage",
-            "value": 500
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_22_04_22_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_22_06_22_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-27 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"esx_chat":{"webhookId":"1557386337580220497","channelId":"1557386335512305664","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"afk":{"webhookId":"1512475306554953789","channelId":"1512475286229356617","url":"https://discord.com/api
+{"updatedAt":"2026-11-27T17:01:14Z","webhooks":{"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913"},"joinleave":{"webhookId":"1570427416076091415","url":"https://discord.com/api/webhooks/15704274160760
```

## 2026-11-27 17:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/api_new/server/faction.lua`
```diff
-                                 [{ name, owner, items }]
+                                 [{ name, owner, label, items }]
+                                 search findet ID und Anzeigenamen (z. B. "Midnight Elite Lager").
+                                 Anzeigenamen kennt ox nur für geladene Lager; sie werden gemerkt (KVP).
+-- Anzeigenamen ("Midnight Elite Lager") kennt ox nur für geladene Lager -> merken (KVP, überlebt Neustarts)
+local function labelKey(name, owner) return 'stashlabel:' .. name .. '|' .. (owner or '') end
+
+local function rememberLabel(name, owner, label)
+    if type(label) == 'string' and label ~= '' and label ~= name then
+        SetResourceKvp(labelKey(name, owner), label)
```

## 2026-11-27 16:22 Uhr
**+1** neu · **~1** geändert · **-5** gelöscht
`+ resources/[selfcode]/api_new/server/faction.lua`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/faction.lua',
```
`− resources/[selfcode]/api_new/README.md`
```diff
- Gelöscht
```
`− resources/[selfcode]/api_new/README.md.bak-pfaendung`
```diff
- Gelöscht
```
`− resources/[selfcode]/api_new/fxmanifest.lua.bak-inventory`
```diff
- Gelöscht
```
`− resources/[selfcode]/api_new/fxmanifest.lua.bak-lifeinvader`
```diff
- Gelöscht
```
`− resources/[selfcode]/api_new/fxmanifest.lua.bak-pfaendung`
```diff
- Gelöscht
```

## 2026-11-27 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"faction":{"channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652"},"esx":{"channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***",
+{"categoryId":"1551161549018759170","webhooks":{"esx_chat":{"webhookId":"1557386337580220497","channelId":"1557386335512305664","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"afk":{"webhookId":"1512475306554953789","channelId":"1512475286229356617","url":"https://discord.com/api
```

## 2026-11-26 23:23 Uhr
**+7** neu · **~5** geändert · **-19** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_16_26_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_22_18_26_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[okok]/okokBanking/cl_utils.lua.bak-pfaendung`
```diff
+ Neue Datei
```
`+ resources/[okok]/okokBanking/sv_utils.lua.bak-pfaendung`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/README.md.bak-pfaendung`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/fxmanifest.lua.bak-pfaendung`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/seizure.lua`
```diff
+ Neue Datei
```
`~ resources/[okok]/okokBanking/cl_utils.lua`
```diff
+-- Pfändung (api_new): gepfändete Spieler kommen nicht an Bank und ATM (State Bag vom Server).
+local lastSeizedHint = 0
+
+    if LocalPlayer.state.pfaendung then
+        local now = GetGameTimer()
+        if now - lastSeizedHint > 8000 then
+            lastSeizedHint = now
+            if Config.okokNotify then
+                exports['okokNotify']:Alert('Bank', 'Dein Konto ist gepfändet.', 5000, 'error')
+            else
```
`~ resources/[okok]/okokBanking/sv_utils.lua`
```diff
+-- Pfändung (api_new): Solange ein Charakter gepfändet ist, sieht okokBanking bei ihm kein Geld.
+-- Abheben, Einzahlen, Überweisen und Rechnungen zahlen scheitern damit an "nicht genug Geld".
+function IsSeized(xPlayer)
+    if not xPlayer or GetResourceState('api_new') ~= 'started' then return false end
+    local ok, seized = pcall(function() return exports['api_new']:isSeized(xPlayer.identifier) end)
+    return ok and seized == true
+end
+
+    if IsSeized(xPlayer) then return 0 end
+    if IsSeized(xPlayer) then return 0 end
```
`~ resources/[selfcode]/api_new/README.md`
```diff
+
+---
+
+## Pfändung (LSPD-Dashboard)
+
+Zieht das komplette Bargeld, das komplette Bankguthaben und alle Fahrzeuge eines Charakters ein und gibt sie später zurück. Alles steht in der Tabelle `rmc_seizure` (wird beim Start angelegt). Funktioniert online und offline.
+
+### Was würde eingezogen?
+```bash
+curl "$API/seizure/preview/char1:abc123" -H "X-API-Key: $KEY"
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/seizure.lua',
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-26T19:59:05Z","webhooks":{"joinleave":{"url":"https://discord.com/api/webhooks/1570427416076091415/***","channelId":"1570427413605781594","webhookId":"1570427416076091415"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"155297109426752716
+{"categoryId":"1551161549018759170","webhooks":{"faction":{"channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652"},"esx":{"channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***",
```
`− resources/[selfcode]/tms-bridge/README.md`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-bridge/client.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-bridge/config.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-bridge/endpoint.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-bridge/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-bridge/html/index.html`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-bridge/server.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-pawn/README.md`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-pawn/client/main.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-pawn/config.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-pawn/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-pawn/server/main.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-pawn/server_config.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-poster/README.md`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-poster/client/main.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-poster/config.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-poster/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-poster/server/main.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/tms-poster/server_config.lua`
```diff
- Gelöscht
```

## 2026-11-26 22:22 Uhr
**+0** neu · **~1** geändert · **-2** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupDate": "22_01_21_11_2026",
-            "backupTimestamp": 1795294863,
-            "id": 11,
-            "backupFile": "banlist_22_01_21_11_2026.json"
-        },
-        {
-            "backupDate": "22_03_21_11_2026",
-            "backupTimestamp": 1795294988,
-            "id": 11,
-            "backupFile": "banlist_22_03_21_11_2026.json"
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_22_01_21_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_22_03_21_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-26 21:23 Uhr
**+3** neu · **~4** geändert · **-0** gelöscht
`+ resources/[manuell_start]/ox_inventory/web/images/pepperspray.png`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/client/pfefferspray.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/server/pfefferspray.lua`
```diff
+ Neue Datei
```
`~ resources/[manuell_start]/ox_inventory/data/items.lua`
```diff
+	["pepperspray"] = {
+		label = "Pfefferspray",
+		weight = 300,
+		stack = false,
+		close = true,
+		consume = 0,
+		description = "Reizgas – blendet Getroffene für kurze Zeit. Benutzen zum Ziehen/Wegstecken.",
+		client = {
+			export = "rmc_core.usePepperSpray",
+			image = "pepperspray.png",
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+            { key = 'pepperspray',    name = 'pfefferspray',    topic = 'Pfefferspray-Treffer',              label = 'Pfefferspray' },
+-- ====== PFEFFERSPRAY ======
+-- Item "pepperspray" (ox_inventory) benutzen = ziehen / wegstecken.
+-- Gezogen: [LMB] halten = sprühen, [X] = wegstecken.
+-- Getroffene Spieler sehen EffectDuration ms lang verschwommen.
+Config.Pfefferspray = {
+    Enabled = true,
+    Item = 'pepperspray',
+    -- nil = jeder darf sprühen. Später nur Polizei z.B.: { police = true, sheriff = true }
+    AllowedJobs = nil,
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-26T17:00:36Z","webhooks":{"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"faction":{"url":"https://discord.com/api/webhooks/15511615731947316
+{"updatedAt":"2026-11-26T19:59:05Z","webhooks":{"joinleave":{"url":"https://discord.com/api/webhooks/1570427416076091415/***","channelId":"1570427413605781594","webhookId":"1570427416076091415"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"155297109426752716
```
`~ resources/[selfcode]/rmc_core/fxmanifest.lua`
```diff
+    'usePepperSpray',
```

## 2026-11-26 19:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:dcdd8750773c33c2ce3ff658853fe0c909367dba": [
+    "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9": [
+            "sender_identifier": "char1:ed00a18aa373b82fda2a51a5f23d0c0567f13db9",
+            "date": "2026/09/16 - 20:15:27",
+            "reason": "Fahrzeugrückgabegebühr",
-            "value": 500,
-            "date": "2026/09/25 - 21:55:44",
-            "reason": "Fahrzeugrückgabegebühr",
-            "sender_identifier": "char1:dcdd8750773c33c2ce3ff658853fe0c909367dba"
-        }
```

## 2026-11-26 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","channelId":"1513950191936344245","webhookId":"1513950212480307490"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169","web
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-26T17:00:36Z","webhooks":{"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"faction":{"url":"https://discord.com/api/webhooks/15511615731947316
```

## 2026-11-26 15:22 Uhr
**+12** neu · **~0** geändert · **-0** gelöscht
`+ resources/[selfcode]/tms-pawn/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-pawn/client/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-pawn/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-pawn/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-pawn/server/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-pawn/server_config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-poster/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-poster/client/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-poster/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-poster/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-poster/server/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/tms-poster/server_config.lua`
```diff
+ Neue Datei
```

## 2026-11-26 10:22 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:66c02ef36d33a8fd6b8a8025e2fbb923addd21cb": [
-        {
-            "value": 100,
-            "receiver_name": "Bank (Kartenerneuerung)",
-            "date": "2026/02/17 - 21:57:11",
-            "sender_identifier": "char1:66c02ef36d33a8fd6b8a8025e2fbb923addd21cb",
-            "sender_name": "Nova Brandt",
-            "receiver_identifier": "bank"
-        },
-        {
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-25T23:01:09Z","categoryId":"1551161549018759170","webhooks":{"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913"},"doors":{"webhookId":"1559665847771988080","url":"https://discord.
+{"categoryId":"1551161549018759170","webhooks":{"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","channelId":"1513950191936344245","webhookId":"1513950212480307490"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169","web
```

## 2026-11-26 00:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-25T17:01:01Z","categoryId":"1551161549018759170","webhooks":{"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/**
+{"updatedAt":"2026-11-25T23:01:09Z","categoryId":"1551161549018759170","webhooks":{"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913"},"doors":{"webhookId":"1559665847771988080","url":"https://discord.
```

## 2026-11-25 22:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-        {
-            "backupDate": "21_57_20_11_2026",
-            "backupTimestamp": 1795208251,
-            "backupFile": "banlist_21_57_20_11_2026.json",
-            "id": 11
-        },
-        {
-            "backupDate": "21_59_20_11_2026",
-            "backupTimestamp": 1795208376,
-            "backupFile": "banlist_21_59_20_11_2026.json",
```

## 2026-11-25 18:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-25T10:34:50Z","webhooks":{"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"1417917687723724872","webhookId":"1552971931869777932"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"15529710
+{"updatedAt":"2026-11-25T17:01:01Z","categoryId":"1551161549018759170","webhooks":{"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/**
```

## 2026-11-25 12:22 Uhr
**+1** neu · **~1** geändert · **-0** gelöscht
`+ core`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-25T09:01:24Z","webhooks":{"esx_useractions":{"channelId":"1557386339866120252","webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***"},"poster":{"channelId":"1560007812342489120","webhookId":"156000
+{"updatedAt":"2026-11-25T10:34:50Z","webhooks":{"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"1417917687723724872","webhookId":"1552971931869777932"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"15529710
```

## 2026-11-25 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-24T23:01:08Z","webhooks":{"housing":{"url":"https://discord.com/api/webhooks/1570424984998912021/***","webhookId":"1570424984998912021","channelId":"1570424980183842916"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/**
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-25T09:01:24Z","webhooks":{"esx_useractions":{"channelId":"1557386339866120252","webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***"},"poster":{"channelId":"1560007812342489120","webhookId":"156000
```

## 2026-11-25 00:22 Uhr
**+0** neu · **~3** geändert · **-0** gelöscht
`~ resources/[oresmon]/0r-radio/web/build/assets/index-8e4836f8.css`
```diff
-.members-list-anchor{position:absolute;top:0;bottom:0;left:29px;display:flex;align-items:center;pointer-events:none;z-index:120}.members-list-box{position:relative;pointer-events:auto;width:135px;max-height:185px;overflow:hidden;display:flex;flex-direction:column}.members-list-box>div{max-height:18
+.members-list-anchor{position:absolute;top:0;bottom:360px;left:29px;display:flex;align-items:center;pointer-events:none;z-index:120}.members-list-box{position:relative;pointer-events:auto;width:135px;max-height:185px;overflow:hidden;display:flex;flex-direction:column}.members-list-box>div{max-heigh
```
`~ resources/[oresmon]/0r-radio/web/src/components/Radio/index.css`
```diff
-.members-list-anchor{position:absolute;top:0;bottom:0;left:29px;display:flex;align-items:center;pointer-events:none;z-index:120}
+.members-list-anchor{position:absolute;top:0;bottom:360px;left:29px;display:flex;align-items:center;pointer-events:none;z-index:120}
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"housing":{"url":"https://discord.com/api/webhooks/1570424984998912021/***","webhookId":"1570424984998912021","channelId":"1570424980183842916"
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-24T23:01:08Z","webhooks":{"housing":{"url":"https://discord.com/api/webhooks/1570424984998912021/***","webhookId":"1570424984998912021","channelId":"1570424980183842916"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/**
```

## 2026-11-24 23:23 Uhr
**+0** neu · **~4** geändert · **-0** gelöscht
`~ resources/[selfcode]/tms-bridge/README.md`
```diff
+## Alarmierung aus dem Panel ins Spiel
+
+In der Leitstelle im MDT: Einsatz öffnen → **Alarmieren → Im Spiel alarmieren** → Fraktion wählen.
+Alle Spieler mit dem Job der Fraktion (z. B. `police`, `ambulance`) bekommen die Meldung innerhalb weniger Sekunden.
+
+- Mit **cd_dispatch** (Codesign) erscheint sie dort als Meldung mit Blip.
+- Für andere Dispatch-Skripte feuert die Ressource das Server-Event `tms-bridge:alert`:
+
+```lua
+AddEventHandler('tms-bridge:alert', function(alert)
```
`~ resources/[selfcode]/tms-bridge/config.lua`
```diff
+-- Alarmierung aus dem Panel ins Spiel: Wird in der Leitstelle „Im Spiel alarmieren“ gewählt,
+-- bekommen alle Spieler mit dem Job der Fraktion (z. B. police, ambulance) die Meldung.
+-- Läuft cd_dispatch (Codesign), erscheint sie dort mit Blip. Andere Skripte: Server-Event 'tms-bridge:alert'.
+Config.Alerts = true
+
+-- Wie oft die Ressource nach neuen Alarmierungen fragt, in Sekunden (mindestens 2).
+Config.AlertInterval = 5
+
+-- Blip und Ton für cd_dispatch.
+Config.AlertBlip = { sprite = 431, scale = 1.2, time = 5, sound = 1 }
```
`~ resources/[selfcode]/tms-bridge/fxmanifest.lua`
```diff
-version '0.4.0'
+version '0.6.1'
```
`~ resources/[selfcode]/tms-bridge/server.lua`
```diff
+-- ─── Alarmierung aus dem Panel ─────────────────────────────────────────────
+-- Die Leitstelle alarmiert im MDT eine Fraktion („Im Spiel alarmieren“). Die Ressource holt die
+-- Alarmierung ab und löst sie für alle Spieler mit dem passenden Job aus.
+--   · cd_dispatch (Codesign): Meldung mit Blip über cd_dispatch:AddNotification
+--   · immer zusätzlich das Server-Event 'tms-bridge:alert' (alert) – für andere Dispatch-Skripte
+
+local function fireAlert(a)
+  local jobs = type(a.jobs) == 'table' and a.jobs or {}
+  local blipCfg = type(Config.AlertBlip) == 'table' and Config.AlertBlip or {}
+  local title = (a.keyword and a.keyword ~= '' and (a.keyword .. ' - ') or '') .. tostring(a.title or 'Einsatz')
```

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
