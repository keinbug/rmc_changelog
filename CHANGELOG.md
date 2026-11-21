# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

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

## 2026-11-20 22:23 Uhr
**+2** neu · **~6** geändert · **-25** gelöscht
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_57_20_11_2026.json`
```diff
+ Neue Datei
```
`+ resources/[esx_addons]/EasyAdmin/backups/banlist_21_59_20_11_2026.json`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-    "lastBackup": 1795121802,
+    "lastBackup": 1795208376,
-            "backupDate": "21_41_15_11_2026",
-            "backupTimestamp": 1794775302,
-            "backupFile": "banlist_21_41_15_11_2026.json"
-        },
-        {
-            "backupDate": "21_43_15_11_2026",
-            "backupTimestamp": 1794775427,
-            "id": 11,
```
`~ resources/[selfcode]/lb-tvcast/client/main.lua`
```diff
-local function drawScreen(q, txn)
-    local a, b, c, d = q[1], q[2], q[3], q[4]
-    -- Vorder- und Rückseite, damit die Zeichenrichtung keine Rolle spielt
-    DrawSpritePoly(a.x, a.y, a.z, b.x, b.y, b.z, c.x, c.y, c.z, 255, 255, 255, 255, TXD, txn, 0.0, 0.0, 1.0, 1.0, 0.0, 1.0, 1.0, 1.0, 1.0)
-    DrawSpritePoly(a.x, a.y, a.z, c.x, c.y, c.z, d.x, d.y, d.z, 255, 255, 255, 255, TXD, txn, 0.0, 0.0, 1.0, 1.0, 1.0, 1.0, 0.0, 1.0, 1.0)
-    DrawSpritePoly(a.x, a.y, a.z, c.x, c.y, c.z, b.x, b.y, b.z, 255, 255, 255, 255, TXD, txn, 0.0, 0.0, 1.0, 1.0, 1.0, 1.0, 1.0, 0.0, 1.0)
-    DrawSpritePoly(a.x, a.y, a.z, d.x, d.y, d.z, c.x, c.y, c.z, 255, 255, 255, 255, TXD, txn, 0.0, 0.0, 1.0, 0.0, 1.0, 1.0, 1.0, 1.0, 1.0)
+-- points: obere Kante links->rechts, dann untere Kante links->rechts (siehe client/screen.lua)
+local function drawScreen(points, txn)
+    local count = #points / 2
```
`~ resources/[selfcode]/lb-tvcast/client/screen.lua`
```diff
+--
+-- Eine Bildfläche ist eine Liste von Punkten in Weltkoordinaten:
+-- erst die obere Kante von links nach rechts, dann die untere Kante von links nach rechts.
+-- 4 Punkte = flaches Bild, mehr Punkte = Bild folgt einer gewölbten Leinwand.
+local PROBE = 0.8       -- so weit vor/hinter der vermuteten Fläche wird nach der echten Oberfläche gesucht
+local SURFACE_GAP = 0.012 -- Abstand des Bildes zur Oberfläche (gegen Flackern)
+local COLUMNS = 10      -- Unterteilung bei gewölbten Flächen
+
-local function quadFrom(center, normal, up, width, height)
-    local right = normalize(crossProduct(-normal, up)) -- rechts aus Sicht des Zuschauers
```
`~ resources/[selfcode]/lb-tvcast/config.lua`
```diff
-Config.ScreenInset = 0.06         -- Rand (Anteil), der bei erkannten TV-Modellen für den Rahmen abgezogen wird
-Config.WallScreen  = {            -- Bildbreite (Meter), wenn auf eine Wand / Map-Fernseher gezielt wird
+Config.OnlyProps   = true         -- true = beim Zielen nur Props (Objekte), keine Wände / kein Boden / keine Map-Teile
+Config.ScreenInset = 0.06        -- Rand (Anteil), der bei erkannten TV-Modellen für den Rahmen abgezogen wird
+Config.WallScreen  = {            -- nur bei OnlyProps = false: Bildbreite (Meter) auf einer Wand / einem Map-Fernseher
-    max = 4.0,
+    max = 6.0,
```
`~ resources/[selfcode]/lb-tvcast/locales.lua`
```diff
+        aim_none_props = 'Ziele auf einen Fernseher oder eine Leinwand~n~~INPUT_FRONTEND_RRIGHT~ Abbrechen',
+        aim_none_props = 'Aim at a TV or a screen prop~n~~INPUT_FRONTEND_RRIGHT~ Cancel',
```
`~ resources/[selfcode]/lb-tvcast/server/main.lua`
```diff
+-- Bildfläche: obere Kante links->rechts, dann untere Kante links->rechts (4 bis 40 Punkte)
-    if type(c) ~= 'table' or #c ~= 4 then return false end
-    for i = 1, 4 do
+    if type(c) ~= 'table' then return false end
+    local n = #c
+    if n < 4 or n > 40 or n % 2 ~= 0 then return false end
+    for i = 1, n do
-    local width, height = #(c[2] - c[1]), #(c[4] - c[1])
-    return width >= 0.2 and width <= 8.0 and height >= 0.1 and height <= 5.0
+    local count = n // 2
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_41_15_11_2026.json`
```diff
- Gelöscht
```
`− resources/[esx_addons]/EasyAdmin/backups/banlist_21_43_15_11_2026.json`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/.fxap`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/Readme.txt`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/client/main.lua`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/config.lua`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/BebasNeueBold.ttf`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/img/close.png`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/scripts.js`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/styles.css`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/tv/img/background.png`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/tv/index.html`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/tv/style.css`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/ui.html`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/video.css`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/video.html`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/html/video.js`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/language/main.lua`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/server/main.lua`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/server/other.lua`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/sql_ESX.sql`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/sql_QBCORE.sql`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/stream/rtxtv.gfx`
```diff
- Gelöscht
```
`− resources/[rtx]/rtx_tv/utils/mock_data.js`
```diff
- Gelöscht
```

## 2026-11-20 21:23 Uhr
**+20** neu · **~7** geändert · **-102** gelöscht
`+ resources/[selfcode]/lb-tvcast/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/client/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/client/screen.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/dui/index.html`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/locales.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/server/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/server/settings.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/ui/app.js`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/ui/assets/icon.svg`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/ui/blank.html`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/ui/dev.js`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/ui/index.html`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/ui/locales.js`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-tvcast/ui/style.css`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/.claude/settings.local.json`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/client/jammer.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/html/photo/jammer.js`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/server/jammer.lua`
```diff
+ Neue Datei
```
`~ resources/[manuell_start]/ox_inventory/data/items.lua`
```diff
+	["jammer"] = {
+		label = "Störsender",
+		weight = 2500,
+		stack = false,
+		close = true,
+		consume = 0,
+		description = "Mobiler Funk-Störsender. Benutzen, um ihn aufzustellen – stört den Funk im Umkreis.",
+		client = {
+			export = "rmc_core.useJammer",
+			image = "jammer.png",
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "receiver_identifier": "char1:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "reason": "Einzahlung auf Bankkonto",
+            "sender_name": "Geldbörse",
+            "sender_identifier": "bank",
+            "date": "2026/11/20 - 20:35:50",
+            "receiver_name": "Coco Milano",
+            "type": "deposit",
+            "value": 145000
+        },
```
`~ resources/[selfcode]/rmc_aduty/config/cl_config.lua`
```diff
-    -- Pulsierendes Leuchten an den Punkten des Aduty-Outfits (fuer alle Spieler sichtbar).
-    ["GLOW"] = {
-        ["Enabled"] = true,
-        ["Color"] = { r = 0, g = 230, b = 255 }, -- Tuerkis, passend zu den Punkten
-        ["Distance"] = 40.0,   -- bis zu dieser Entfernung wird der Effekt gezeichnet
-        ["Range"] = 0.9,       -- Reichweite jedes Lichtpunkts in Metern
-        ["Intensity"] = 6.0,   -- Helligkeit
-        ["PulseSpeed"] = 2.5,  -- hoeher = schnelleres Pulsieren
-        ["PulseDepth"] = 0.6   -- 0 = dauerhaft an, 1 = pulsiert bis ganz dunkel
-    },
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+-- ====== Funk-Störsender (Jammer) ======
+-- Item benutzen -> Störsender aufstellen. Wer in der Zone steht, hört Funk nur noch
+-- verrauscht / abgehackt (im Kern gar nicht mehr). Funkt jemand AUS der Zone heraus,
+-- hören ihn die anderen ebenfalls gestört. Nutzt SaltyChat (SetRadioVolume + IsSending).
+Config.Jammer = {
+    Enabled = true,
+    Resource = 'saltychat',
+    Item = 'jammer',
+    Prop = 'ch_prop_ch_mobile_jammer_01x',
+
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"clothing_strip":{"webhookId":"1551161592467423353","channelId":"1551161585614061618","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"faction":{"webhookId":"1551161573194731652","channelId":"1551161570439208960","url":"https://disco
+{"categoryId":"1551161549018759170","webhooks":{"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557386346782265425","webhookId":"1557386349395583076"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","channelId":"15529898236
```
`~ resources/[selfcode]/rmc_core/fxmanifest.lua`
```diff
-fx_version 'cerulean'
-game 'gta5'
-lua54 'yes'
-
-
-author 'KeinBug'
-description 'RMC-Core'
-name 'rmc_core'
-version '1.0.0'
-
```
`~ resources/[selfcode]/rmc_core/html/photo/index.html`
```diff
+    <script src="jammer.js"></script>
```
`− resources/[selfcode]/rmc_aduty/client/glow.lua`
```diff
- Gelöscht
```
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

## 2026-11-20 20:23 Uhr
**+4** neu · **~16** geändert · **-0** gelöscht
`+ cfg/rechte.cfg.bak-rolesync`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_aduty/client/glow.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_aduty/client/teleport.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/server/join.lua.bak-rolesync`
```diff
+ Neue Datei
```
`~ cfg/rechte.cfg`
```diff
+#### API Sync Roles: darf Gruppen-Zuordnungen setzen
+add_ace resource.api_new command.add_principal allow
+add_ace resource.api_new command.remove_principal allow
+
+
+
-set ea_logIdentifier "discord,license"
+set ea_logIdentifier "discord,license"
+# api_new Role Sync: darf Gruppen-Zuordnungen setzen
+add_ace resource.api_new command.add_principal allow
```
`~ resources/[esx_addons]/EasyAdmin/banlist.json`
```diff
-[
-    {
-        "name": "Unknown",
-        "expireString": "20/11/2026 \t19:22:18",
-        "reason": "AFFE ( Spielername: Unknown - table: 5aa66d2c7ddf7436 ), \nGebannt von: Sebbi",
-        "banner": "Sebbi",
-        "identifiers": [
-            "license:dcdd8750773c33c2ce3ff658853fe0c909367dba"
-        ],
-        "expire": 1795198938,
```
`~ resources/[esx_addons]/ks-multicharacter/fxmanifest.lua`
```diff
-    'ks-libs-configs/ks-sql-slots.lua', -- muss VOR ks-server.lua geladen werden
```
`~ resources/[esx_addons]/ks-multicharacter/ks-libs-configs/ks-config.lua`
```diff
-    Enabled = true,                 -- false = altes Verhalten (Discord-Rollen)
+    Enabled = false,                -- false = altes Verhalten (Discord-Rollen per Bot-Token), true = Slots aus SQL
```
`~ resources/[esx_addons]/ks-multicharacter/ks-libs-configs/ks-open-server.lua`
```diff
-ksConfig.DiscordBotToken = "***TOKEN***"
+ksConfig.DiscordBotToken = "***TOKEN***"
```
`~ resources/[esx_addons]/ks-multicharacter/ks-libs-configs/ks-sql-slots.lua`
```diff
+
+
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:726b2e82f8613191a738a5158a2b2cd5c7dbeea1": [
+    "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5": [
-            "sender_identifier": "char2:726b2e82f8613191a738a5158a2b2cd5c7dbeea1",
-            "date": "2026/11/19 - 19:00:53",
-            "value": 2500,
-            "sender_name": "Michael Auer",
+            "value": 500,
+            "sender_identifier": "char1:f6a7d1d68111745581e11c74b2f45c0a9822fca5",
+            "type": "withdraw",
+            "receiver_name": "cd_garage",
```
`~ resources/[selfcode]/api_new/server/rolesync.lua`
```diff
-      1. Join: Card "Discord-Rollen werden geprüft..." (CheckSeconds), danach bei einer Team-Rolle
-         die Card "Du hast die Rolle X bekommen" (ResultSeconds). Der Role Sync blockiert nie den Join.
+      1. Join: rmc_core (server/join.lua) zeigt über die Exports RoleSyncBegin/RoleSyncResult die Card
+         "Discord-Rollen werden geprüft..." (CheckSeconds) und danach bei einer Team-Rolle
+         "Du hast die Rolle X bekommen" (ResultSeconds).
-local function connectingDiscord(src)
-    for _ = 1, 12 do
-        for _, id in ipairs(GetPlayerIdentifiers(src) or {}) do
-            if id:sub(1, 8) == 'discord:' then return id:sub(9) end
-        end
```
`~ resources/[selfcode]/rmc_aduty/client/client.lua`
```diff
+        local smooth = cfg["Smooth"] == true
+        local boostMultiplier = speedCfg["BoostMultiplier"] or 3.0
+        -- 14-17 Waffenwechsel, 99/100 Fahrzeugwaffen, 81/82 Radio
+        local scrollControls = { 14, 15, 16, 17, 99, 100, 81, 82 }
-            -- Jeder Shift-Druck schaltet eine Stufe weiter; nach der letzten
-            -- Geschwindigkeit beginnt die Liste wieder von vorne.
-            if justPressed(21) then
-                speedLevel = speedLevel % #speedLevels + 1
+            -- Mausrad gehoert im Noclip nur der Geschwindigkeit: Waffen- und
+            -- Radiowechsel werden solange blockiert.
```
`~ resources/[selfcode]/rmc_aduty/config/cl_config.lua`
```diff
-cl_config = {}
-
-cl_config.general = {
-    language = "de",
-    screenshot = {
-        enable = true,
-        resource = "screenshot-basic"
-    }
-}
-
```
`~ resources/[selfcode]/rmc_aduty/config/sv_config.lua`
```diff
+        teleport_waypoint = 10181046,
+        -- Leer = Teleport-Logs gehen an "actions" (bzw. kein Discord-Log).
+        teleport = "",
+            ["teleport_waypoint"] = "%s hat sich zum Wegpunkt teleportiert",
+            ["teleport_waypoint"] = "%s teleported to the waypoint",
```
`~ resources/[selfcode]/rmc_aduty/server/server.lua`
```diff
+    teleport_waypoint = "teleport",
+    teleport_waypoint = { title = "Teleport", emoji = "ghost", colorKey = "teleport_waypoint" },
+        if not apiType then apiType, apiAction = action:match("^(teleport)_(waypoint)$") end
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-11-20T17:01:07Z","webhooks":{"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"},"poster":{"url":"https://discord.com/api/webhooks/1560007815156998144/
+{"categoryId":"1551161549018759170","webhooks":{"clothing_strip":{"webhookId":"1551161592467423353","channelId":"1551161585614061618","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"faction":{"webhookId":"1551161573194731652","channelId":"1551161570439208960","url":"https://disco
```
`~ resources/[selfcode]/rmc_core/server/join.lua`
```diff
-local DISCORD_EPOCH_MS = 1420070400000
-
-
-local ID_PREFIX = {
-    steam   = 'steam:',
-    discord = 'discord:',
-    xbl     = 'xbl:',
-    live    = 'live:',
-    license = 'license:',
-    license2= 'license2:',
```
`~ server.cfg`
```diff
(Secrets — Inhalt unterdrückt)
```
`~ server.cfg.bkp`
```diff
(Secrets — Inhalt unterdrückt)
```

## 2026-11-20 19:23 Uhr
**+3** neu · **~3** geändert · **-0** gelöscht
`+ resources/[selfcode]/api_new/fxmanifest.lua.bak-rolesync`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/server/rolesync.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/api_new/settings.lua.bak-rolesync`
```diff
+ Neue Datei
```
`~ resources/[esx_addons]/EasyAdmin/banlist.json`
```diff
-        "banid": 1,
-        "reason": "Test ( Spielername: Unknown - table: 3c6ef372fe94f824 ), \nGebannt von: Sebbi",
-        "expireString": "20/11/2026 \t19:17:00",
-        "identifiers": [
-            "license:dcdd8750773c33c2ce3ff658853fe0c909367dba"
-        ],
-        "banner": "Sebbi",
-        "expire": 1795198620,
-        "name": "Unknown"
-    },
```
`~ resources/[selfcode]/api_new/fxmanifest.lua`
```diff
+    'server/rolesync.lua',
```
`~ resources/[selfcode]/api_new/settings.lua`
```diff
+
+-- Role Sync (server/rolesync.lua): Discord-Rolle -> Ingame-Gruppe beim Join
+-- Token und Guild kommen aus rmc_core (server/discord_config.lua bzw. Convar rmc_discord_bot_token).
+Settings.RoleSync = {
+    Enabled = true,
+    Roles = { -- Reihenfolge = Priorität (die erste passende Rolle gewinnt)
+        { id = '1573394820427157634', label = 'Owner',   group = 'owner' },
+        { id = '1573394990757978212', label = 'Admin',   group = 'admin' },
+        { id = '1573395118583709877', label = 'Mod',     group = 'mod' },
+        { id = '1573395173361197136', label = 'Support', group = 'support' },
```

## 2026-11-20 18:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"esx_jobs":{"channelId":"1557386361172918374","webhookId":"1557386364578955274","url":"https://discord.com/api/webhooks/1557386364578955274/***"},"troll":{"channelId":"1552971103910236172","webhookId":"1552971107500433498","url":"https://discord.com/a
+{"categoryId":"1551161549018759170","updatedAt":"2026-11-20T17:01:07Z","webhooks":{"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"},"poster":{"url":"https://discord.com/api/webhooks/1560007815156998144/
```

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
