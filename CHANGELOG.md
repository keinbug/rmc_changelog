# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

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

## 2026-11-15 22:22 Uhr
**+7** neu · **~4** geändert · **-2** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_41_15_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_43_15_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/admins.json`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/fxmanifest.lua.bak-txadmin`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/main.lua.bak-keylog`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/txadmin.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/settings.lua.bak-txadmin`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupFile": "banlist_21_23_10_11_2026.json",
-            "backupTimestamp": 1794342199,
-            "id": 11,
-            "backupDate": "21_23_10_11_2026"
-        },
-        {
-            "backupFile": "banlist_21_25_10_11_2026.json",
-            "backupTimestamp": 1794342324,
-            "id": 11,
-            "backupDate": "21_25_10_11_2026"
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/txadmin.lua',
```
`~ resources/[selfcode]/api_new/server/main.lua`
```diff
-        print(('[api_new] Ungültiger API-Key von %s'):format(ip))
+        -- Aufrufe ganz ohne Key (z. B. Status-Monitor des Panels) nicht loggen, nur falsche Keys
+        if key ~= '' then print(('[api_new] Ungültiger API-Key von %s'):format(ip)) end
```
`~ resources/[selfcode]/api_new/settings.lua`
```diff
+
+-- txAdmin-Endpunkte (/txadmin/...): Accounts anzeigen und über das Panel verwalten
+Settings.TxAdmin = {
+    Enabled    = true,
+    Url        = "http://127.0.0.1:40120",                 -- Web-Port von txAdmin
+    Username   = "RMC-Panel",                              -- eigener txAdmin-Account für das Panel
+    Password   = "xqh6AXQLWNJMxBNyHBw3",                                       -- dessen Passwort (leer = nur lesen)
+    AdminsFile = "/home/FiveM/server/txData/admins.json",
+}
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_23_10_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_25_10_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-15 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"esx_test":{"channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194"},"lager":{"channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879
+{"updatedAt":"2026-11-15T17:01:09Z","categoryId":"1551161549018759170","webhooks":{"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490","channelId":"1513950191936344245"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***"
```

## 2026-11-15 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-14T23:00:39Z","webhooks":{"einreise":{"webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431"},"adminjail":{"webhookId":"1551161578009796630","url":"https://discord.com/api/webhooks/155116157800979663
+{"webhooks":{"esx_test":{"channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194"},"lager":{"channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879
```

## 2026-11-15 00:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-14T17:01:28Z","categoryId":"1551161549018759170","webhooks":{"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913"},"joinleave":{"webhookId":"1570427416076091415","url":"https://disc
+{"updatedAt":"2026-11-14T23:00:39Z","webhooks":{"einreise":{"webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431"},"adminjail":{"webhookId":"1551161578009796630","url":"https://discord.com/api/webhooks/155116157800979663
```

## 2026-11-14 22:23 Uhr
**+2** neu · **~1** geändert · **-2** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_37_14_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_40_14_11_2026.json`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1794602238,
-            "id": 11,
-            "backupTimestamp": 1794255639,
-            "backupFile": "banlist_21_20_09_11_2026.json",
-            "backupDate": "21_20_09_11_2026"
-        },
-        {
-            "id": 11,
-            "backupTimestamp": 1794255764,
-            "backupFile": "banlist_21_22_09_11_2026.json",
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_20_09_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_22_09_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-14 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-14T09:01:16Z","categoryId":"1551161549018759170","webhooks":{"freecam_photo":{"channelId":"1551520126367572008","url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284"},"minijobs":{"channelId":"1570426349213188196","url":"https://disc
+{"updatedAt":"2026-11-14T17:01:28Z","categoryId":"1551161549018759170","webhooks":{"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913"},"joinleave":{"webhookId":"1570427416076091415","url":"https://disc
```

## 2026-11-14 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-13T23:01:00Z","webhooks":{"hotdog":{"webhookId":"1474547103081566412","channelId":"1474547082076622979","url":"https://discord.com/api/webhooks/1474547103081566412/***"},"esx":{"webhookId":"1557386326951592027","channelId":"142010343056291037
+{"updatedAt":"2026-11-14T09:01:16Z","categoryId":"1551161549018759170","webhooks":{"freecam_photo":{"channelId":"1551520126367572008","url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284"},"minijobs":{"channelId":"1570426349213188196","url":"https://disc
```

## 2026-11-14 00:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068","webhookId":"1471556835994767400"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618","webhookId":"15511615924674
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-13T23:01:00Z","webhooks":{"hotdog":{"webhookId":"1474547103081566412","channelId":"1474547082076622979","url":"https://discord.com/api/webhooks/1474547103081566412/***"},"esx":{"webhookId":"1557386326951592027","channelId":"142010343056291037
```

## 2026-11-13 22:23 Uhr
**+2** neu · **~1** geändert · **-2** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_35_13_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_37_13_11_2026.json`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1794515602,
+    "lastBackup": 1794602238,
-            "backupTimestamp": 1794169013,
-            "backupDate": "21_16_08_11_2026",
-            "backupFile": "banlist_21_16_08_11_2026.json"
+            "backupTimestamp": 1794255639,
+            "backupFile": "banlist_21_20_09_11_2026.json",
+            "backupDate": "21_20_09_11_2026"
-            "backupTimestamp": 1794169138,
-            "backupDate": "21_18_08_11_2026",
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_16_08_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_18_08_11_2026.json`
```diff
- Gelöscht
```

## 2026-11-13 20:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "type": "withdraw",
+            "sender_identifier": "char1:51a4fca1e0d1af9e02314c787e76ada4e063cd38",
+            "reason": "Fahrzeugrückgabegebühr",
+            "value": 2500,
+            "date": "2026/11/13 - 20:06:54",
+            "receiver_name": "cd_garage",
+            "receiver_identifier": "cd_garage",
+            "sender_name": "Rafael Sanchez"
+        },
```
`~ resources/[selfcode]/api_new/server/easyadmin.lua`
```diff
-    POST   /easyadmin/ban                    { identifiers=[...], reason, duration }  Offline bannen
+    POST   /easyadmin/ban                    { identifiers=[...], reason, duration, name? }  Offline bannen (name -> statt "Unknown")
+    -- Offline-Bans: EasyAdmin kennt den Namen nicht und speichert "Unknown".
+    -- Name aus dem Request ({ name = "..." }, z.B. vom Panel) übernehmen und im Ban speichern.
+    local name = type(body.name) == 'string' and body.name:gsub('%s+', ' '):match('^%s*(.-)%s*$'):sub(1, 64) or ''
+    if name ~= '' and (ban.name == nil or ban.name == '' or ban.name == 'Unknown') then
+        ban.name = name
+        -- Server-seitig getriggert -> source = Konsole -> Rechteprüfung in EasyAdmin greift nicht
+        TriggerEvent('EasyAdmin:editBan', ban)
+    end
```

## 2026-11-13 19:23 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/banlist.json`
```diff
-[]
+[
+    {
+        "banid": 1,
+        "reason": "Test ( Spielername: Unknown - table: 3c6ef372fe94f824 ), \nGebannt von: Sebbi",
+        "expireString": "20/11/2026 \t19:17:00",
+        "identifiers": [
+            "license:dcdd8750773c33c2ce3ff658853fe0c909367dba"
+        ],
+        "banner": "Sebbi",
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:726b2e82f8613191a738a5158a2b2cd5c7dbeea1": [
+    "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38": [
-            "sender_identifier": "bank",
-            "receiver_identifier": "char2:726b2e82f8613191a738a5158a2b2cd5c7dbeea1",
-            "sender_name": "Savings Interest",
-            "reason": "Savings account interest payment (Period 27)",
+            "sender_identifier": "bank",
+            "reason": "Savings account interest payment (Period 43)",
-            "date": "2026/07/05 - 09:20:38",
-            "receiver_name": "Savings Account"
```

## 2026-11-13 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-13T09:00:41Z","categoryId":"1551161549018759170","webhooks":{"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455","webhookId":"1551161582942158879"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583
+{"webhooks":{"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068","webhookId":"1471556835994767400"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618","webhookId":"15511615924674
```

## 2026-11-13 10:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-11-13T05:36:28Z","categoryId":"1551161549018759170","webhooks":{"doors":{"url":"https://discord.com/api/webhooks/1559665847771988080/***","channelId":"1559665845330907296","webhookId":"1559665847771988080"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/**
+{"updatedAt":"2026-11-13T09:00:41Z","categoryId":"1551161549018759170","webhooks":{"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455","webhookId":"1551161582942158879"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583
```

## 2026-11-13 07:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"willkommen":{"channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005"},"esx_paycheck":{"channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357
+{"updatedAt":"2026-11-13T05:36:28Z","categoryId":"1551161549018759170","webhooks":{"doors":{"url":"https://discord.com/api/webhooks/1559665847771988080/***","channelId":"1559665845330907296","webhookId":"1559665847771988080"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/**
```

## 2026-11-13 01:23 Uhr
**+1** neu · **~3** geändert · **-0** gelöscht
`+ resources/.claude/settings.local.json`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"esx_resources":{"channelId":"1557386346782265425","webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"join":{"channelId":"1448120760391565352","webhookId":"1552971091771924552","url":"https://discord.c
+{"webhooks":{"willkommen":{"channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005"},"esx_paycheck":{"channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357
```
`~ resources/[selfcode]/rmc_core/server/webhook.lua`
```diff
+-- ============================================
+-- LOG-API (v1-api.rmc-rp.de) – wie bei rmc_aduty
+-- Jeder Log geht zusätzlich (zum Discord-Webhook) an die Log-API,
+-- inkl. Typ (type) und Aktion (action).
+-- Diese Datei ist server_script -> Key gelangt nicht zum Client.
+-- Überschreibbar per server.cfg: set rmc_logapi_url / set rmc_logapi_key
+-- ============================================
+local LogApi = {
+    enabled = GetConvar("rmc_logapi_enabled", "true") == "true",
+    url     = GetConvar("rmc_logapi_url", "https://v1-api.rmc-rp.de"),
```
`~ resources/[selfcode]/rmc_core/server/webhook_links.lua`
```diff
+-- Umgekehrte Suche: Webhook-URL -> Key (z.B. 'afk'). Wird von webhook.lua
+-- genutzt, um den Log-Typ für die Log-API zu bestimmen. 'default' zählt nicht.
+function GetWebhookKeyByUrl(url)
+    if type(url) ~= 'string' or url == '' then return nil end
+    for key, link in pairs(Links) do
+        if key ~= 'default' and link == url then return key end
+    end
+    return nil
+end
+
```

## 2026-11-13 00:23 Uhr
**+3** neu · **~8** geändert · **-0** gelöscht
`+ resources/[selfcode]/api_new/client/voice.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/garage.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/voice.lua`
```diff
+ Neue Datei
```
`~ resources/[cd]/cd_garage/server/features/impound.lua`
```diff
-end)
+end)
+
+-- ============================================================
+--  api_new (Admin-Panel): Fahrzeug ohne Gebühr aus dem Abschlepphof holen.
+--  Nötig, weil cd_garage abgeschleppte Fahrzeuge zusätzlich im Speicher (ImpoundData) hält.
+--  Bei einem cd_garage-Update diesen Block wieder ans Dateiende setzen.
+-- ============================================================
+exports('ApiUnimpound', function(plate, spawnVehicle)
+    local okRun, err = pcall(removeVehicleFromImpound, 0, plate, spawnVehicle == true)
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+            "sender_name": "Coco Milano",
+            "type": "withdraw",
+            "receiver_identifier": "cd_garage",
+            "receiver_name": "cd_garage",
+            "value": 500,
+            "date": "2026/11/12 - 23:56:36",
+            "reason": "Fahrzeugrückgabegebühr"
+        },
+        {
+            "sender_identifier": "char1:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
```
`~ resources/[selfcode]/api_new/README.md`
```diff
+
+---
+
+## SaltyChat (Funk & Voice)
+
+Läuft über die Server-Exports von `saltychat`. Funkkanäle liest der Client aus (ohne Antwort: `clientData: false`).
+
+### Voice-Status eines Spielers (Reichweite, lebendig, Funkkanäle, Lautsprecher)
+```bash
+curl "$API/voice/player/4" -H "X-API-Key: $KEY"
```
`~ resources/[selfcode]/api_new/client/vehicle.lua`
```diff
-local actions = {}
+-- Global, damit andere Module (client/voice.lua) eigene Aktionen ergänzen können
+ApiActions = ApiActions or {}
+local actions = ApiActions
+-- ============================================================
+--  Garage (server/garage.lua)
+-- ============================================================
+
+local ESXObj
+local function esx()
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/voice.lua',
+    'server/garage.lua',
+    'client/voice.lua',
```
`~ resources/[selfcode]/api_new/server/location.lua`
```diff
+Api.nearestPostal = function(x, y) return nearestPostal(x, y) end
+
```
`~ resources/[selfcode]/api_new/server/vehicle.lua`
```diff
+-- Für andere Module (server/voice.lua)
+Api.clientAction = clientAction
+Api.staffLog = discord
+
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"esx":{"channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027"},"doors":{"channelId":"1559665845330907296","url":"https://discord.com/api/webhooks/1559665847771988080/***","webhookId":"1559665847771988080"},"c
+{"categoryId":"1551161549018759170","webhooks":{"esx_resources":{"channelId":"1557386346782265425","webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"join":{"channelId":"1448120760391565352","webhookId":"1552971091771924552","url":"https://discord.c
```

## 2026-11-12 23:23 Uhr
**+5** neu · **~4** geändert · **-0** gelöscht
`+ resources/[selfcode]/api_new/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/client/location.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/client/vehicle.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/location.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/vehicle.lua`
```diff
+ Neue Datei
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/location.lua',
+    'server/vehicle.lua',
+    'client/location.lua',
+    'client/vehicle.lua',
```
`~ resources/[selfcode]/api_new/settings.lua`
```diff
+
+-- Standort-Endpunkte (/location/..., /locations)
+Settings.Location = {
+    Enabled         = true,
+    PostalResource  = 'rmc_core',              -- woher die PLZ-Liste kommt
+    PostalFile      = 'data/new-postals.json',
+    ClientTimeoutMs = 3000,                    -- so lange auf Straße/Gebiet vom Client warten
+}
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"clothing_strip":{"webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618"},"basicneeds":{"webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"14179176
+{"webhooks":{"esx":{"channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027"},"doors":{"channelId":"1559665845330907296","url":"https://discord.com/api/webhooks/1559665847771988080/***","webhookId":"1559665847771988080"},"c
```
`~ resources/[selfcode]/rmc_housing/fxmanifest.lua`
```diff
-description 'IPL-Housing für ESX: Mieten, Schlüssel, Interior-Stile, ox_inventory-Lager mit Stufen, Umkleide, Miete + Strom'
+description 'IPL-Housing'
```

## 2026-11-12 22:23 Uhr
**+4** neu · **~9** geändert · **-0** gelöscht
`+ resources/[manuell_start]/ox_inventory/data/items.lua.bak_flint`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/core.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/housing.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_housing/server/api.lua`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1794428965,
+    "lastBackup": 1794515602,
-            "id": 11,
-            "backupTimestamp": 1794082451,
-            "backupDate": "21_14_07_11_2026",
-            "backupFile": "banlist_21_14_07_11_2026.json"
-        },
-        {
-            "id": 11,
-            "backupTimestamp": 1794082576,
```
`~ resources/[manuell_start]/ox_inventory/data/items.lua`
```diff
-		server = {
-			export = 'rcore_camping.flint',
-		},
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char1:726b2e82f8613191a738a5158a2b2cd5c7dbeea1": [
-        {
-            "date": "2026/11/11 - 20:48:28",
-            "receiver_identifier": "cd_garage",
-            "value": 500,
-            "sender_identifier": "char1:726b2e82f8613191a738a5158a2b2cd5c7dbeea1",
-            "reason": "Sicherstellungsgebühr",
-            "type": "withdraw",
-            "sender_name": "Fabi Huber",
-            "receiver_name": "cd_garage"
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/housing.lua',
+    'server/core.lua',
```
`~ resources/[selfcode]/api_new/settings.lua`
```diff
+
+-- rmc_housing-Endpunkte (/housing/...)
+Settings.Housing = {
+    Enabled   = true,
+    Resource  = 'rmc_housing',
+    AdminName = 'API',         -- steht im Housing-Discord-Log, wenn im Body kein "admin" steht
+}
+
+-- rmc_core-Endpunkte (/core/...): Adminjail, Sozialstunden, Uncuff
+Settings.Core = {
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-12T17:01:00Z","webhooks":{"versicherung":{"webhookId":"1535733186921898004","channelId":"1535733166138990602","url":"https://discord.com/api/webhooks/1535733186921898004/***"},"esx_jobs":{"webhookId":"1557386364578955274","channelId":"1557386
+{"webhooks":{"clothing_strip":{"webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618"},"basicneeds":{"webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"14179176
```
`~ resources/[selfcode]/rmc_core/server/adminjail.lua`
```diff
+-- ---------- Exports für api_new (nur serverseitig) ----------
+local function jailOut(entry, extra)
+    local out = {
+        reason = entry.reason,
+        adminName = entry.adminName,
+        dogModel = entry.dogModel,
+        treatsCollected = entry.treatsCollected or 0,
+        timeReduced = entry.timeReduced or 0,
+    }
+    for k, v in pairs(extra or {}) do out[k] = v end
```
`~ resources/[selfcode]/rmc_core/server/sozialstunden.lua`
```diff
+-- ---------- Exports für api_new (nur serverseitig) ----------
+exports("SendToSozialstunden", SendToSozialstunden)
+
+exports("GetSozialstunden", function(targetId)
+    local rec = active[tonumber(targetId)]
+    if not rec then return nil end
+    return { serverId = tonumber(targetId), remaining = rec.remaining, reason = rec.reason }
+end)
+
+exports("ListSozialstunden", function()
```
`~ resources/[selfcode]/rmc_housing/fxmanifest.lua`
```diff
+    'server/api.lua',
```

## 2026-11-12 21:23 Uhr
**+9** neu · **~0** geändert · **-0** gelöscht
`+ resources/[selfcode]/api_new/api_new`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/client/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/easyadmin.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/http.js`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/package-lock.json`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/settings.lua`
```diff
+ Neue Datei
```
