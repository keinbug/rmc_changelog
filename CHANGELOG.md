# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

## 2026-11-04 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"join":{"webhookId":"1552971091771924552","url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352"},"staff":{"webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763"},"
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-04T09:01:30Z","webhooks":{"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400","channelId":"1471556817061544068"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/*
```

## 2026-11-04 01:22 Uhr
**+0** neu · **~5** geändert · **-0** gelöscht
`~ resources/[manuell_start]/ox_inventory/client.lua`
```diff
+-- Platzieren: Vorschau-Prop frei positionieren und genau dort abstellen
+local PLACE_MAX_DISTANCE = 4.0
+
+RegisterNUICallback('placeItem', function(data, cb)
+	cb(1)
+
+	if usingItem or discardHolding then return end
+
+	local item = PlayerData.inventory[data.slot]
+	if not item then return end
```
`~ resources/[manuell_start]/ox_inventory/locales/de.json`
```diff
-  "discard_picked_up": "aufgehoben"
+  "discard_picked_up": "aufgehoben",
+  "ui_place": "Platzieren",
+  "place_confirm": "Platzieren",
+  "place_cancel": "Abbrechen",
+  "place_rotate": "Drehen",
+  "place_height": "Höhe",
+  "place_fine": "Feinjustierung",
+  "place_ground": "Am Boden ausrichten",
+  "place_too_far": "Zu weit entfernt"
```
`~ resources/[manuell_start]/ox_inventory/locales/en.json`
```diff
-  "discard_picked_up": "picked up"
+  "discard_picked_up": "picked up",
+  "ui_place": "Place",
+  "place_confirm": "Place",
+  "place_cancel": "Cancel",
+  "place_rotate": "Rotate",
+  "place_height": "Height",
+  "place_fine": "Fine adjust",
+  "place_ground": "Snap to ground",
+  "place_too_far": "Too far away"
```
`~ resources/[manuell_start]/ox_inventory/web/build/assets/index.js`
```diff
-`+d),de&&C_([O,k,A],e=>{d=M_(d,e,` `)}),b&&ve?b.createHTML(d):d},t.setConfig=function(){Ke(arguments.length>0&&arguments[0]!==void 0?arguments[0]:{}),me=!0},t.clearConfig=function(){Ue=null,me=!1},t.isValidAttribute=function(e,t,n){return Ue||Ke({}),it(He(e),He(t),n)},t.addHook=function(e,t){typeof
+`+d),de&&C_([O,k,A],e=>{d=M_(d,e,` `)}),b&&ve?b.createHTML(d):d},t.setConfig=function(){Ke(arguments.length>0&&arguments[0]!==void 0?arguments[0]:{}),me=!0},t.clearConfig=function(){Ue=null,me=!1},t.isValidAttribute=function(e,t,n){return Ue||Ke({}),it(He(e),He(t),n)},t.addHook=function(e,t){typeof
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708","channelId":"1552971120460828763"
+{"webhooks":{"join":{"webhookId":"1552971091771924552","url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352"},"staff":{"webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763"},"
```

## 2026-11-04 00:23 Uhr
**+0** neu · **~6** geändert · **-0** gelöscht
`~ resources/[manuell_start]/ox_inventory/client.lua`
```diff
+-- Wegwerfen: Item als Prop in die Hand nehmen und physikalisch wegwerfen
+local discardDefaultProp = `prop_paper_bag_small`
+local discardThrowDict, discardThrowClip = 'anim@heists@narcotics@trash', 'throw_b'
+local discardHolding = false
+
+local function getCamDirection()
+	local rot = GetGameplayCamRot(2)
+	local x, z = math.rad(rot.x), math.rad(rot.z)
+	local num = math.abs(math.cos(x))
+
```
`~ resources/[manuell_start]/ox_inventory/locales/de.json`
```diff
+  "ui_discard": "Wegwerfen",
-  "component_slot_occupied" : "Der %s Slot dieser Waffe ist bereits belegt",
+  "component_slot_occupied": "Der %s Slot dieser Waffe ist bereits belegt",
-  "storage": "Kofferraum"
+  "storage": "Kofferraum",
+  "discard_throw": "Wegwerfen",
+  "discard_cancel": "Abbrechen",
+  "discard_pickup": "Aufheben",
+  "discard_picked_up": "aufgehoben"
```
`~ resources/[manuell_start]/ox_inventory/locales/en.json`
```diff
+  "ui_discard": "Discard",
-  "storage": "Storage"
+  "storage": "Storage",
+  "discard_throw": "Throw away",
+  "discard_cancel": "Cancel",
+  "discard_pickup": "Pick up",
+  "discard_picked_up": "picked up"
```
`~ resources/[manuell_start]/ox_inventory/modules/inventory/server.lua`
```diff
+---Weggeworfene Items, die per ox_target wieder aufgehoben werden koennen.
+---@type table<integer, { name: string, count: number, metadata: table, owner: number, netId: number?, placing: boolean? }>
+local ThrownItems = {}
+local thrownId = 0
+local THROWN_LIFETIME = 10 * 60000 -- nach 10 Minuten verschwindet das Prop samt Item
+
+local function removeThrown(id)
+	local thrown = ThrownItems[id]
+	if not thrown then return end
+
```
`~ resources/[manuell_start]/ox_inventory/web/build/assets/index.js`
```diff
-`+d),de&&C_([O,k,A],e=>{d=M_(d,e,` `)}),b&&ve?b.createHTML(d):d},t.setConfig=function(){Ke(arguments.length>0&&arguments[0]!==void 0?arguments[0]:{}),me=!0},t.clearConfig=function(){Ue=null,me=!1},t.isValidAttribute=function(e,t,n){return Ue||Ke({}),it(He(e),He(t),n)},t.addHook=function(e,t){typeof
+`+d),de&&C_([O,k,A],e=>{d=M_(d,e,` `)}),b&&ve?b.createHTML(d):d},t.setConfig=function(){Ke(arguments.length>0&&arguments[0]!==void 0?arguments[0]:{}),me=!0},t.clearConfig=function(){Ue=null,me=!1},t.isValidAttribute=function(e,t,n){return Ue||Ke({}),it(He(e),He(t),n)},t.addHook=function(e,t){typeof
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512
+{"webhooks":{"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708","channelId":"1552971120460828763"
```

## 2026-11-03 23:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokTuning/config.lua`
```diff
-            name        = "KUROKAI",
-            jobs        = { "kurokai" },
+            name        = "Midnight Elite",
+            jobs        = { "midnight_elite" },
-            name        = "KUROKAI",
-            jobs        = { "kurokai" },
+            name        = "Midnight Elite",
+            jobs        = { "midnight_elite" },
-            name        = "KUROKAI",
-            jobs        = { "kurokai" },
```

## 2026-11-03 22:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ server.cfg`
```diff
(Secrets — Inhalt unterdrückt)
```
`~ server.cfg.bkp`
```diff
(Secrets — Inhalt unterdrückt)
```

## 2026-11-03 21:23 Uhr
**+1** neu · **~6** geändert · **-17** gelöscht
`+ resources/[selfcode]/rmc_tablet/.claude/settings.local.json`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1793649503,
+    "lastBackup": 1793736129,
-        {
-            "backupTimestamp": 1793302996,
-            "backupDate": "20_43_29_10_2026",
-            "backupFile": "banlist_20_43_29_10_2026.json",
-            "id": 11
-        },
-        {
-            "backupTimestamp": 1793303121,
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497","channelId":"155738633551230
+{"categoryId":"1551161549018759170","webhooks":{"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512
```
`~ resources/[selfcode]/rmc_tablet/client.lua`
```diff
+RegisterNetEvent('rmc_tablet:denied', function()
+    busy = false
+    requestId = requestId + 1
+end)
+
+-- Eigener Befehl mit + davor: taucht nicht im Chat-Vorschlag auf, nur für die Taste.
+RegisterCommand('+rmc_tablet', function()
+    if open then
+        closeTablet()
+    else
```
`~ resources/[selfcode]/rmc_tablet/config.lua`
```diff
+-- Standardtaste zum Öffnen. Spieler können sie unter Einstellungen > Tastenbelegung > FiveM ändern.
+Config.Key = 'F6'
+
+-- Nur diese Jobs dürfen das Tablet öffnen (ESX-Jobname, nicht das Label).
+-- Optional mit Mindest-Rang: ['police'] = 2  -> erst ab Grade 2. true = alle Ränge.
+Config.Jobs = {
+    ['police'] = true,
+    ['ambulance'] = true,
+}
+
```
`~ resources/[selfcode]/rmc_tablet/html/app.js`
```diff
-  if (event.key === "Escape") postClose();
+  if (event.key === "Escape" || event.key === "F6") {
+    event.preventDefault();
+    postClose();
+  }
```
`~ resources/[selfcode]/rmc_tablet/server.lua`
```diff
+local ESX = nil
+
+local function getESX()
+    if ESX then return ESX end
+    if GetResourceState('es_extended') ~= 'started' then return nil end
+    local ok, obj = pcall(function()
+        return exports['es_extended']:getSharedObject()
+    end)
+    if ok and type(obj) == 'table' then ESX = obj end
+    return ESX
```
`− resources/[selfcode]/rmc_halloween/README.md`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/client.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/config.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/html/index.html`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/html/sounds/distant.mp3`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/html/sounds/halloween.mp3`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/html/sounds/heartbeat.mp3`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/html/sounds/moan.mp3`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/html/sounds/scream.mp3`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/html/sounds/whisper.mp3`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/scares.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_halloween/server.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_test_trash/Lang.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_test_trash/client/client.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_test_trash/config.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_test_trash/fxmanifest.lua`
```diff
- Gelöscht
```

## 2026-11-03 20:23 Uhr
**+0** neu · **~4** geändert · **-0** gelöscht
`~ resources/[jaksam_scripte]/vehicles_keys/current_config.json`
```diff
-{"client":{"lockDrivingVehiclesNPC":false,"alarmBlip":{"color":1,"sprite":161,"duration":15,"scale":1},"completelyDisableWindowDestroy":false,"isHotwireRequired":true,"use3Dtext":true,"vehicleLockAnim":{"name":"fob_click","duration":800,"dict":"anim@mp_player_intmenu@key_fob@"},"canTargetDrivingNPC
+{"client":{"lockDrivingVehiclesNPC":true,"alarmBlip":{"color":1,"sprite":161,"duration":15,"scale":1},"completelyDisableWindowDestroy":false,"isHotwireRequired":true,"use3Dtext":true,"vehicleLockAnim":{"name":"fob_click","duration":800,"dict":"anim@mp_player_intmenu@key_fob@"},"allowAutoOpenDriverD
```
`~ resources/[selfcode]/rmc_autopilot_taxi/client/taxi.lua`
```diff
+    SetVehicleNeedsToBeHotwired(veh, false)
+    Entity(veh).state:set('canAlwaysStart', true, true) -- Bypass für vehicles_keys
+            -- Schlüssel-Scripts (z.B. "NPC-Fahrzeuge abschließen") dürfen das Taxi nicht verriegeln
+            if GetVehicleDoorLockStatus(Taxi.vehicle) > 1 then
+                SetVehicleDoorsLocked(Taxi.vehicle, 1)
+                SetVehicleDoorsLockedForAllPlayers(Taxi.vehicle, false)
+            end
+
```
`~ resources/[selfcode]/rmc_autopilot_taxi/config.lua`
```diff
+-- ==============================
+--  Fahrzeugschlüssel-Bypass (jaksam vehicles_keys)
+-- ==============================
+-- Verhindert, dass "Geschlossene Türen von fahrenden NPC-Fahrzeugen" / Hotwiring
+-- das Taxi blockiert: der Fahrgast bekommt temporäre Schlüssel für das Kennzeichen.
+Config.VehicleKeys = {
+    enabled  = true,
+    resource = 'vehicles_keys', -- Ressourcenname des Schlüssel-Scripts
+}
+
```
`~ resources/[selfcode]/rmc_autopilot_taxi/server/main.lua`
```diff
+-- ==============================
+--  Fahrzeugschlüssel (jaksam vehicles_keys)
+-- ==============================
+
+local function keysAvailable()
+    return Config.VehicleKeys and Config.VehicleKeys.enabled
+        and GetResourceState(Config.VehicleKeys.resource) == 'started'
+end
+
+local function giveKeys(src, plate)
```

## 2026-11-03 19:23 Uhr
**+14** neu · **~1** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_autopilot_taxi/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/client/app.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/client/taxi.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/server/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/ui/app.js`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/ui/assets/car.png`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/ui/assets/icon.svg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/ui/assets/marker-car.svg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/ui/assets/marker-dest.svg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/ui/assets/marker-pickup.svg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/ui/index.html`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_autopilot_taxi/ui/style.css`
```diff
+ Neue Datei
```
`~ resources/[jaksam_scripte]/vehicles_keys/current_config.json`
```diff
-{"server":{"vehicleAlarmsItems":{"3":"vehicle_alarm_3","2":"vehicle_alarm_2","1":"vehicle_alarm_1","4":"vehicle_alarm_4"},"acePermission":"vehicles_keys","probabilityPoliceAlertNpcStolenVehicles":35,"jobsThatCanInstallAlarms":false,"vehicleTransferContractItemName":"vehicle_transfer_contract"},"sha
+{"client":{"lockDrivingVehiclesNPC":false,"alarmBlip":{"color":1,"sprite":161,"duration":15,"scale":1},"completelyDisableWindowDestroy":false,"isHotwireRequired":true,"use3Dtext":true,"vehicleLockAnim":{"name":"fob_click","duration":800,"dict":"anim@mp_player_intmenu@key_fob@"},"canTargetDrivingNPC
```

## 2026-11-03 18:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-03T09:00:55Z","categoryId":"1551161549018759170","webhooks":{"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169","webhookId":"1552971096847028264"},"freecam_photo":{"url":"https://discord.com/api/webhooks/15515201323194122
+{"webhooks":{"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497","channelId":"155738633551230
```

## 2026-11-03 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-02T23:00:39Z","webhooks":{"esx_test":{"webhookId":"1557386332483887194","channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"join":{"webhookId":"1552971091771924552","channelId":"144812076039156
+{"updatedAt":"2026-11-03T09:00:55Z","categoryId":"1551161549018759170","webhooks":{"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169","webhookId":"1552971096847028264"},"freecam_photo":{"url":"https://discord.com/api/webhooks/15515201323194122
```

## 2026-11-03 04:23 Uhr
**+0** neu · **~0** geändert · **-101** gelöscht
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/.fxap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/1.png`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/2.png`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/3.png`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/README.txt`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/FixCollision/apa_ch2_10_6.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/server.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/sp_manifest.ymt`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/MajestyMansionManifest.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_baselegno.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_bbq.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_cancello_l.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_cancello_r.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_coll.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_colonna.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_colonnaesterna.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_cornici.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_coso.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_cucina.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_esterno.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_esterno_coll.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_esterno_ymap.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_gazebo.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_lavandino.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_libri.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_luce.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_mensolabagno.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_mensolavetro.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_mobile12.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_muroesterno.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_piantagenerale.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_piscina.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_piscina_acqua.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_piscina_acqua_coll.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_portaentrata_r.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_portagenerale.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_props.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room04_mobile.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room04_tavolino.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room05.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room06.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room07.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room08.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room08_armadio.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room08_porta.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room09.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room10.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room10_murales.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room11.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room12.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room13.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14_armadio.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14_letto.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14_scaffale.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room14_tavolino.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room15.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_room15_divanetto.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_rotonda.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_sassi.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_serranda.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_setsedie.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_shell.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_socket.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_socket2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_specchio.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_specchio2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradaesterna.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradina.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradina2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradina3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_stradina4.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_tappeto.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_tavololampada.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_terrenoesterno.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_texture.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_ymap.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ab45_villa_ytyp.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_4.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_6.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_critical_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_long_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_long_1.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_strm_1.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/apa_ch2_10_strm_2.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ba_curtain2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/bh1_36_gatefrm_iref.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_10_grass_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_10_land_04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_rdprops_ch2_rd_wire074.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_rdprops_ch2_rd_wire075.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_rdprops_ch2_rd_wire109.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch2_rdprops_ch2_rd_wire110.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/ch_chint02_mirror_frame.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/AB45-MajestyMansion/stream/vinewood_hills.ymt`
```diff
- Gelöscht
```

## 2026-11-03 03:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "receiver_name": "cd_garage",
+            "sender_name": "Coco Black",
+            "type": "withdraw",
+            "date": "2026/11/03 - 03:14:08",
+            "sender_identifier": "char4:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "reason": "Fahrzeugrückgabegebühr",
+            "value": 2500,
+            "receiver_identifier": "cd_garage"
+        },
```

## 2026-11-03 02:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char3:95e98569cca18ee079f5fe27ab54152ede42f277": [
-        {
-            "date": "2026/11/02 - 10:01:02",
-            "value": 9183,
-            "receiver_identifier": "char3:95e98569cca18ee079f5fe27ab54152ede42f277",
-            "type": "interest_savings",
-            "sender_name": "Savings Interest",
-            "reason": "Savings account interest payment (Period 42)",
-            "receiver_name": "Savings Account",
-            "sender_identifier": "bank"
```

## 2026-11-03 00:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-02T17:01:30Z","webhooks":{"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"147155683599476740
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-02T23:00:39Z","webhooks":{"esx_test":{"webhookId":"1557386332483887194","channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"join":{"webhookId":"1552971091771924552","channelId":"144812076039156
```

## 2026-11-02 21:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
+    "lastBackup": 1793649503,
-            "backupFile": "banlist_20_39_28_10_2026.json",
-            "backupDate": "20_39_28_10_2026",
-            "backupTimestamp": 1793216370,
-            "id": 11
-        },
-        {
-            "backupFile": "banlist_20_41_28_10_2026.json",
-            "backupDate": "20_41_28_10_2026",
-            "backupTimestamp": 1793216495,
```

## 2026-11-02 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-02T09:01:18Z","webhooks":{"default":{"channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269"},"chopshop":{"channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/
+{"updatedAt":"2026-11-02T17:01:30Z","webhooks":{"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"147155683599476740
```

## 2026-11-02 10:22 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5": [
+    "char3:95e98569cca18ee079f5fe27ab54152ede42f277": [
-            "receiver_identifier": "bank",
-            "sender_name": "Bonnie Parker",
-            "reason": "Auszahlung vom Bankkonto",
-            "type": "withdraw",
-            "date": "2026/10/28 - 01:26:09",
-            "value": 5000,
-            "sender_identifier": "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5",
-            "receiver_name": "Geldbörse"
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"bell":{"webhookId":"1471556835994767400","channelId":"1471556817061544068","url":"https://discord.com/api/webhooks/1471556835994767400/***"},"esx_jobs":{"webhookId":"1557386364578955274","channelId":"1557386361172918374","url":"https://discord.com/ap
+{"updatedAt":"2026-11-02T09:01:18Z","webhooks":{"default":{"channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269"},"chopshop":{"channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/
```

## 2026-11-02 00:23 Uhr
**+0** neu · **~6** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_minijobs/client/deliver.lua`
```diff
-TR = TR or {}
-
-local carryProp = 0
-local carryGen = 0
-local pointEntities = {}
-local takingPizza = false
-local handingPizza = false
-
-local function carrySpec()
-    local asg = TR.State.assignment
```
`~ resources/[selfcode]/rmc_minijobs/client/interactions.lua`
```diff
-TR = TR or {}
-TR.ZoneMeta = TR.ZoneMeta or {}
-
-local pendingInvite = nil
-
-CreateThread(function()
-    Wait(1000)
-    print('[Minijob] Team-Event-Handler registriert')
-end)
-
```
`~ resources/[selfcode]/rmc_minijobs/client/jobs.lua`
```diff
-TR = TR or {}
-
-local function applyResult(result)
-    if not result then return false end
-    if result.config then TR.ApplyLiveConfig(result.config) end
-    if result.assignment then
-        TR.State.assignment = result.assignment
-        if TR.OnAssignmentUpdate then TR.OnAssignmentUpdate() end
-    end
-    if result.dutyJobId ~= nil then TR.State.dutyJobId = result.dutyJobId end
```
`~ resources/[selfcode]/rmc_minijobs/client/runner.lua`
```diff
-TR = TR or {}
-
-local asgEntities = {}
-local worldTargets = {}
-local asgZones = {}
-local asgBlips = {}
-local spawnedPointIds = {}
-local snappedNear = {}
-local plantMarkers = {}
-local STREAM_IN = 80.0
```
`~ resources/[selfcode]/rmc_minijobs/server/admin.lua`
```diff
-TR = TR or {}
-
-local RANK_LOOKUP = {
-    owner = true, inhaber = true, superadmin = true, admin = true, god = true,
-    management = true, leitung = true, projektleiter = true, projektleitung = true,
-}
-
-local function normalizeRank(value)
-    if value == nil then return '' end
-    if type(value) == 'table' then value = value.name or value[1] end
```
`~ resources/[selfcode]/rmc_minijobs/server/jobs.lua`
```diff
-TR = TR or {}
-TR.Duty = {}
-TR.Assignments = {}
-TR.SourceMap = {}
-TR.DutyVehicle = {}
-TR.Cooldowns = {}
-TR.ActionStamp = {}
-TR.PaperStock = {}
-
-local function nowMs()
```

## 2026-11-01 23:23 Uhr
**+0** neu · **~5** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-01T17:00:56Z","webhooks":{"esx_paycheck":{"webhookId":"1557386357381533816","channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***"},"esx_jobs":{"webhookId":"1557386364578955274","channelId":"1557386
+{"categoryId":"1551161549018759170","webhooks":{"bell":{"webhookId":"1471556835994767400","channelId":"1471556817061544068","url":"https://discord.com/api/webhooks/1471556835994767400/***"},"esx_jobs":{"webhookId":"1557386364578955274","channelId":"1557386361172918374","url":"https://discord.com/ap
```
`~ resources/[selfcode]/rmc_minijobs/client/interactions.lua`
```diff
+local pendingInvite = nil
+
+CreateThread(function()
+    Wait(1000)
+    print('[Minijob] Team-Event-Handler registriert')
+end)
+
-    local alert = lib.alertDialog({
-        header = 'Team-Einladung',
-        content = ('%s möchte dich einladen für den Job: %s'):format(inviterName, jobLabel),
```
`~ resources/[selfcode]/rmc_minijobs/client/jobs.lua`
```diff
+            print('[Minijob] Gefundener Spieler: ' .. name .. ' (ID: ' .. id .. ')')
-    local result = lib.callback.await('minijob:server:invitePlayer', false, tonumber(input[1]), jobId)
+    print('[Minijob] Eingabe erhalten: ' .. tostring(input[1]) .. ' (Typ: ' .. type(input[1]) .. ')')
+    local targetId = tonumber(input[1])
+    print('[Minijob] Konvertierte ID: ' .. targetId)
+    local result = lib.callback.await('minijob:server:invitePlayer', false, targetId, jobId)
```
`~ resources/[selfcode]/rmc_minijobs/fxmanifest.lua`
```diff
+    'client/interactions.lua',
```
`~ resources/[selfcode]/rmc_minijobs/server/admin.lua`
```diff
+    print('[Minijob Server] Einladung empfangen - Source: ' .. source .. ', Target: ' .. targetId .. ' (Typ: ' .. type(targetId) .. '), Job: ' .. jobId)
+
+    targetId = tonumber(targetId)
+    print('[Minijob Server] Konvertierte Target: ' .. targetId)
+
+    print('[Minijob Server] Sende Einladung von ' .. source .. ' (' .. inviter .. ') an ' .. targetId .. ' für Job ' .. jobId)
```

## 2026-11-01 21:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1793476361,
-        {
-            "backupFile": "banlist_20_36_27_10_2026.json",
-            "backupDate": "20_36_27_10_2026",
-            "id": 11,
-            "backupTimestamp": 1793129808
-        },
-        {
-            "backupFile": "banlist_20_38_27_10_2026.json",
-            "backupDate": "20_38_27_10_2026",
```

## 2026-11-01 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816","channelId":"1557386352226598913"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652","channelId":"1551161570439
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-01T17:00:56Z","webhooks":{"esx_paycheck":{"webhookId":"1557386357381533816","channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***"},"esx_jobs":{"webhookId":"1557386364578955274","channelId":"1557386
```

## 2026-11-01 14:22 Uhr
**+0** neu · **~4** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_minijobs/client/interactions.lua`
```diff
+RegisterNetEvent('minijob:client:syncAssignment', function(assignment)
+    if assignment then
+        TR.State.assignment = assignment
+        if TR.OnAssignmentUpdate then TR.OnAssignmentUpdate() end
+    end
+end)
+
```
`~ resources/[selfcode]/rmc_minijobs/client/jobs.lua`
```diff
+    local job = Utils.FindMinijob(jobId)
+
+    if job and job.allowTeamplay then
+        exports.ox_target:addLocalEntity(ped, {
+            {
+                name = 'mj_invite_' .. jobId,
+                icon = 'fa-solid fa-users',
+                label = 'Team einladen',
+                distance = 2.2,
+                onSelect = function()
```
`~ resources/[selfcode]/rmc_minijobs/client/runner.lua`
```diff
+
+    if TR.State.team and TR.State.team.id then
+        lib.callback.await('minijob:server:syncAssignment', false, result.assignment)
+    end
```
`~ resources/[selfcode]/rmc_minijobs/server/admin.lua`
```diff
+
+lib.callback.register('minijob:server:syncAssignment', function(source, assignment)
+    local teamId = TR.State.team and TR.State.team.id
+    if not teamId or not teams[teamId] then return end
+
+    for memberId in pairs(teams[teamId].members) do
+        if memberId ~= source then
+            TriggerClientEvent('minijob:client:syncAssignment', memberId, assignment)
+        end
+    end
```

## 2026-11-01 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","channelId":"1557386329686413342","webhookId":"1557386332483887194"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","channelId":"146755634349264
+{"webhooks":{"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816","channelId":"1557386352226598913"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652","channelId":"1551161570439
```

## 2026-11-01 02:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[manuell_start]/ox_inventory/data/items.lua`
```diff
-		stack = false,
+		stack = true,
```
`~ resources/[manuell_start]/ox_inventory/data/shops.lua`
```diff
-            { name = 'liquid', price = 9 },
```

## 2026-11-01 01:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokTuning/config.lua`
```diff
-            name        = "Kanzaki Tuning", --1
+            name        = "Benny Tuning", --1
-            name        = "Kanzaki Tuning",--2
+            name        = "Benny Tuning",--2
-            name        = "Kanzaki Tuning",--- 3
+            name        = "Benny Tuning",--- 3
-            name        = "Kanzaki Tuning",--Heli/LKW
+            name        = "Benny Tuning",--Heli/LKW
-      },       
+      },
```

## 2026-11-01 00:23 Uhr
**+0** neu · **~1** geändert · **-164** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353","channelId":"1551161585614061618"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"15529710
+{"categoryId":"1551161549018759170","webhooks":{"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","channelId":"1557386329686413342","webhookId":"1557386332483887194"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","channelId":"146755634349264
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/.fxap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/client.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/config.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/overrides/tstudio_legionsquare_asset_deer01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/overrides/tstudio_legionsquare_asset_deer02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/overrides/tstudio_legionsquare_asset_lamp01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/overrides/tstudio_legionsquare_asset_lamp02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/overrides/tstudio_legionsquare_asset_lamp03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/overrides/tstudio_legionsquare_asset_lamp05.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/overrides/tstudio_legionsquare_distantlights.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/overrides/tstudio_legionsquare_lodlights.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/overrides/tstudio_legionsquare_lp.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_em_water_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_em_water_02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_grave_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_grave_04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_grave_05.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_grave_07.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_grave_08.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_grave_09.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_grave_11.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_grave_13.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_grave_15.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_light_g.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_light_tenticles.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_spirits_0.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ydr/tstudio_legion_halloween_spirits_1.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ymap/tstudio_legion_halloween_placement.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/legion/ymap/tstudio_legion_halloween_placement_lod.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/overrides/tstudio_lsextension_asset_campfirezone.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/overrides/tstudio_lsextension_asset_ext_torch.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/overrides/tstudio_lsextension_asset_lamp01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/overrides/tstudio_lsextension_asset_lamp02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/overrides/tstudio_lsextension_asset_lamp03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/overrides/tstudio_lsextension_park1_lp.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/overrides/tstudio_lsextension_park2_lp.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ycd/anim@tstudio_legion_halloween_5.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ydr/tstudio_legion_halloween_light_p.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ydr/tstudio_legion_halloween_light_tenticles_n.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ydr/tstudio_legion_halloween_light_tenticles_s.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ydr/tstudio_legion_halloween_ouija_tstudio.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ydr/tstudio_legion_halloween_ouija_yn.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ydr/tstudio_legion_halloween_spirits_2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ydr/tstudio_legion_halloween_spirits_3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ydr/tstudio_lsextension_halloween_water_1.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ydr/tstudio_lsextension_halloween_water_2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ymap/tstudio_lsextension_halloween_placement_lod.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ymap/tstudio_lsextension_n_halloween_placement.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/lsextension/ymap/tstudio_lsextension_s_halloween_placement.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/_manifest_peak_halloween.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/overrides/tstudio_legiontowers_asset_walllight01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ycd/anim@tstudio_peak_halloween.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ycd/anim@tstudio_peak_halloween_sps.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ycd/anim@tstudio_peak_halloween_sps_lod.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ycd/anim@tstudio_peak_halloween_uv.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_banner_webs_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_banner_webs_02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_candy_bucket_1.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_candy_bucket_2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_candy_bucket_3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_cauldren_anim.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_dirtpile_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_ghost_cat.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_ghostface.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_grave_00.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_grave_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_grave_02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_grave_03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_grave_04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_grave_05.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_grave_06.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_ground_ooze.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_handdoor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_ouija_board.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_ouija_tstudio.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_ouija_yn.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_palm_ooze.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_palm_ooze_c.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_pillar_ooze.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_pumpkin01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_pumpkin02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_pumpkin03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_pumpkin04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_pumpkin05.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_purple_wings.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_red_wings.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_skel_hand.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_spider_00.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_spider_an.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_sps_bans_frame.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_sps_banshee.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_sps_banshee_lod.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_sps_dan_gho_frame.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_sps_ghost_dance.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_sps_ghost_dance_lod.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_sps_wall_fa_frame.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_sps_wall_face.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ydr/tstudio_peak_halloween_sps_wall_face_lod.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/yft/tstudio_peak_halloween_cloth_ghost.yft`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/yft/tstudio_peak_halloween_skeleton.yft`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ymap/tstudio_peak_halloween_bridge_placement.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ymap/tstudio_peak_halloween_placement.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ymap/tstudio_peak_halloween_sps.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ymap/tstudio_peak_halloween_sps_lods.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ytd/tstudio_peak_halloween_txd.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ytyp/tstudio_peak_halloween_props_a.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ytyp/tstudio_peak_halloween_sps_lods.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ytyp/tstudio_peak_halloween_sps_props.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/peak/ytyp/tstudio_peak_halloween_uv_anims.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/_manifest_tsudio_legion_halloween.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/vanilla/prop_wall_light_02a.yft`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ycd/anim@tstudio_legion_halloween.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ycd/anim@tstudio_legion_halloween_2.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ycd/anim@tstudio_legion_halloween_3.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ycd/anim@tstudio_legion_halloween_4.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ycd/nightmare_anim.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ycd/zombies_animations.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_anim_billboard_c.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_arbour_00.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_arbour_00s.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_arbour_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_arbour_02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_arbour_03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_arbour_04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_banner_webs_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_banner_webs_02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_bats.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_candy_bucket_1.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_candy_bucket_2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_candy_bucket_3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_cauldren_anim.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_dirtpile_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_flail_tent_lod.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_ghostface.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_grave_00.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_grave_02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_grave_03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_grave_06.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_grave_10.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_grave_12.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_grave_14.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_handdoor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_light_o.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_ouija_board.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_pumpkin01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_pumpkin02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_pumpkin03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_pumpkin04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_pumpkin05.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_purple_wings.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_red_wings.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_scarecrow01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_skel_hand.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudio_legion_halloween_spider_00.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ydr/tstudios_legion_halloween_spirits_uv.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/yft/tstudio_legion_halloween_cloth_ghost_2.yft`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/yft/tstudio_legion_halloween_flail_tent.yft`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ytd/tstudio_legion_halloween_billboard_txd.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ytd/tstudio_legion_halloween_txd.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ytyp/tstudio_legion_halloween_billboards_lod.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ytyp/tstudio_legion_halloween_props_a.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/stream/shared/ytyp/tstudio_legion_halloween_props_b.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zaddon_halloween/ymap_loader.lua`
```diff
- Gelöscht
```

## 2026-10-31 22:23 Uhr
**+0** neu · **~5** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_minijobs/client/admin.lua`
```diff
+        position = 'middle-left',
+        { type = 'checkbox', label = 'Fahrzeug erforderlich', default = job.vehicle and job.vehicle.required or false },
+        { type = 'checkbox', label = 'Teamplay erlauben', default = job.allowTeamplay or false },
-        requiredJob = input[13],
+        requiredJob = input[15],
+        allowTeamplay = input[7],
-        vehicle = { model = input[4], platePrefix = tostring(input[5] or 'JOB'):sub(1, 6) },
-        payment = { min = input[6], max = input[7], perPoint = input[8], bonus = input[9] },
+        vehicle = { model = input[4], platePrefix = tostring(input[5] or 'JOB'):sub(1, 6), required = input[6] },
+        payment = { min = input[8], max = input[9], perPoint = input[10], bonus = input[11] },
```
`~ resources/[selfcode]/rmc_minijobs/client/interactions.lua`
```diff
+RegisterNetEvent('minijob:client:teamInvite', function(inviterId, inviterName, jobId, jobLabel)
+    local alert = lib.alertDialog({
+        header = 'Team-Einladung',
+        content = ('%s möchte dich einladen für den Job: %s'):format(inviterName, jobLabel),
+        centered = true,
+        cancel = true,
+    })
+    if alert == 'confirm' then
+        lib.callback.await('minijob:server:acceptInvite', false, inviterId, jobId)
+    end
```
`~ resources/[selfcode]/rmc_minijobs/client/main.lua`
```diff
+    team = { id = nil, members = {} },
```
`~ resources/[selfcode]/rmc_minijobs/client/runner.lua`
```diff
+CreateThread(function()
+    while true do
+        local asg = TR.State.assignment
+        if not asg then
+            Wait(700)
+        else
+            local job = Utils.FindMinijob(asg.jobId)
+            if job and job.vehicle and job.vehicle.required then
+                local playerPed = PlayerPedId()
+                if IsPedInAnyVehicle(playerPed, false) then
```
`~ resources/[selfcode]/rmc_minijobs/server/admin.lua`
```diff
+        allowTeamplay = false,
+            required = false,
+    if patch.allowTeamplay ~= nil then job.allowTeamplay = patch.allowTeamplay == true end
+
+local teams = {}
+
+lib.callback.register('minijob:server:invitePlayer', function(source, targetId, jobId)
+    local job = Utils.FindMinijob(jobId)
+    if not job or not job.allowTeamplay then
+        return { ok = false, message = 'Teamplay ist für diesen Job nicht aktiviert.' }
```

## 2026-10-31 21:23 Uhr
**+0** neu · **~3** geändert · **-1** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
+    "lastBackup": 1793476361,
-        {
-            "backupFile": "banlist_20_34_26_10_2026.json",
-            "backupDate": "20_34_26_10_2026",
-            "id": 11,
-            "backupTimestamp": 1793043270
-        },
-        {
-            "backupFile": "banlist_20_36_26_10_2026.json",
-            "backupDate": "20_36_26_10_2026",
```
`~ resources/[manuell_start]/ox_inventory/data/items.lua`
```diff
-	["metallbarren"] = {
-		label = "Metallbarren",
-		weight = 2500,
-		stack = true,
-		close = true,
-	},	
-
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789","channelId":"1512475286229356617"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194","channelId":"1557386329686413342"}
+{"categoryId":"1551161549018759170","webhooks":{"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353","channelId":"1551161585614061618"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"15529710
```
`− resources/[manuell_start]/ox_inventory/web/images/metallbarren.png`
```diff
- Gelöscht
```

## 2026-10-31 20:23 Uhr
**+4** neu · **~3** geändert · **-0** gelöscht
`+ resources/[manuell_start]/ox_inventory/web/images/mechanikteile.png`
```diff
+ Neue Datei
```
`+ resources/[manuell_start]/ox_inventory/web/images/metallteile.png`
```diff
+ Neue Datei
```
`+ resources/[manuell_start]/ox_inventory/web/images/verbundmaterial.png`
```diff
+ Neue Datei
```
`+ resources/[manuell_start]/ox_inventory/web/images/waffenplane.png`
```diff
+ Neue Datei
```
`~ resources/[manuell_start]/ox_inventory/data/items.lua`
```diff
-	["waffengehause"] = {
-		label = "Waffengehäuse",
-		weight = 300,
+	--- NEUE WAFFENBAUTEILE---
+
+	["metallteile"] = {
+		label = "Metallteile",
+		weight = 500,
-	["waffenlauf"] = {
-		label = "Waffenlauf",
```
`~ resources/[manuell_start]/ox_inventory/web/images/metallbarren.png`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-31T17:45:17Z","categoryId":"1551161549018759170","webhooks":{"sozialstunden":{"channelId":"1552971081491419187","url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709"},"lager":{"channelId":"1551161580324921455","url":"https://discord
+{"webhooks":{"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789","channelId":"1512475286229356617"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194","channelId":"1557386329686413342"}
```

## 2026-10-31 19:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-31T17:19:30Z","categoryId":"1551161549018759170","webhooks":{"esx_resources":{"channelId":"1557386346782265425","url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076"},"poster":{"channelId":"1560007812342489120","url":"https://discor
+{"updatedAt":"2026-10-31T17:45:17Z","categoryId":"1551161549018759170","webhooks":{"sozialstunden":{"channelId":"1552971081491419187","url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709"},"lager":{"channelId":"1551161580324921455","url":"https://discord
```
`~ resources/[stream]/[mlo]/[tstudio]/tstudio_redstuner/config.lua`
```diff
-        {
-            Id = 1,
-            Pos = vector3(-679.40985107422, -2444.626464843, 13.257986068726),
-            GetOutPos = vector4(-684.7432, -2440.2537, 14.2635, 155.3924),
-        },
-        {
-            Id = 2,
-            Pos = vector3(-676.12170410156, -2446.5249023438, 13.257986068726),
-            GetOutPos = vector4(-684.7432, -2440.2537, 14.2635, 155.3924),
-        }
```
