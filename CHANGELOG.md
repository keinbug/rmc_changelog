# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

## 2026-11-20 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"esx_useractions":{"channelId":"1557386339866120252","url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582"},"minijobs":{"channelId":"1570426349213188196","url":"https://discord.com/api/webhooks/157042635180
+{"categoryId":"1551161549018759170","webhooks":{"esx_jobs":{"channelId":"1557386361172918374","webhookId":"1557386364578955274","url":"https://discord.com/api/webhooks/1557386364578955274/***"},"troll":{"channelId":"1552971103910236172","webhookId":"1552971107500433498","url":"https://discord.com/a
```

## 2026-11-20 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"afk":{"webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617"},"lager":{"webhookId":"1551161582942158879","url":"https://discord.com/api/webhooks/1551161582942158879/***","c
+{"categoryId":"1551161549018759170","webhooks":{"esx_useractions":{"channelId":"1557386339866120252","url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582"},"minijobs":{"channelId":"1570426349213188196","url":"https://discord.com/api/webhooks/157042635180
```

## 2026-11-19 22:23 Uhr
**+1** neu · **~6** geändert · **-0** gelöscht
`+ resources/[selfcode]/api_new/server/items.lua`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
+    "lastBackup": 1795121802,
-        {
-            "backupDate": "21_37_14_11_2026",
-            "id": 11,
-            "backupFile": "banlist_21_37_14_11_2026.json",
-            "backupTimestamp": 1794688675
-        },
-        {
-            "backupDate": "21_40_14_11_2026",
-            "id": 11,
```
`~ resources/[selfcode]/api_new/README.md`
```diff
-Jeder Request braucht den API-Key aus `settings.lua` (`Settings.ApiKey`):
+Jeder Request braucht den API-Key aus `settings.lua` (`Settings.ApiKey`). Einzige Ausnahme sind die öffentlichen [Item-Routen](#items-ox_inventory--öffentlich):
+## Items (ox_inventory) – öffentlich
+
+Diese Routen brauchen **keinen API-Key** und sind nicht an die IP-Whitelist gebunden. Sie liefern nur Item-Definitionen (keine Spieler- oder Inventardaten) und sind über `https://fivem-api.rmc-rp.de` erreichbar.
+
+```bash
+PUB="https://fivem-api.rmc-rp.de"
+
+curl "$PUB/items"                              # alle Items mit Metadaten
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/items.lua',
```
`~ resources/[selfcode]/api_new/server/http.js`
```diff
+const fs = require('fs');
+const path = require('path');
+// ============================================================
+//  Item-Bilder (ox_inventory/web/images) - öffentlich, ohne API-Key
+//  GET /items/image/:name   (:name = Item- oder Dateiname, Endung optional)
+// ============================================================
+
+const IMAGE_TYPES = {
+    png: 'image/png',
+    webp: 'image/webp',
```
`~ resources/[selfcode]/api_new/server/main.lua`
```diff
+      GET  /items, /items/:name, /items/image/:name
+                                   -> ÖFFENTLICH (ohne Key), siehe server/items.lua
+-- Öffentliche Route: KEIN API-Key, KEINE IP-Whitelist (z.B. Item-Liste und -Bilder).
+-- Nur für Daten nutzen, die jeder sehen darf. Eigenes Rate-Limit pro Besucher-IP.
+--  Api.addPublicRoute('GET', '/items/:name', function(res, params, body, query, req) ... end, 240)
+local publicRoutes = {}
+local publicRate = {}
+
+function Api.addPublicRoute(method, pattern, handler, maxPerMinute)
+    local regex = '^' .. pattern:gsub('[%-%.]', '%%%0'):gsub(':[%w_]+', '([^/]+)') .. '$'
```
`~ resources/[selfcode]/api_new/settings.lua`
```diff
+
+-- Items-Endpunkte (/items/...): ox_inventory-Items, Metadaten und Bilder
+-- ÖFFENTLICH - kein API-Key, keine IP-Whitelist (nur Item-Definitionen, keine Spielerdaten)
+Settings.Items = {
+    Enabled              = true,
+    Resource             = 'ox_inventory',
+    ImageDir             = 'web/images',                    -- Ordner in der Resource
+    PublicUrl            = 'https://fivem-api.rmc-rp.de',   -- Basis für "imageUrl" ('' = aus dem Request)
+    CacheSeconds         = 60,                              -- so lange wird die Item-Liste gecacht
+    MaxRequestsPerMinute = 240,                             -- pro Besucher-IP (JSON-Routen)
```

## 2026-11-19 21:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "receiver_identifier": "bank",
+            "reason": "Auszahlung vom Bankkonto",
+            "sender_identifier": "char2:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "date": "2026/11/19 - 20:46:03",
+            "value": 100000,
+            "type": "withdraw",
+            "sender_name": "Timo Anderson",
+            "receiver_name": "Geldbörse"
+        },
```
`~ resources/[selfcode]/rmc_core/data/sits.json`
```diff
-[{"x":1225.8873,"y":-420.7482,"z":68.0417,"label":"Sit Chair 4","h":255.6565,"id":"sit_1791572244_8861","dict":"timetable@ron@ig_3_couch","anim":"base"},{"x":1226.4694,"y":-419.3795,"z":68.0817,"label":"Sit Chair 2","h":271.1957,"id":"sit_1791572300_6917","dict":"timetable@ron@ig_5_p3","anim":"ig_5
+[{"x":1225.8873,"y":-420.7482,"z":68.0417,"label":"Sit Chair 4","h":255.6565,"id":"sit_1791572244_8861","dict":"timetable@ron@ig_3_couch","anim":"base"},{"x":1226.4694,"y":-419.3795,"z":68.0817,"label":"Sit Chair 2","h":271.1957,"id":"sit_1791572300_6917","dict":"timetable@ron@ig_5_p3","anim":"ig_5
```

## 2026-11-19 20:23 Uhr
**+5** neu · **~1** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_skate/client.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_skate/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_skate/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_skate/server.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_skate/stream/p_defilied_ragdoll_01_s.ydr`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/rmc_core/data/sits.json`
```diff
-[{"x":1225.8873,"id":"sit_1791572244_8861","z":68.0417,"label":"Sit Chair 4","dict":"timetable@ron@ig_3_couch","anim":"base","h":255.6565,"y":-420.7482},{"x":1226.4694,"id":"sit_1791572300_6917","z":68.0817,"label":"Sit Chair 2","dict":"timetable@ron@ig_5_p3","anim":"ig_5_p3_base","h":271.1957,"y":
+[{"x":1225.8873,"y":-420.7482,"z":68.0417,"label":"Sit Chair 4","h":255.6565,"id":"sit_1791572244_8861","dict":"timetable@ron@ig_3_couch","anim":"base"},{"x":1226.4694,"y":-419.3795,"z":68.0817,"label":"Sit Chair 2","h":271.1957,"id":"sit_1791572300_6917","dict":"timetable@ron@ig_5_p3","anim":"ig_5
```

## 2026-11-19 19:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5": [
+    "char2:726b2e82f8613191a738a5158a2b2cd5c7dbeea1": [
-            "type": "deposit",
-            "receiver_identifier": "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5",
-            "reason": "Einzahlung auf Bankkonto",
-            "date": "2026/11/18 - 19:28:35",
-            "sender_identifier": "bank",
-            "value": 100000,
-            "receiver_name": "Jasmin Winchester",
-            "sender_name": "Geldbörse"
```

## 2026-11-19 18:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"willkommen":{"webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575"},"esx_useractions":{"webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386
+{"categoryId":"1551161549018759170","webhooks":{"afk":{"webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617"},"lager":{"webhookId":"1551161582942158879","url":"https://discord.com/api/webhooks/1551161582942158879/***","c
```

## 2026-11-19 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-18T23:01:05Z","webhooks":{"troll":{"channelId":"1552971103910236172","webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/1552971107500433498/***"},"esx":{"channelId":"1420103430562910370","webhookId":"1557386326951592027","url":"https://discord.com/api/we
+{"webhooks":{"willkommen":{"webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575"},"esx_useractions":{"webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386
```

## 2026-11-19 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"chopshop":{"webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744"},"me":{"webhookId":"1513950212480307490","url":"https://discord.com/api/webhooks/1513950212480307490/***",
+{"updatedAt":"2026-11-18T23:01:05Z","webhooks":{"troll":{"channelId":"1552971103910236172","webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/1552971107500433498/***"},"esx":{"channelId":"1420103430562910370","webhookId":"1557386326951592027","url":"https://discord.com/api/we
```

## 2026-11-18 22:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-        {
-            "backupDate": "21_35_13_11_2026",
-            "backupTimestamp": 1794602113,
-            "id": 11,
-            "backupFile": "banlist_21_35_13_11_2026.json"
-        },
-        {
-            "backupDate": "21_37_13_11_2026",
-            "backupTimestamp": 1794602238,
-            "id": 11,
```

## 2026-11-18 20:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "type": "deposit",
+            "receiver_identifier": "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5",
+            "reason": "Einzahlung auf Bankkonto",
+            "date": "2026/11/18 - 19:28:35",
+            "sender_identifier": "bank",
+            "value": 100000,
+            "receiver_name": "Jasmin Winchester",
+            "sender_name": "Geldbörse"
+        },
```

## 2026-11-18 19:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c": [
+    "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5": [
-            "reason": "Fahrzeugrückgabegebühr",
-            "sender_identifier": "char2:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
-            "type": "withdraw",
-            "receiver_identifier": "cd_garage",
-            "sender_name": "Timo Anderson",
-            "value": 500,
-            "receiver_name": "cd_garage",
-            "date": "2026/10/06 - 21:19:34"
```

## 2026-11-18 18:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-18T09:00:42Z","categoryId":"1551161549018759170","webhooks":{"poster":{"channelId":"1560007812342489120","url":"https://discord.com/api/webhooks/1560007815156998144/***","webhookId":"1560007815156998144"},"marriage":{"channelId":"1467556343492640830","url":"https://discord.com
+{"categoryId":"1551161549018759170","webhooks":{"chopshop":{"webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744"},"me":{"webhookId":"1513950212480307490","url":"https://discord.com/api/webhooks/1513950212480307490/***",
```

## 2026-11-18 10:22 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char3:95e98569cca18ee079f5fe27ab54152ede42f277": [
+    "char2:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c": [
-            "sender_name": "Savings Interest",
-            "sender_identifier": "bank",
-            "reason": "Savings account interest payment (Period 43)",
-            "date": "2026/11/10 - 10:00:58",
-            "value": 9392,
-            "type": "interest_savings",
-            "receiver_name": "Savings Account",
-            "receiver_identifier": "char3:95e98569cca18ee079f5fe27ab54152ede42f277"
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-17T23:19:35Z","webhooks":{"chopshop":{"channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312"},"einreise":{"channelId":"1552971085937381431","url":"https://discord.com/api/webhooks/1552971088328392714
+{"updatedAt":"2026-11-18T09:00:42Z","categoryId":"1551161549018759170","webhooks":{"poster":{"channelId":"1560007812342489120","url":"https://discord.com/api/webhooks/1560007815156998144/***","webhookId":"1560007815156998144"},"marriage":{"channelId":"1467556343492640830","url":"https://discord.com
```

## 2026-11-18 00:23 Uhr
**+3** neu · **~9** geändert · **-0** gelöscht
`+ resources/[esx_addons]/ks-multicharacter/ks-libs-configs/ks-sql-slots.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/multichar.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_api/server/modules/multichar.lua`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/ks-multicharacter/fxmanifest.lua`
```diff
+    'ks-libs-configs/ks-sql-slots.lua', -- muss VOR ks-server.lua geladen werden
```
`~ resources/[esx_addons]/ks-multicharacter/ks-libs-configs/ks-config.js`
```diff
-ksConfig.DiscordSlotTxt = 'Du musst eine Rolle auf Discord haben, um ihn freizuschalten.';
+ksConfig.DiscordSlotTxt = 'Dieser Slot muss vom Team für dich freigeschaltet werden.';
```
`~ resources/[esx_addons]/ks-multicharacter/ks-libs-configs/ks-config.lua`
```diff
-ksConfig = {}
-
-ksConfig.QBcore = 'qb-core'
-ksConfig.ESX = 'es_extended'
-ksConfig.Framework = ksGetFramework(ksConfig.QBcore, ksConfig.ESX)
-
-ksConfig.EmptySlots = 1 -- Default slots for all players
-
-ksConfig.EnableDiscord = true
-
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/multichar.lua',
```
`~ resources/[selfcode]/api_new/server/refunds.lua`
```diff
+    GET    /refunds/account/:license alle offenen Rückerstattungen eines Spielkontos (alle Charaktere)
+-- Alle offenen Rückerstattungen eines Spielkontos: Lizenz ohne Charakter-Slot, findet char1:…, char2:… usw.
+Api.addRoute('GET', '/refunds/account/:license', function(res, params)
+    local license = (tostring(params[1] or ''):gsub('^license:', ''))
+    if #license < 20 or #license > 64 or not license:match('^%w+$') then return fail(res, 400, 'Ungültige Lizenz') end
+
+    local rows = dbQuery(('SELECT * FROM `%s` WHERE identifier = ? OR identifier LIKE ? ORDER BY id DESC LIMIT 50'):format(TABLE),
+        { license, 'char%:' .. license }) or {}
+    local E = esx()
+    local list = {}
```
`~ resources/[selfcode]/rmc_api/config/api_key.lua`
```diff
+-- ========================================
+--  MULTICHAR-SLOTS (ks-multicharacter)
+-- ========================================
+-- Beide Werte müssen zu ksConfig.SqlSlots in ks-multicharacter/ks-libs-configs/ks-config.lua passen.
+Config.Multichar = {
+    Table = 'rmc_multichar_slots',
+    MaxExtraSlots = 3,
+}
+
```
`~ resources/[selfcode]/rmc_api/fxmanifest.lua`
```diff
+    'server/modules/multichar.lua',
```
`~ resources/[selfcode]/rmc_api/server/main.lua`
```diff
+    -- Multichar-Slots (ks-multicharacter, SQL statt Discord-Rollen)
+    { method = 'GET',  path = '/multichar/list',                      handler = function(req, res) MulticharModule.list(req, res) end },
+    { method = 'GET',  path = '/multichar/status/:id',                handler = function(req, res, p) MulticharModule.status(req, res, p[1]) end },
+    { method = 'POST', path = '/multichar/grant',                     handler = function(req, res) MulticharModule.grant(req, res) end },
+    { method = 'POST', path = '/multichar/revoke',                    handler = function(req, res) MulticharModule.revoke(req, res) end },
+
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"minijobs":{"url":"https://discord.com/api/webhooks/1570426351809335326/***","webhookId":"1570426351809335326","channelId":"1570426349213188196"}
+{"updatedAt":"2026-11-17T23:19:35Z","webhooks":{"chopshop":{"channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312"},"einreise":{"channelId":"1552971085937381431","url":"https://discord.com/api/webhooks/1552971088328392714
```

## 2026-11-17 23:23 Uhr
**+1** neu · **~2** geändert · **-0** gelöscht
`+ resources/[selfcode]/api_new/server/character.lua`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/api_new/README.md`
```diff
+## Charaktere
+
+Liest aus der Tabelle `users`, funktioniert also auch offline. `:target` = Server-ID oder Discord-ID (online), Charakter-Identifier (`char1:abc…`), Lizenz (`license:abc…`) oder eine Discord-ID – die wird auch offline über die Spalte `users.discord_id` gefunden.
+
+### Alle Charaktere eines Spielkontos
+```bash
+curl "$API/characters/4" -H "X-API-Key: $KEY"
+curl "$API/characters/123456789012345678" -H "X-API-Key: $KEY"
+```
+
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/character.lua',
```

## 2026-11-17 22:22 Uhr
**+2** neu · **~1** geändert · **-2** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_48_17_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_50_17_11_2026.json`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupTimestamp": 1794515477,
-            "backupFile": "banlist_21_31_12_11_2026.json",
-            "backupDate": "21_31_12_11_2026",
-            "id": 11
-        },
-        {
-            "backupTimestamp": 1794515602,
-            "backupFile": "banlist_21_33_12_11_2026.json",
-            "backupDate": "21_33_12_11_2026",
-            "id": 11
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_31_12_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_33_12_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-17 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"doors":{"channelId":"1559665845330907296","webhookId":"1559665847771988080","url":"https://discord.com/api/webhooks/1559665847771988080/***"},"esx":{"channelId":"1420103430562910370","webhookId":"1557386326951592027","url":"https://discord.com/api/we
+{"webhooks":{"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"minijobs":{"url":"https://discord.com/api/webhooks/1570426351809335326/***","webhookId":"1570426351809335326","channelId":"1570426349213188196"}
```

## 2026-11-17 16:23 Uhr
**+0** neu · **~7** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_housing/README.md`
```diff
-| `/housingadmin` | Liste aller Objekte: Teleport, Mieter räumen, Löschen, Abrechnung sofort ausführen |
+| `/housingadmin` | Liste aller Objekte: Betreten (Admin, mit vollen Mieter-Rechten solange man drin ist), Garage betreten, Teleport, Mieter räumen, Löschen, Abrechnung sofort ausführen |
```
`~ resources/[selfcode]/rmc_housing/client/creator.lua`
```diff
+                    { title = 'Betreten (Admin)', icon = 'door-open',
+                      description = p.tenant and 'Ohne Schlüssel rein · Lager, Umkleide, Tablet, Geräte und Punkte wie der Mieter nutzen' or 'Leeres Objekt ansehen',
+                      onSelect = function() EnterProperty(p.id, 'admin') end },
+                    if (p.garageSize or 0) > 0 then
+                        sub[#sub + 1] = { title = 'Garage betreten (Admin)', icon = 'warehouse', description = ('%d Stellplätze · eingeparkte Fahrzeuge ansehen'):format(p.garageSize),
+                            onSelect = function() Garage.enter(p, true) end }
+                    end
```
`~ resources/[selfcode]/rmc_housing/client/garage.lua`
```diff
-function Garage.enter(p)
+function Garage.enter(p, admin)
-    local ok, data = lib.callback.await('rmc_housing:garage:enter', false, p.id)
+    local ok, data = lib.callback.await('rmc_housing:garage:enter', false, p.id, admin == true)
```
`~ resources/[selfcode]/rmc_housing/config.lua`
```diff
+
+---------------------------------------------------------------------
+-- Anzeige (ox_lib): Position von Hinweis-Texten und Benachrichtigungen
+---------------------------------------------------------------------
+Config.UI = {
+    textPosition   = 'left-center',  -- [E]-Hinweise: 'left-center' | 'right-center' | 'top-center' | 'bottom-center'
+    notifyPosition = 'center-left',  -- Benachrichtigungen: 'top-left' | 'center-left' | 'bottom-left' | 'top' | 'bottom' | 'top-right' | 'center-right' | 'bottom-right'
+}
+
+-- Gilt für alle Aufrufe in dieser Resource; eine im Aufruf gesetzte Position hat Vorrang.
```
`~ resources/[selfcode]/rmc_housing/server/admin.lua`
```diff
-            entrance = p.entrance, garage = p.garage, points = p.points, interior = p.interior, appliances = p.appliances,
+            entrance = p.entrance, garage = p.garage, garageSize = l and l.garage or 0, points = p.points, interior = p.interior, appliances = p.appliances,
```
`~ resources/[selfcode]/rmc_housing/server/garage.lua`
```diff
-local function access(src, pid)
+local function access(src, pid, admin)
-    if not (r == 'owner' or (k and truthy(k.perm_enter))) then return false, 'Du hast keinen Zugang zu dieser Garage.' end
-    if l.status == 'lockout' then return false, 'Die Garage ist wegen offener Miete gesperrt.' end
+    if not admin then
+        if not (r == 'owner' or (k and truthy(k.perm_enter))) then return false, 'Du hast keinen Zugang zu dieser Garage.' end
+        if l.status == 'lockout' then return false, 'Die Garage ist wegen offener Miete gesperrt.' end
+    end
-lib.callback.register('rmc_housing:garage:enter', function(src, pid)
+lib.callback.register('rmc_housing:garage:enter', function(src, pid, admin)
```
`~ resources/[selfcode]/rmc_housing/server/main.lua`
```diff
+AdminInside = {}  -- [src] = propertyId (per /housingadmin betreten: volle Mieter-Rechte, solange drinnen)
-    TriggerClientEvent('ox_lib:notify', src, { title = 'Housing', description = msg, type = typ or 'inform', duration = 6000 })
+    TriggerClientEvent('ox_lib:notify', src, { title = 'Housing', description = msg, type = typ or 'inform', duration = 6000, position = Config.UI.notifyPosition })
-function Housing.role(src, pid)
+-- raw = true: echte Rolle ohne Admin-Zugang (für Blips / Punkte draußen)
+-- 3. Rückgabewert true = Rechte kommen nur vom Admin-Zugang
+function Housing.role(src, pid, raw)
+    if not raw and AdminInside[src] == pid and Inside[src] == pid then return 'owner', nil, true end
+    -- Admin in einem vermieteten Objekt: verhält sich wie der Hauptmieter
+    local admin = mode == 'admin'
```

## 2026-11-17 14:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[devcore]/devcore_needs/configs/items.lua`
```diff
+            Stress = nil, -- How much stress do you want to remove after using the item if you don't want to use the stress system leave nil
+            Alcohol = nil -- Set the amount of alcohol the item should add after each drink.
+        },
+    },
+
+    ["cooked_chicken"] = {-- item name
+        Size = 220, -- Item size
+        Type = 'FOOD', -- Item type 'DRINK' , 'FOOD' , 'GLASS'
+        Prop = { -- Prop spawn data for idle & usage.
+            Main = {
```

## 2026-11-17 12:22 Uhr
**+0** neu · **~7** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_housing/README.md`
```diff
-## Geräte: Ofen & Kaffeeautomat (ox_target)
+## Geräte: Ofen, Kaffeeautomat & Dusche (ox_target)
-- Ohne Strom gehen beide Geräte nicht (`needPower`). Vom Mieter aufgestellte Geräte kann er per `ox_target` → *Gerät abbauen* wieder entfernen.
+- **Dusche:** *Gerät aufstellen* → *Dusche* → *Bestehendes Objekt auswählen* → auf den **Boden der Dusche** zielen und „Diese Stelle“ mit `E` bestätigen.
+  Danach `ox_target` → *Duschen*: Die Figur läuft hin, zieht sich aus (nur `esx_skin`), duscht 20 Sek. und ist danach sauber (Blut/Dreck weg) und nass.
+  Jeder in der Wohnung kann duschen und sieht das Wasser. Immer nur eine Person gleichzeitig. Einstellungen: `Config.Appliances.types.shower`.
+- Ohne Strom gehen Ofen und Kaffeeautomat nicht (`needPower`). Vom Mieter aufgestellte Geräte kann er per `ox_target` → *Gerät abbauen* wieder entfernen.
```
`~ resources/[selfcode]/rmc_housing/client/appliances.lua`
```diff
+-- Geräte im Interior: Ofen, Kaffeeautomat & Dusche
-local KINDS = { 'oven', 'coffee' }
-local ICON = { oven = 'fire-burner', coffee = 'mug-hot' }
+local KINDS = { 'oven', 'coffee', 'shower' }
+local ICON = { oven = 'fire-burner', coffee = 'mug-hot', shower = 'shower' }
+local KIND_DESC = { oven = 'z. B. TK-Pizza backen', shower = 'Dusche im Bad anvisieren, dort wird geduscht' }
-                description = k == 'coffee' and ('%d Kaffee pro Füllung'):format(t.servings) or 'z. B. TK-Pizza backen' }
+                description = k == 'coffee' and ('%d Kaffee pro Füllung'):format(t.servings) or KIND_DESC[k] }
-            description = 'z. B. den Herd, der schon in der Küche steht, anvisieren' }
+            description = kind == 'shower' and 'Die Dusche im Bad anvisieren · „Diese Stelle“ = hier wird geduscht'
```
`~ resources/[selfcode]/rmc_housing/client/creator.lua`
```diff
-        opts[#opts + 1] = { title = 'Gerät aufstellen', icon = 'mug-hot', description = ('%d / %d · Ofen oder Kaffeeautomat'):format(#Draft.appliances, Config.Appliances.max), onSelect = function()
+        opts[#opts + 1] = { title = 'Gerät aufstellen', icon = 'mug-hot', description = ('%d / %d · Ofen, Kaffeeautomat oder Dusche'):format(#Draft.appliances, Config.Appliances.max), onSelect = function()
-        opts[#opts + 1] = { title = 'Gerät aufstellen', icon = 'mug-hot', description = ('%d / %d · Ofen oder Kaffeeautomat'):format(#Edit.appliances, Config.Appliances.max), onSelect = function()
+        opts[#opts + 1] = { title = 'Gerät aufstellen', icon = 'mug-hot', description = ('%d / %d · Ofen, Kaffeeautomat oder Dusche'):format(#Edit.appliances, Config.Appliances.max), onSelect = function()
```
`~ resources/[selfcode]/rmc_housing/client/main.lua`
```diff
-        opts[#opts + 1] = { title = 'Gerät aufstellen', icon = 'mug-hot', description = 'Ofen oder Kaffeeautomat · Objekt wählen und platzieren', onSelect = function()
+        opts[#opts + 1] = { title = 'Gerät aufstellen', icon = 'mug-hot', description = 'Ofen, Kaffeeautomat oder Dusche · Objekt wählen und platzieren', onSelect = function()
-        opts[#opts + 1] = { title = 'Punkte einrichten', icon = 'location-dot', description = 'Lager, Umkleide, Tür, Tablet und Geräte selbst platzieren', onSelect = pointsMenu }
+        opts[#opts + 1] = { title = 'Punkte einrichten', icon = 'location-dot', description = 'Lager, Umkleide, Tür, Tablet, Geräte und Dusche selbst platzieren', onSelect = pointsMenu }
```
`~ resources/[selfcode]/rmc_housing/config.lua`
```diff
+-- Geräte im Interior (ox_target): Ofen, Kaffeeautomat & Dusche
+        -- Dusche: am einfachsten "Bestehendes Objekt auswählen" → die Dusche im Bad anvisieren ("Diese Stelle").
+        -- Dort stellt sich der Spieler hin und duscht. Alle in der Wohnung sehen das Wasser.
+        shower = {
+            label = 'Dusche',
+            models = {       -- zum neu Aufstellen (ungültige Modelle werden ausgeblendet)
+                { model = 'prop_shower_rack_01', label = 'Duschablage' },
+                { model = 'prop_towel_rail_02',  label = 'Handtuchhalter' },
+            },
+            needPower = false,   -- Wasser läuft auch ohne Strom
```
`~ resources/[selfcode]/rmc_housing/server/appliances.lua`
```diff
+-- Geräte im Interior: Ofen, Kaffeeautomat & Dusche (Bedienung über ox_target)
+local Showers = {} -- ['pid:id'] = { src, untilAt } (wer gerade duscht)
-    Housing.activity(l.id, a.kind == 'oven' and 'cooking-pot' or 'coffee', ('%s aufgestellt'):format(typeOf(a.kind).label))
+    Housing.activity(l.id, ({ oven = 'cooking-pot', coffee = 'coffee', shower = 'shower-head' })[a.kind] or 'plug', ('%s aufgestellt'):format(typeOf(a.kind).label))
+            Showers[ovenKey(pid, id)] = nil
-local ALLOWED = { coffee = { draw = true, refill = true }, oven = { ovenIn = true, ovenOut = true } }
+-- Dusche: immer nur einer gleichzeitig. Alle in der Wohnung bekommen das Wasser angezeigt.
+Use.shower = function(src, pid, a)
+    local t = typeOf('shower')
+    local key = ovenKey(pid, a.id)
```
`~ resources/[selfcode]/rmc_housing/web/app.js`
```diff
-    { ok: true, t: D.appliances.length ? `${D.appliances.length} Gerät(e) aufgestellt (Ofen / Kaffeeautomat)` : 'Keine Geräte · optional, in der Vorschau mit [E] → „Gerät aufstellen“', step: 2 },
+    { ok: true, t: D.appliances.length ? `${D.appliances.length} Gerät(e) aufgestellt (Ofen / Kaffeeautomat / Dusche)` : 'Keine Geräte · optional, in der Vorschau mit [E] → „Gerät aufstellen“', step: 2 },
```

## 2026-11-17 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-16T17:00:42Z","categoryId":"1551161549018759170","webhooks":{"willkommen":{"webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575"},"minijobs":{"webhookId":"1570426351809335326","url":"https://discord
+{"categoryId":"1551161549018759170","webhooks":{"doors":{"channelId":"1559665845330907296","webhookId":"1559665847771988080","url":"https://discord.com/api/webhooks/1559665847771988080/***"},"esx":{"channelId":"1420103430562910370","webhookId":"1557386326951592027","url":"https://discord.com/api/we
```

## 2026-11-17 01:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_housing/client/garage.lua`
```diff
-    Wait(0)
-    SetVehicleOnGroundProperly(veh)
-    FreezeEntityPosition(veh, true)
+    -- Erst einfrieren, wenn das Fahrzeug wirklich auf dem Boden steht (sonst schwebt es auf Spawn-Höhe).
+    -- Läuft pro Fahrzeug im Hintergrund, damit das Betreten nicht hängt.
+    CreateThread(function()
+        RequestCollisionAtCoord(pos.x, pos.y, pos.z)
+        ActivatePhysics(veh)
+        local t = GetGameTimer()
+        local grounded = false
```

## 2026-11-17 00:23 Uhr
**+3** neu · **~13** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_housing/.claude/settings.local.json`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/client/garage.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/garage.lua`
```diff
+ Neue Datei
```
`~ resources/[cd]/cd_garage/server/features/property_garages.lua`
```diff
-RegisterServerEvent('cd_garage:PropertyGarage:Create', function(newGarageData)
-    CreatePropertyGarage(source, newGarageData)
-end)
-
-function CreatePropertyGarage(src, newGarageData)
-    if not TypeCheck(newGarageData, 'table', '6545', 'data nil or not a table in cd_garage:PropertyGarage:Create') then
-        return
-    end
-
-    local garageId = GenerateUniqueId(12)
```
`~ resources/[cd]/cd_garage/server/features/vehicle_functions.lua`
```diff
-local VehicleSpawnLocks = {}
-function CanVehicleSpawnFromThisGarage(plate, shellCoords, persistantSpawn, garageRaideSpawn)
-    if persistantSpawn then
-        return {
-            result = true
-        }
-    end
-
-    local fakeData = FakePlateTable and FakePlateTable[plate]
-    if fakeData and fakeData.originalplate then
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38": [
+    "char3:95e98569cca18ee079f5fe27ab54152ede42f277": [
-            "type": "interest_savings",
+            "sender_name": "Savings Interest",
-            "value": 3,
+            "value": 9392,
+            "type": "interest_savings",
-            "receiver_identifier": "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38",
-            "sender_name": "Savings Interest"
+            "receiver_identifier": "char3:95e98569cca18ee079f5fe27ab54152ede42f277"
```
`~ resources/[selfcode]/rmc_housing/README.md`
```diff
+## Hausgarage (2 / 6 / 10 Stellplätze)
+
+Eigenes Garagen-System, **ohne cd_garage**. Die Fahrzeuge stehen sichtbar im GTA-Online-Garagen-Interior.
+
+1. **Admin:** `/housingadmin` → Objekt → „Garage setzen“ (Einfahrt draußen, optional Ausparkpunkt). Ohne Punkt gibt es keine Garage.
+2. **Mieter:** Tablet → Reiter **Garage** → Garage einmalig kaufen (Preise in `Config.Garage.tiers`, Upgrade = Differenz).
+3. **Einparken:** mit dem eigenen Fahrzeug zum Garagen-Punkt, `[E]`. Voll = kein weiteres Fahrzeug (2er-Garage → max. 2).
+4. **Ausparken:** zu Fuß `[E]` am Garagen-Punkt → Garage betreten → ans Fahrzeug stellen, `[E]`. Das Auto erscheint draußen am Ausparkpunkt.
+
+| Garage | Interior | Stellplätze |
```
`~ resources/[selfcode]/rmc_housing/client/creator.lua`
```diff
+    garage   = { label = 'Garage',     icon = 'warehouse', color = { 96, 200, 214 } },
+    spawn    = { label = 'Ausparken',  icon = 'car',       color = { 92, 201, 148 } },
+-- Garage setzen: hinfahren/hinlaufen, in Ausparkrichtung ausrichten, [E]
+local function editGarage(p)
+    if Edit or Preview or Current then return Notify('Verlasse zuerst das aktuelle Interior.', 'error') end
+    if p.garage then Teleport(p.garage) elseif #(GetEntityCoords(cache.ped) - vec3(p.entrance.x, p.entrance.y, p.entrance.z)) > 60.0 then Teleport(p.entrance) end
+    Notify('Stell dich (oder dein Auto) dahin, wo das Fahrzeug ausparken soll. Die Blickrichtung ist die Ausparkrichtung.', 'inform')
+    local pos = PlacePoint('garage', { entrance = p.entrance, garage = p.garage, spawn = p.garage and p.garage.spawn })
+    if not pos then return Notify('Abgebrochen.', 'inform') end
+    local ok, msg = lib.callback.await('rmc_housing:admin:setGarage', false, p.id, pos)
```
`~ resources/[selfcode]/rmc_housing/client/main.lua`
```diff
-    if busy or Current then return end
+    if busy or Current or Garage.current then return end
+-- Hausgarage (client/garage.lua): zu Fuß betreten, als Fahrer einparken. Ohne gekaufte Garage → Tablet.
+local function garagePress(p, inVeh)
+    if (p.garageSize or 0) == 0 then
+        if p.role == 'owner' then
+            notify('Du hast noch keine Garage. Kaufe sie am Tablet.', 'inform')
+            return OpenManage(p.id, 'garage')
+        end
+        return notify('Für dieses Objekt wurde noch keine Garage gekauft.', 'inform')
```
`~ resources/[selfcode]/rmc_housing/config.lua`
```diff
+---------------------------------------------------------------------
+-- Hausgarage (eigenes System, ohne cd_garage)
+-- 1. Admin setzt den Garagen-Punkt draußen: /housingadmin → Objekt → "Garage setzen"
+--    (+ optional Ausparkpunkt). Ohne Punkt kann keine Garage gekauft werden.
+-- 2. Der Hauptmieter kauft die Garage am Tablet (Reiter "Garage"): 2, 6 oder 10 Stellplätze.
+-- 3. Am Garagen-Punkt: im Fahrzeug [E] = einparken, zu Fuß [E] = Garage betreten.
+--    Drinnen stehen die eingeparkten Fahrzeuge auf ihren Plätzen, [E] am Fahrzeug = ausparken.
+-- Nutzen dürfen: Hauptmieter + Schlüsselinhaber mit Zutritt. Ausparken darf nur der Fahrzeughalter.
+-- Stellplätze prüfen/verschieben (Admin): /housinggarage 2|6|10
+---------------------------------------------------------------------
```
`~ resources/[selfcode]/rmc_housing/fxmanifest.lua`
```diff
+    'server/garage.lua',
+    'client/garage.lua',
```
`~ resources/[selfcode]/rmc_housing/server/admin.lua`
```diff
-            entrance = p.entrance, points = p.points, interior = p.interior, appliances = p.appliances,
+            entrance = p.entrance, garage = p.garage, points = p.points, interior = p.interior, appliances = p.appliances,
+-- Garage setzen (pos) oder entfernen (pos = nil)
+lib.callback.register('rmc_housing:admin:setGarage', function(src, pid, pos)
+    if not Housing.isAdmin(src) then return false, 'Keine Berechtigung.' end
+    local p = Properties[tonumber(pid)]
+    if not p then return false, 'Objekt nicht gefunden.' end
+    local v = pos and vec(pos) or nil
+    if pos and not v then return false, 'Ungültige Position.' end
+    -- Ausparkpunkt behalten, wenn er noch in der Nähe liegt
```
`~ resources/[selfcode]/rmc_housing/server/db.lua`
```diff
-local SCHEMA_VERSION = 3
+local SCHEMA_VERSION = 4
+    `garage` TINYINT NOT NULL DEFAULT 0,
+
+-- Hausgarage: welches Fahrzeug steht auf welchem Stellplatz (Fahrzeugdaten bleiben in owned_vehicles)
+[[CREATE TABLE IF NOT EXISTS `rmc_housing_vehicles` (
+    `plate` VARCHAR(12) NOT NULL,
+    `lease_id` INT NOT NULL,
+    `property_id` INT NOT NULL,
+    `slot` TINYINT NOT NULL,
```
`~ resources/[selfcode]/rmc_housing/server/main.lua`
```diff
-        points = ? WHERE id = ?]], {
+        points = ?, garage = ? WHERE id = ?]], {
-        l.power_cancelled and 1 or 0, json.encode(l.points or {}), l.id,
+        l.power_cancelled and 1 or 0, json.encode(l.points or {}), l.garage or 0, l.id,
+    l.garage = tonumber(l.garage) or 0
+        garage = Housing.garagePayload and Housing.garagePayload(src, pid) or nil,
-        local r = x and Housing.role(src, pid)
+        local r, k = nil, nil
+        if x then r, k = Housing.role(src, pid) end
+            garage = (Config.Garage.enabled and (r == 'owner' or (k and truthy(k.perm_enter)))) and p.garage or nil,
```
`~ resources/[selfcode]/rmc_housing/web/app.js`
```diff
+  { id: 'garage', icon: 'car', label: 'Garage', show: d => !!(d.garage && d.garage.available && (d.role === 'owner' || d.garage.size > 0)) },
+  S.garSel = null;
-  const views = { uebersicht: vOverview, schluessel: vKeys, interior: vInterior, lager: vStorage, umkleide: vWardrobe, zahlungen: vBills };
+  const views = { uebersicht: vOverview, schluessel: vKeys, interior: vInterior, lager: vStorage, garage: vGarage, umkleide: vWardrobe, zahlungen: vBills };
+  if (id === 'garage' && d.garage && d.garage.size) return `<span class="ct">${d.garage.vehicles.length}/${d.garage.size}</span>`;
+/* ---------- Garage ---------- */
+function vGarage(d) {
+  const G = d.garage, owner = d.role === 'owner';
+  const next = G.tiers.find(t => t.upgrade);
+  const sel = G.tiers.find(t => t.slots === S.garSel) || next || G.tiers[G.tiers.length - 1];
```
`~ resources/[selfcode]/rmc_housing/web/style.css`
```diff
+.tiers.g3{grid-template-columns:repeat(3,minmax(0,1fr))}
+.tier .lot{height:74px;display:flex;flex-wrap:wrap;align-content:flex-end;gap:5px}
+.tier .lot svg{width:20px;height:20px;color:var(--muted)}
+.tier[aria-checked="true"] .lot svg{color:var(--brass)}
+.bays{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:10px}
+.bay{position:relative;display:grid;gap:3px;justify-items:start;padding:14px;border-radius:12px;border:1px dashed var(--line);background:var(--raise);color:var(--muted)}
+.bay svg{width:22px;height:22px;margin-bottom:4px}
+.bay b{font-size:13.5px;color:var(--fg-2)}
+.bay .no{position:absolute;top:10px;right:12px;font-family:var(--f-mono);font-size:11px;color:var(--muted)}
+.bay.full{border-style:solid;border-color:rgba(216,179,115,.4);background:var(--brass-soft)}
```

## 2026-11-16 22:23 Uhr
**+2** neu · **~1** geändert · **-2** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_45_16_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_47_16_11_2026.json`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-        {
-            "backupTimestamp": 1794428840,
-            "id": 11,
-            "backupDate": "21_27_11_11_2026",
-            "backupFile": "banlist_21_27_11_11_2026.json"
-        },
-        {
-            "backupTimestamp": 1794428965,
-            "id": 11,
-            "backupDate": "21_29_11_11_2026",
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_27_11_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_29_11_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-16 20:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/api_new/admins.json`
```diff
-  {
-    "$schema": 1,
-    "name": "RMC-DripQueen",
-    "master": false,
-    "password_hash": "$2a$11$ed6JLnynRbrQkCAurUMsBueKIuTUydvELa3PnXiywgYIJC2wIFRb.",
-    "providers": {
-      "citizenfx": {
-        "id": "HotDripQueen",
-        "identifier": "fivem:8599143",
-        "data": {}
```

## 2026-11-16 19:23 Uhr
**+7** neu · **~1** geändert · **-0** gelöscht
`+ resources/[selfcode]/api_new/client/screen.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/fxmanifest.lua.bak-refunds`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/fxmanifest.lua.bak-screen`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/refunds.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/screen.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/ui/screen.html`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/ui/screen.js`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/refunds.lua',
+    'server/screen.lua',
+    'client/screen.lua',
+}
+
+-- Live-Bildschirm: unsichtbare Seite, die das Spielbild nur bei Bedarf per WebRTC überträgt
+ui_page 'ui/screen.html'
+
+files {
+    'ui/screen.html',
```

## 2026-11-16 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-16T09:01:29Z","webhooks":{"staff":{"webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763"},"versicherung":{"webhookId":"1535733186921898004","url":"https://discord.
+{"updatedAt":"2026-11-16T17:00:42Z","categoryId":"1551161549018759170","webhooks":{"willkommen":{"webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575"},"minijobs":{"webhookId":"1570426351809335326","url":"https://discord
```

## 2026-11-16 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-15T23:01:13Z","webhooks":{"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924552"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/**
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-16T09:01:29Z","webhooks":{"staff":{"webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763"},"versicherung":{"webhookId":"1535733186921898004","url":"https://discord.
```

## 2026-11-16 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-15T17:01:09Z","categoryId":"1551161549018759170","webhooks":{"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490","channelId":"1513950191936344245"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***"
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-15T23:01:13Z","webhooks":{"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924552"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/**
```
