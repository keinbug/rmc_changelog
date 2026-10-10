# 📋 FiveM Changelog

Automatisch generiert aus `/home/FiveM` — stündlich aktualisiert.

## 2026-10-10 13:23 Uhr
**+49** neu · **~11** geändert · **-3** gelöscht
`+ SAVE/dolu_tool/LICENSE`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/README.md`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/controls.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/instructionalButtons.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/keybinds.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/main.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/menu.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/modules/audio.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/modules/interior.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/modules/locations.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/modules/object.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/modules/peds.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/modules/vehicles.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/modules/weapons.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/modules/world.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/noclip.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/target.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/client/utils.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/config.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/ar.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/cs.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/da.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/de.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/en.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/es.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/fr.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/hu.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/it.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/ja.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/pl.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/pt.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/th.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/zh-cn.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/locales/zh-tw.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/server/main.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/server/version.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/shared/data/locations.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/shared/data/mloInteriors.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/shared/data/pedList.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/shared/data/radioStations.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/shared/data/staticEmitters.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/shared/data/vehicleList.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/shared/data/weaponList.json`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/shared/init.lua`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/web/build/assets/index-BzP1ScT8.js`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/web/build/assets/index-GPYetTxq.css`
```diff
+ Neue Datei
```
`+ SAVE/dolu_tool/web/build/index.html`
```diff
+ Neue Datei
```
`+ resources/[manuell_start]/oxmysql/web/build/assets/index-ed335b58.js`
```diff
+ Neue Datei
```
`~ resources/[manuell_start]/es_extended/server/config/discord.lua`
```diff
-    -- Optional: bestehende Nachrichten-ID. Leer = Bot merkt sich die ID selbst
-    PanelMessageId = "1551154479007793154",
+    -- Optional: Startwert, nur wenn panel.json noch keine Nachrichten-ID hat
+    PanelMessageId = "",
-    RefreshInterval = 15000,
+    RefreshInterval = 30000,
```
`~ resources/[manuell_start]/es_extended/server/functions.lua`
```diff
+    local metadata = xPlayer.metadata
+    if type(metadata) ~= "table" then
+        return
+    end
+
-    xPlayer.setMeta("health", GetEntityHealth(ped))
-    xPlayer.setMeta("armor", GetPedArmour(ped))
-    xPlayer.setMeta("lastPlaytime", xPlayer.getPlayTime())
+    metadata.health = GetEntityHealth(ped)
+    metadata.armor = GetPedArmour(ped)
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/bot.js`
```diff
-let heartbeatTimer = null;
+let sessionId = null;
+let resumeGatewayUrl = null;
+let reconnectTimer = null;
+let connectGeneration = 0;
+let builtFingerprint = null;
+let lastPanelFingerprint = null;
+function isMissingMessage(err) {
+    const msg = String(err && err.message ? err.message : err);
+    return /\b404\b/.test(msg) || msg.includes('10008') || msg.includes('Unknown Message');
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/bridge.lua`
```diff
+local resourceSummary = { at = 0, text = nil }
+local RESOURCE_CACHE_MS = 60000
+local function getResourceSummary()
+    local nowMs = GetGameTimer()
+    if resourceSummary.text and (nowMs - resourceSummary.at) < RESOURCE_CACHE_MS then
+        return resourceSummary.text
+    end
+
+    local resourceCount, startedCount = GetNumResources(), 0
+    for i = 0, resourceCount - 1 do
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558405954020581438"}
+{"channelId":"1550507281396011150","messageId":"1558439293457014815"}
```
`~ resources/[manuell_start]/oxmysql/README.md`
```diff
+<div align="center">
+
-![](https://img.shields.io/github/downloads/overextended/oxmysql/total?logo=github)
-![](https://img.shields.io/github/downloads/overextended/oxmysql/latest/total?logo=github)
-![](https://img.shields.io/github/contributors/overextended/oxmysql?logo=github)
-![](https://img.shields.io/github/v/release/overextended/oxmysql?logo=github) 
+[![](https://img.shields.io/github/downloads/overextended/oxmysql/total?style=for-the-badge&logo=github)](https://github.com/overextended/oxmysql/releases/latest/download/oxmysql.zip)
+[![](https://img.shields.io/github/downloads/overextended/oxmysql/latest/total?style=for-the-badge&logo=github)](https://github.com/overextended/oxmysql/releases/latest/download/oxmysql.zip)
+[![](https://img.shields.io/github/v/release/overextended/oxmysql?style=for-the-badge&logo=github)](https://github.com/overextended/oxmysql/releases/latest/)\
+[![](https://badges.5metrics.dev/oxmysql/serverRank.svg?style=for-the-badge)](https://5metrics.dev/resource/oxmysql)
```
`~ resources/[manuell_start]/oxmysql/dist/build.js`
```diff
+var __toCommonJS = (mod) => __copyProps(__defProp({}, "__esModule", { value: true }), mod);
-  "node_modules/lru.min/lib/index.js"(exports2) {
+  "node_modules/lru.min/lib/index.js"(exports3) {
-    Object.defineProperty(exports2, "__esModule", { value: true });
-    exports2.createLRU = void 0;
+    Object.defineProperty(exports3, "__esModule", { value: true });
+    exports3.createLRU = void 0;
-    exports2.createLRU = createLRU;
+    exports3.createLRU = createLRU;
-  "node_modules/named-placeholders/index.js"(exports2, module2) {
```
`~ resources/[manuell_start]/oxmysql/fxmanifest.lua`
```diff
-
-
-
-
-version '2.14.1'
+version '2.14.3'
```
`~ resources/[manuell_start]/oxmysql/logger/fivemanage.js`
```diff
-// https://fivemanage.com/?ref=overextended
+// https://refer.fivemanage.com/overextended
```
`~ resources/[manuell_start]/oxmysql/web/build/index.html`
```diff
-<!DOCTYPE html>
+<!doctype html>
-    <script type="module" crossorigin src="./assets/index-856dcf43.js"></script>
+    <script type="module" crossorigin src="./assets/index-ed335b58.js"></script>
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-10T08:00:59Z","categoryId":"1551161549018759170","webhooks":{"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","channelId":"1467556343492640830","webhookId":"1467556382038429901"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664","webhookId":"1557386337580220497"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","channelId":"1513950191936344245","webhookId":"1513950212480307490"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431","webhookId":"1552971088328392714"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617","webhookId":"1512475306554953789"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"1552971081491419187","webhookId":"1552971083731181709"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455","webhookId":"1551161582942158879"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","channelId":"1552989823604756600","webhookId":"1552989826213617715"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","channelId":"1551520126367572008","webhookId":"1551520132319412284"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763","webhookId":"1552971123233394708"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618","webhookId":"1551161592467423353"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374","webhookId":"1557386364578955274"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557386346782265425","webhookId":"1557386349395583076"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744","webhookId":"1552971074814218312"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","channelId":"1551161570439208960","webhookId":"1551161573194731652"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","channelId":"1552971110457286766","webhookId":"1552971115209564220"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068","webhookId":"1471556835994767400"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","channelId":"1557386329686413342","webhookId":"1557386332483887194"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"1417917687723724872","webhookId":"1552971931869777932"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252","webhookId":"1557386342755991582"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200","webhookId":"1552971079239077968"},"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","channelId":"1551624348660531240","webhookId":"1551624352477225113"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924552"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169","webhookId":"1552971096847028264"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","channelId":"1552971099317211136","webhookId":"1552971101741654046"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","channelId":"1552971103910236172","webhookId":"1552971107500433498"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","channelId":"1457180906816012401","webhookId":"1457180941750632469"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","channelId":"1551161550096699392","webhookId":"1551161552537653269"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913","webhookId":"1557386357381533816"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979","webhookId":"1474547103081566412"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370","webhookId":"1557386326951592027"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","channelId":"1551161575690211428","webhookId":"1551161578009796630"}}}
+{"updatedAt":"2026-10-10T11:21:38Z","webhooks":{"expose":{"channelId":"1551624348660531240","webhookId":"1551624352477225113","url":"https://discord.com/api/webhooks/1551624352477225113/***"},"bell":{"channelId":"1471556817061544068","webhookId":"1471556835994767400","url":"https://discord.com/api/webhooks/1471556835994767400/***"},"sozialstunden":{"channelId":"1552971081491419187","webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***"},"ausbluten":{"channelId":"1552971076718297200","webhookId":"1552971079239077968","url":"https://discord.com/api/webhooks/1552971079239077968/***"},"esx_resources":{"channelId":"1557386346782265425","webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"me":{"channelId":"1513950191936344245","webhookId":"1513950212480307490","url":"https://discord.com/api/webhooks/1513950212480307490/***"},"staff":{"channelId":"1552971120460828763","webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***"},"chopshop":{"channelId":"1552971071882399744","webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***"},"esx_paycheck":{"channelId":"1557386352226598913","webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***"},"txadmin":{"channelId":"1552989823604756600","webhookId":"1552989826213617715","url":"https://discord.com/api/webhooks/1552989826213617715/***"},"freecam_photo":{"channelId":"1551520126367572008","webhookId":"1551520132319412284","url":"https://discord.com/api/webhooks/1551520132319412284/***"},"esx_jobs":{"channelId":"1557386361172918374","webhookId":"1557386364578955274","url":"https://discord.com/api/webhooks/1557386364578955274/***"},"default":{"channelId":"1551161550096699392","webhookId":"1551161552537653269","url":"https://discord.com/api/webhooks/1551161552537653269/***"},"afk":{"channelId":"1512475286229356617","webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***"},"esx":{"channelId":"1420103430562910370","webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***"},"esx_useractions":{"channelId":"1557386339866120252","webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***"},"adminjail":{"channelId":"1551161575690211428","webhookId":"1551161578009796630","url":"https://discord.com/api/webhooks/1551161578009796630/***"},"clothing_strip":{"channelId":"1551161585614061618","webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"esx_chat":{"channelId":"1557386335512305664","webhookId":"1557386337580220497","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"lager":{"channelId":"1551161580324921455","webhookId":"1551161582942158879","url":"https://discord.com/api/webhooks/1551161582942158879/***"},"sperrzone":{"channelId":"1552971110457286766","webhookId":"1552971115209564220","url":"https://discord.com/api/webhooks/1552971115209564220/***"},"frak":{"channelId":"1552971094267527169","webhookId":"1552971096847028264","url":"https://discord.com/api/webhooks/1552971096847028264/***"},"basicneeds":{"channelId":"1417917687723724872","webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***"},"support":{"channelId":"1552971099317211136","webhookId":"1552971101741654046","url":"https://discord.com/api/webhooks/1552971101741654046/***"},"willkommen":{"channelId":"1551161595436990575","webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***"},"troll":{"channelId":"1552971103910236172","webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/1552971107500433498/***"},"esx_test":{"channelId":"1557386329686413342","webhookId":"1557386332483887194","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"marriage":{"channelId":"1467556343492640830","webhookId":"1467556382038429901","url":"https://discord.com/api/webhooks/1467556382038429901/***"},"einreise":{"channelId":"1552971085937381431","webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***"},"hotdog":{"channelId":"1474547082076622979","webhookId":"1474547103081566412","url":"https://discord.com/api/webhooks/1474547103081566412/***"},"join":{"channelId":"1448120760391565352","webhookId":"1552971091771924552","url":"https://discord.com/api/webhooks/1552971091771924552/***"},"versicherung":{"channelId":"1457180906816012401","webhookId":"1457180941750632469","url":"https://discord.com/api/webhooks/1457180941750632469/***"},"faction":{"channelId":"1551161570439208960","webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***"}},"categoryId":"1551161549018759170"}
```
`− filename.json`
```diff
- Gelöscht
```
`− myprofile`
```diff
- Gelöscht
```
`− resources/[manuell_start]/oxmysql/web/build/assets/index-856dcf43.js`
```diff
- Gelöscht
```

## 2026-10-10 12:23 Uhr
**+0** neu · **~0** geändert · **-6** gelöscht
`− resources/[selfcode]/lb-lieferlos/tests/client_mocks.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/lb-lieferlos/tests/client_test.py`
```diff
- Gelöscht
```
`− resources/[selfcode]/lb-lieferlos/tests/mocks.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/lb-lieferlos/tests/ox_test.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/lb-lieferlos/tests/run.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/lb-lieferlos/tests/run.py`
```diff
- Gelöscht
```

## 2026-10-10 11:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558388791130193972"}
+{"channelId":"1550507281396011150","messageId":"1558405954020581438"}
```

## 2026-10-10 10:23 Uhr
**+0** neu · **~3** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558358493306691652"}
+{"channelId":"1550507281396011150","messageId":"1558388791130193972"}
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:726b2e82f8613191a738a5158a2b2cd5c7dbeea1": [
+    "char3:f6a7d1d68111745581e11c74b2f45c0a9822fca5": [
-            "value": 3,
-            "reason": "Savings account interest payment (Period 27)",
-            "receiver_identifier": "char2:726b2e82f8613191a738a5158a2b2cd5c7dbeea1",
-            "date": "2026/07/05 - 09:20:38",
-            "sender_identifier": "bank",
+            "receiver_name": "Savings Account",
+            "date": "2026/10/09 - 10:01:07",
+            "value": 8555,
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-09T22:52:22Z","webhooks":{"einreise":{"channelId":"1552971085937381431","url":"https://discord.com/api/webhooks/1552971088328392714/***","webhookId":"1552971088328392714"},"bell":{"channelId":"1471556817061544068","url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400"},"esx_useractions":{"channelId":"1557386339866120252","url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582"},"faction":{"channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652"},"afk":{"channelId":"1512475286229356617","url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789"},"join":{"channelId":"1448120760391565352","url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552"},"freecam_photo":{"channelId":"1551520126367572008","url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284"},"sperrzone":{"channelId":"1552971110457286766","url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220"},"hotdog":{"channelId":"1474547082076622979","url":"https://discord.com/api/webhooks/1474547103081566412/***","webhookId":"1474547103081566412"},"expose":{"channelId":"1551624348660531240","url":"https://discord.com/api/webhooks/1551624352477225113/***","webhookId":"1551624352477225113"},"esx_resources":{"channelId":"1557386346782265425","url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076"},"troll":{"channelId":"1552971103910236172","url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498"},"me":{"channelId":"1513950191936344245","url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490"},"esx":{"channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027"},"esx_jobs":{"channelId":"1557386361172918374","url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274"},"clothing_strip":{"channelId":"1551161585614061618","url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353"},"ausbluten":{"channelId":"1552971076718297200","url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968"},"lager":{"channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879"},"basicneeds":{"channelId":"1417917687723724872","url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932"},"txadmin":{"channelId":"1552989823604756600","url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715"},"staff":{"channelId":"1552971120460828763","url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708"},"adminjail":{"channelId":"1551161575690211428","url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630"},"sozialstunden":{"channelId":"1552971081491419187","url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709"},"versicherung":{"channelId":"1457180906816012401","url":"https://discord.com/api/webhooks/1457180941750632469/***","webhookId":"1457180941750632469"},"support":{"channelId":"1552971099317211136","url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046"},"esx_test":{"channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194"},"chopshop":{"channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312"},"marriage":{"channelId":"1467556343492640830","url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901"},"default":{"channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269"},"esx_chat":{"channelId":"1557386335512305664","url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497"},"willkommen":{"channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005"},"frak":{"channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264"},"esx_paycheck":{"channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816"}}}
+{"updatedAt":"2026-10-10T08:00:59Z","categoryId":"1551161549018759170","webhooks":{"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","channelId":"1467556343492640830","webhookId":"1467556382038429901"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664","webhookId":"1557386337580220497"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","channelId":"1513950191936344245","webhookId":"1513950212480307490"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431","webhookId":"1552971088328392714"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617","webhookId":"1512475306554953789"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"1552971081491419187","webhookId":"1552971083731181709"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455","webhookId":"1551161582942158879"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","channelId":"1552989823604756600","webhookId":"1552989826213617715"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","channelId":"1551520126367572008","webhookId":"1551520132319412284"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763","webhookId":"1552971123233394708"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618","webhookId":"1551161592467423353"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374","webhookId":"1557386364578955274"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557386346782265425","webhookId":"1557386349395583076"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744","webhookId":"1552971074814218312"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","channelId":"1551161570439208960","webhookId":"1551161573194731652"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","channelId":"1552971110457286766","webhookId":"1552971115209564220"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068","webhookId":"1471556835994767400"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","channelId":"1557386329686413342","webhookId":"1557386332483887194"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"1417917687723724872","webhookId":"1552971931869777932"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252","webhookId":"1557386342755991582"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200","webhookId":"1552971079239077968"},"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","channelId":"1551624348660531240","webhookId":"1551624352477225113"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924552"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169","webhookId":"1552971096847028264"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","channelId":"1552971099317211136","webhookId":"1552971101741654046"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","channelId":"1552971103910236172","webhookId":"1552971107500433498"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","channelId":"1457180906816012401","webhookId":"1457180941750632469"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","channelId":"1551161550096699392","webhookId":"1551161552537653269"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913","webhookId":"1557386357381533816"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979","webhookId":"1474547103081566412"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370","webhookId":"1557386326951592027"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","channelId":"1551161575690211428","webhookId":"1551161578009796630"}}}
```

## 2026-10-10 08:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558310657898844204"}
+{"channelId":"1550507281396011150","messageId":"1558358493306691652"}
```

## 2026-10-10 05:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558285981118111807"}
+{"channelId":"1550507281396011150","messageId":"1558310657898844204"}
```

## 2026-10-10 03:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558250735559385142"}
+{"channelId":"1550507281396011150","messageId":"1558285981118111807"}
```

## 2026-10-10 01:23 Uhr
**+0** neu · **~2** geändert · **-1** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558237349224128575"}
+{"channelId":"1550507281396011150","messageId":"1558250735559385142"}
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-09T14:55:28Z","webhooks":{"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194","channelId":"1557386329686413342"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046","channelId":"1552971099317211136"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652","channelId":"1551161570439208960"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879","channelId":"1551161580324921455"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400","channelId":"1471556817061544068"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708","channelId":"1552971120460828763"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284","channelId":"1551520126367572008"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490","channelId":"1513950191936344245"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220","channelId":"1552971110457286766"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901","channelId":"1467556343492640830"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","webhookId":"1551624352477225113","channelId":"1551624348660531240"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789","channelId":"1512475286229356617"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497","channelId":"1557386335512305664"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","webhookId":"1457180941750632469","channelId":"1457180906816012401"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076","channelId":"1557386346782265425"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","webhookId":"1552971088328392714","channelId":"1552971085937381431"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816","channelId":"1557386352226598913"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582","channelId":"1557386339866120252"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264","channelId":"1552971094267527169"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005","channelId":"1551161595436990575"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353","channelId":"1551161585614061618"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709","channelId":"1552971081491419187"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552","channelId":"1448120760391565352"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","webhookId":"1474547103081566412","channelId":"1474547082076622979"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715","channelId":"1552989823604756600"}},"categoryId":"1551161549018759170"}
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-09T22:52:22Z","webhooks":{"einreise":{"channelId":"1552971085937381431","url":"https://discord.com/api/webhooks/1552971088328392714/***","webhookId":"1552971088328392714"},"bell":{"channelId":"1471556817061544068","url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400"},"esx_useractions":{"channelId":"1557386339866120252","url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582"},"faction":{"channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652"},"afk":{"channelId":"1512475286229356617","url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789"},"join":{"channelId":"1448120760391565352","url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552"},"freecam_photo":{"channelId":"1551520126367572008","url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284"},"sperrzone":{"channelId":"1552971110457286766","url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220"},"hotdog":{"channelId":"1474547082076622979","url":"https://discord.com/api/webhooks/1474547103081566412/***","webhookId":"1474547103081566412"},"expose":{"channelId":"1551624348660531240","url":"https://discord.com/api/webhooks/1551624352477225113/***","webhookId":"1551624352477225113"},"esx_resources":{"channelId":"1557386346782265425","url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076"},"troll":{"channelId":"1552971103910236172","url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498"},"me":{"channelId":"1513950191936344245","url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490"},"esx":{"channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027"},"esx_jobs":{"channelId":"1557386361172918374","url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274"},"clothing_strip":{"channelId":"1551161585614061618","url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353"},"ausbluten":{"channelId":"1552971076718297200","url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968"},"lager":{"channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879"},"basicneeds":{"channelId":"1417917687723724872","url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932"},"txadmin":{"channelId":"1552989823604756600","url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715"},"staff":{"channelId":"1552971120460828763","url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708"},"adminjail":{"channelId":"1551161575690211428","url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630"},"sozialstunden":{"channelId":"1552971081491419187","url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709"},"versicherung":{"channelId":"1457180906816012401","url":"https://discord.com/api/webhooks/1457180941750632469/***","webhookId":"1457180941750632469"},"support":{"channelId":"1552971099317211136","url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046"},"esx_test":{"channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194"},"chopshop":{"channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312"},"marriage":{"channelId":"1467556343492640830","url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901"},"default":{"channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269"},"esx_chat":{"channelId":"1557386335512305664","url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497"},"willkommen":{"channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005"},"frak":{"channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264"},"esx_paycheck":{"channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816"}}}
```
`− resources/[manuell_start]/ox_doorlock/.claude/settings.local.json`
```diff
- Gelöscht
```

## 2026-10-10 00:24 Uhr
**+2** neu · **~9** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_doors/audio/data/oxdoorlock_sounds.dat54.rel`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/audio/dlc_oxdoorlock/oxdoorlock.awc`
```diff
+ Neue Datei
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558220457289977856"}
+{"channelId":"1550507281396011150","messageId":"1558237349224128575"}
```
`~ resources/[selfcode]/rmc_doors/client/main.lua`
```diff
-local function distSqTo(coords)
-    local p = GetEntityCoords(PlayerPedId())
-    local dx, dy, dz = p.x - coords.x, p.y - coords.y, p.z - coords.z
+local function distSqBetween(a, b)
+    local dx, dy, dz = a.x - b.x, a.y - b.y, a.z - b.z
+local function distSqTo(coords)
+    return distSqBetween(GetEntityCoords(PlayerPedId()), coords)
+end
+
+local function doorDistSqFrom(origin, door)
```
`~ resources/[selfcode]/rmc_doors/config.lua`
```diff
+--- ox_target hängt Aufschließen/Abschließen an die Tür, sobald die Resource läuft.
+--- INPUT_PICKUP (E) ist dann aus. INPUT_DETONATE (G) bleibt der Dietrich.
-Config.DefaultRate = 1.0
-
-Config.Sounds = {
-    lock = { name = 'DOOR_BUZZ', set = 'MP_PLAYER_APARTMENT' },
-    unlock = { name = 'DOOR_OPEN', set = 'GTAO_APT_DOOR_DOWNSTAIRS_GLASS_SOUNDS' },
-}
+--- Door-System-Tempo wie ox_doorlock. Über 10 bleibt die Tür stehen.
+Config.DefaultRate = 10.0
```
`~ resources/[selfcode]/rmc_doors/fxmanifest.lua`
```diff
+    'audio/data/oxdoorlock_sounds.dat54.rel',
+    'audio/dlc_oxdoorlock/oxdoorlock.awc',
+data_file 'AUDIO_WAVEPACK' 'audio/dlc_oxdoorlock'
+data_file 'AUDIO_SOUNDDATA' 'audio/data/oxdoorlock_sounds.dat'
+
```
`~ resources/[selfcode]/rmc_doors/html/app.js`
```diff
-    document.getElementById('f-rate').value = door && door.doorRate != null ? door.doorRate : 1;
+    document.getElementById('f-rate').value = door && door.doorRate != null ? door.doorRate : 10;
```
`~ resources/[selfcode]/rmc_doors/html/index.html`
```diff
-                                <input id="f-rate" type="number" min="0.1" max="20" step="0.1" value="1" />
+                                <input id="f-rate" type="number" min="0.2" max="10" step="0.1" value="10" />
```
`~ resources/[selfcode]/rmc_doors/locales/de.lua`
```diff
+    target_unlock = 'Aufschließen',
+    target_lock = 'Abschließen',
+    target_lockpick = 'Dietrich',
```
`~ resources/[selfcode]/rmc_doors/locales/en.lua`
```diff
+    target_unlock = 'Unlock',
+    target_lock = 'Lock',
+    target_lockpick = 'Lockpick',
```
`~ resources/[selfcode]/rmc_doors/server/main.lua`
```diff
-        doorRate = math.min(20.0, math.max(0.1, doorRate)),
+        doorRate = math.min(10.0, math.max(0.2, doorRate)),
-    local c = door.coords
-    local dx, dy, dz = coords.x - c.x, coords.y - c.y, coords.z - c.z
+
-    return (dx * dx + dy * dy + dz * dz) <= (limit * limit)
+    local limitSq = limit * limit
+
+    local function near(point)
+        if type(point) ~= 'table' then return false end
```

## 2026-10-09 23:24 Uhr
**+13** neu · **~1** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_doors/client/creator.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/client/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/config.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/doors.sql`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/html/app.js`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/html/index.html`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/html/style.css`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/locales/de.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/locales/en.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/server/main.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/shared/locale.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_doors/sql/rmc_doors.sql`
```diff
+ Neue Datei
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558191003817742488"}
+{"channelId":"1550507281396011150","messageId":"1558220457289977856"}
```

## 2026-10-09 22:24 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "value": 500,
+            "date": "2026/10/09 - 22:00:20",
+            "type": "withdraw",
+            "receiver_identifier": "cd_garage",
+            "sender_identifier": "char1:5d9a7aa1b89a5c67108c44299d6b73c6e39c062c",
+            "reason": "Fahrzeugrückgabegebühr",
+            "sender_name": "Misaki Lee",
+            "receiver_name": "cd_garage"
+        },
```

## 2026-10-09 21:24 Uhr
**+10** neu · **~16** geändert · **-2** gelöscht
`+ resources/[selfcode]/lb-lieferlos/README.md`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-lieferlos/install/esx_items.sql`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-lieferlos/install/ox_inventory_items.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-lieferlos/tests/client_mocks.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-lieferlos/tests/client_test.py`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-lieferlos/tests/mocks.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-lieferlos/tests/ox_test.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-lieferlos/tests/run.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-lieferlos/tests/run.py`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/lb-lieferlos/ui/dist/assets/index-DkJW2aaQ.js`
```diff
+ Neue Datei
```
`~ resources/[devcore]/devcore_needs/configs/items.lua`
```diff
+            ['sarke'] = {label = 'Kirschblüten Sake'},
```
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
+    "lastBackup": 1791571216,
-            "backupDate": "20_24_04_10_2026",
-            "backupTimestamp": 1791138260,
-            "id": 11,
-            "backupFile": "banlist_20_24_04_10_2026.json"
-        },
-        {
-            "backupDate": "20_26_04_10_2026",
-            "backupTimestamp": 1791138385,
-            "id": 11,
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558174842577223761"}
+{"channelId":"1550507281396011150","messageId":"1558191003817742488"}
```
`~ resources/[selfcode]/lb-lieferlos/.luacheckrc`
```diff
-globals = { 'Config', 'Postal', 'Bridge' }
+globals = { 'Config', 'Postal', 'Bridge', 'Lieferlos' }
-    'CreateThread', 'Wait', 'SetTimeout', 'Citizen', 'source',
+    'CreateThread', 'Wait', 'GetConvar', 'RegisterCommand', 'GetGameTimer', 'SetTimeout', 'Citizen', 'source',
-exclude_files = { 'ui/**' }
-exclude_files = { 'ui/**', 'install/**' }
+exclude_files = { 'ui/**', 'install/**', 'tests/**' }
```
`~ resources/[selfcode]/lb-lieferlos/client/main.lua`
```diff
+-- Item images: the app tries these base URLs in order and falls back to the built-in icon.
+-- https://cfx-nui-<resource>/ is the current NUI scheme, nui://<resource>/ the older one (ox_inventory's default convar).
+local function imageConfig()
+    local path = Config.ItemImagePath
+    if not path then return nil end
+    local bases = {}
+    local function add(b)
+        if type(b) ~= 'string' or b == '' then return end
+        b = b:gsub('/+$', '')
+        for _, x in ipairs(bases) do if x == b then return end end
```
`~ resources/[selfcode]/lb-lieferlos/config.lua`
```diff
+-- WICHTIG: Alle Artikel aus Config.Shops müssen als Items im Inventar existieren (Standard: die Items
+-- aus dem Consume-Script, die es schon gibt). Für eigene neue Items: install/ox_inventory_items.lua bzw. install/esx_items.sql.
+-- Beim Start prüft die Ressource das und schreibt fehlende Items in die Server-Konsole.
+
+-- Lieferlos-Artikel auf bereits vorhandene Server-Items umleiten: [Lieferlos-Name] = 'Server-Item'
+-- Beispiel: Config.ItemMapping = { tburger = 'tower_burger' }
+Config.ItemMapping = {
+    -- 'napollitano' steht in devcore_needs, existiert aber nicht in ox_inventory -> dort heißt es 'napollitanopizza'
+    napollitano = 'napollitanopizza',
+}
```
`~ resources/[selfcode]/lb-lieferlos/fxmanifest.lua`
```diff
-version '1.0.1'
+version '1.0.4'
```
`~ resources/[selfcode]/lb-lieferlos/server/bridge.lua`
```diff
-local inv = Config.Inventory
-if inv == 'auto' then
-    inv = GetResourceState('ox_inventory'):find('start') and 'ox_inventory' or 'esx'
+-- ---------------------------------------------------------------- inventory detection
+-- Resolved lazily (not at file load), so the result is correct even if ox_inventory starts after this resource.
+local function detectInventory()
+    local want = Config.Inventory
+    if want == 'ox' then want = 'ox_inventory' end
+    if want == 'ox_inventory' or want == 'esx' then return want end
+    local state = GetResourceState('ox_inventory')
```
`~ resources/[selfcode]/lb-lieferlos/server/main.lua`
```diff
+local driverWentOnline, driverWentOffline -- defined further below
+            if not Bridge.IsAvailable(it.name) then return nil, ('%s ist gerade nicht verfügbar.'):format(it.label) end
+    local droppedDriver = d and d.online
+    if droppedDriver then driverWentOffline() end
+-- ---------------------------------------------------------------- "Fahrer im Dienst" broadcast
+-- One tiny broadcast (LB Phone NotifyEveryone / esx:showNotification to -1), never a per-player loop with data.
+local lastDriverNotify = {}   -- [identifier] = os.time() of the last broadcast caused by this driver
+local lastBroadcast = 0
+local noDriverAnnounced = true
+
```
`~ resources/[selfcode]/lb-lieferlos/sql/lieferlos.sql`
```diff
-INSERT IGNORE INTO `items` (`name`, `label`, `weight`, `rare`, `can_remove`) VALUES
-    ('burger', 'Burger', 1, 0, 1),
-    ('burger_xl', 'Heart Stopper', 1, 0, 1),
-    ('fries', 'Pommes', 1, 0, 1),
-    ('cola', 'eCola', 1, 0, 1),
-    ('sprunk', 'Sprunk', 1, 0, 1),
-    ('milkshake', 'Milchshake', 1, 0, 1),
-    ('chicken_bucket', 'Cluckin'' Bucket', 2, 0, 1),
-    ('chicken_wrap', 'Fowl Wrap', 1, 0, 1),
-    ('pizza', 'Pizza Margherita', 2, 0, 1),
```
`~ resources/[selfcode]/lb-lieferlos/ui/dist/index.html`
```diff
-      <script type="module" crossorigin src="/ui/dist/assets/index-gkEW31eK.js"></script>
-      <link rel="stylesheet" crossorigin href="/ui/dist/assets/index-DwGDBUpZ.css">
+      <script type="module" crossorigin src="/ui/dist/assets/index-DkJW2aaQ.js"></script>
+      <link rel="stylesheet" crossorigin href="/ui/dist/assets/index-BJz2cef8.css">
```
`~ resources/[selfcode]/lb-lieferlos/ui/src/App.tsx`
```diff
+    Beer,
+    Cake,
+    Candy,
+    Fish,
+    Martini,
+    Nut,
+    Soup,
+    Wine,
+    Apple,
+    Banana,
```
`~ resources/[selfcode]/lb-lieferlos/ui/src/app.css`
```diff
-.item-icon { border-radius: 0.7rem; background: var(--background-tertiary); color: var(--accent); display: flex; align-items: center; justify-content: center; flex: none; }
+.item-icon { border-radius: 0.7rem; background: var(--background-tertiary); color: var(--accent); display: flex; align-items: center; justify-content: center; flex: none; overflow: hidden; }
+.item-icon.has-img img { width: 86%; height: 86%; object-fit: contain; pointer-events: none; }
```
`~ resources/[selfcode]/lb-lieferlos/ui/src/mock.ts`
```diff
-            { name: 'burger', label: 'Bleeder Burger', description: 'Doppeltes Patty, Cheddar, Bleeder-Sauce', price: 9, icon: 'burger', popular: true },
-            { name: 'burger_xl', label: 'Heart Stopper', description: 'Vier Patties, Bacon, viel Käse', price: 14, icon: 'burger' },
-            { name: 'fries', label: 'Money Shot Fries', description: 'Knusprige Pommes', price: 4, icon: 'fries' },
-            { name: 'cola', label: 'eCola', description: '0,5 l', price: 3, icon: 'drink' },
-            { name: 'milkshake', label: 'Meat Free Shake', description: 'Vanille oder Schoko', price: 5, icon: 'shake' }
+            { name: 'burger', label: 'Burger', description: 'Der Klassiker mit Käse und Soße', price: 8, icon: 'burger', popular: true },
+            { name: 'tburger', label: 'Tower Burger', description: 'Doppelt hoch, doppelt satt', price: 14, icon: 'burger' },
+            { name: 'pulledpork_burger', label: 'Pulled Pork Burger', description: 'Zartes Pulled Pork, BBQ-Soße, Coleslaw', price: 12, icon: 'burger' },
+            { name: 'chips', label: 'Chips', description: 'Die Tüte für nebenbei', price: 3, icon: 'chips' }
-        id: 'cluckinbell', label: "Cluckin' Bell", category: 'Chicken', color: '#F59E0B', short: 'CB',
```
`~ resources/[selfcode]/lb-lieferlos/ui/src/types.ts`
```diff
+    image?: string // own image (file name or full URL)
+    images?: { bases: string[]; ext: string } // item image base URLs (tried in order), undefined = icons only
```
`~ resources/[selfcode]/rmc_core/data/sits.json`
```diff
-[]
+[{"id":"sit_1791572244_8861","label":"Sit Chair 4","anim":"base","dict":"timetable@ron@ig_3_couch","y":-420.7482,"x":1225.8873,"h":255.6565,"z":68.0417},{"id":"sit_1791572300_6917","label":"Sit Chair 2","anim":"ig_5_p3_base","dict":"timetable@ron@ig_5_p3","y":-419.3795,"x":1226.4694,"h":271.1957,"z":68.0817}]
```
`− resources/[selfcode]/lb-lieferlos/ui/dist/assets/index-Blyp_gGa.js`
```diff
- Gelöscht
```
`− resources/[selfcode]/lb-lieferlos/ui/dist/assets/index-gkEW31eK.js`
```diff
- Gelöscht
```

## 2026-10-09 20:24 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558150186482671638"}
+{"channelId":"1550507281396011150","messageId":"1558174842577223761"}
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "value": 10000,
+            "date": "2026/10/09 - 19:27:18",
+            "receiver_identifier": "bank",
+            "reason": "Auszahlung vom Bankkonto",
+            "sender_identifier": "char1:726b2e82f8613191a738a5158a2b2cd5c7dbeea1",
+            "type": "withdraw",
+            "sender_name": "Fabi Huber",
+            "receiver_name": "Geldbörse"
+        },
```

## 2026-10-09 19:24 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[okok]/okokBanking/transactions.json`
```diff
+        {
+            "value": 100,
+            "receiver_identifier": "bank",
+            "sender_identifier": "char1:726b2e82f8613191a738a5158a2b2cd5c7dbeea1",
+            "date": "2026/10/09 - 19:09:46",
+            "sender_name": "Fabi Huber",
+            "receiver_name": "Bank (Kartenerneuerung)"
+        },
```

## 2026-10-09 17:23 Uhr
**+0** neu · **~4** geändert · **-3** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558108581599911987"}
+{"channelId":"1550507281396011150","messageId":"1558130711574224910"}
```
`~ resources/[oresmon]/rm_hackerv/shared/cfg.lua`
```diff
-    ['phoneJobs'] = {'ambulance'}, -- Jobs for allow use hacker phone (un-comment if you want works with jobs)
+    ['phoneJobs'] = {'sakura'}, -- Jobs for allow use hacker phone (un-comment if you want works with jobs)
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
-Config.PierRides = {
-    Enabled = true,
-    Center = vector3(-1656.0, -1128.0, 18.0),
-    StreamDistance = 180.0,
-    NearDistance = 120.0,
-
-    Ferris = {
-        Position = vector3(-1663.97, -1126.7, 30.7),
-        BoardingPoint = vector3(-1661.95, -1127.011, 12.6973),
-        BoardingRadius = 2.0,
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","updatedAt":"2026-10-09T14:19:57Z","webhooks":{"basicneeds":{"channelId":"1417917687723724872","webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***"},"clothing_strip":{"channelId":"1551161585614061618","webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"esx_chat":{"channelId":"1557386335512305664","webhookId":"1557386337580220497","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"bell":{"channelId":"1471556817061544068","webhookId":"1471556835994767400","url":"https://discord.com/api/webhooks/1471556835994767400/***"},"ausbluten":{"channelId":"1552971076718297200","webhookId":"1552971079239077968","url":"https://discord.com/api/webhooks/1552971079239077968/***"},"afk":{"channelId":"1512475286229356617","webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***"},"esx_test":{"channelId":"1557386329686413342","webhookId":"1557386332483887194","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"marriage":{"channelId":"1467556343492640830","webhookId":"1467556382038429901","url":"https://discord.com/api/webhooks/1467556382038429901/***"},"troll":{"channelId":"1552971103910236172","webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/1552971107500433498/***"},"freecam_photo":{"channelId":"1551520126367572008","webhookId":"1551520132319412284","url":"https://discord.com/api/webhooks/1551520132319412284/***"},"join":{"channelId":"1448120760391565352","webhookId":"1552971091771924552","url":"https://discord.com/api/webhooks/1552971091771924552/***"},"chopshop":{"channelId":"1552971071882399744","webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***"},"default":{"channelId":"1551161550096699392","webhookId":"1551161552537653269","url":"https://discord.com/api/webhooks/1551161552537653269/***"},"staff":{"channelId":"1552971120460828763","webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***"},"sozialstunden":{"channelId":"1552971081491419187","webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***"},"esx_paycheck":{"channelId":"1557386352226598913","webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***"},"sperrzone":{"channelId":"1552971110457286766","webhookId":"1552971115209564220","url":"https://discord.com/api/webhooks/1552971115209564220/***"},"expose":{"channelId":"1551624348660531240","webhookId":"1551624352477225113","url":"https://discord.com/api/webhooks/1551624352477225113/***"},"frak":{"channelId":"1552971094267527169","webhookId":"1552971096847028264","url":"https://discord.com/api/webhooks/1552971096847028264/***"},"support":{"channelId":"1552971099317211136","webhookId":"1552971101741654046","url":"https://discord.com/api/webhooks/1552971101741654046/***"},"esx_useractions":{"channelId":"1557386339866120252","webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***"},"esx":{"channelId":"1420103430562910370","webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***"},"esx_jobs":{"channelId":"1557386361172918374","webhookId":"1557386364578955274","url":"https://discord.com/api/webhooks/1557386364578955274/***"},"versicherung":{"channelId":"1457180906816012401","webhookId":"1457180941750632469","url":"https://discord.com/api/webhooks/1457180941750632469/***"},"faction":{"channelId":"1551161570439208960","webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"willkommen":{"channelId":"1551161595436990575","webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***"},"esx_resources":{"channelId":"1557386346782265425","webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"einreise":{"channelId":"1552971085937381431","webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***"},"lager":{"channelId":"1551161580324921455","webhookId":"1551161582942158879","url":"https://discord.com/api/webhooks/1551161582942158879/***"},"adminjail":{"channelId":"1551161575690211428","webhookId":"1551161578009796630","url":"https://discord.com/api/webhooks/1551161578009796630/***"},"me":{"channelId":"1513950191936344245","webhookId":"1513950212480307490","url":"https://discord.com/api/webhooks/1513950212480307490/***"},"txadmin":{"channelId":"1552989823604756600","webhookId":"1552989826213617715","url":"https://discord.com/api/webhooks/1552989826213617715/***"},"hotdog":{"channelId":"1474547082076622979","webhookId":"1474547103081566412","url":"https://discord.com/api/webhooks/1474547103081566412/***"}}}
+{"updatedAt":"2026-10-09T14:55:28Z","webhooks":{"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194","channelId":"1557386329686413342"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046","channelId":"1552971099317211136"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652","channelId":"1551161570439208960"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879","channelId":"1551161580324921455"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400","channelId":"1471556817061544068"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708","channelId":"1552971120460828763"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284","channelId":"1551520126367572008"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490","channelId":"1513950191936344245"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220","channelId":"1552971110457286766"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901","channelId":"1467556343492640830"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","webhookId":"1551624352477225113","channelId":"1551624348660531240"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789","channelId":"1512475286229356617"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497","channelId":"1557386335512305664"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","webhookId":"1457180941750632469","channelId":"1457180906816012401"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076","channelId":"1557386346782265425"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","webhookId":"1552971088328392714","channelId":"1552971085937381431"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816","channelId":"1557386352226598913"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582","channelId":"1557386339866120252"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264","channelId":"1552971094267527169"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005","channelId":"1551161595436990575"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353","channelId":"1551161585614061618"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709","channelId":"1552971081491419187"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552","channelId":"1448120760391565352"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","webhookId":"1474547103081566412","channelId":"1474547082076622979"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715","channelId":"1552989823604756600"}},"categoryId":"1551161549018759170"}
```
`− resources/[selfcode]/rmc_core/client/pier_coaster_track.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_core/client/pier_rides.lua`
```diff
- Gelöscht
```
`− resources/[selfcode]/rmc_core/server/pier_rides.lua`
```diff
- Gelöscht
```

## 2026-10-09 16:23 Uhr
**+3** neu · **~3** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_core/client/pier_coaster_track.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/client/pier_rides.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/server/pier_rides.lua`
```diff
+ Neue Datei
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558103708397736039"}
+{"channelId":"1550507281396011150","messageId":"1558108581599911987"}
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+-- ====== PIER / RIESENRAD + ACHTERBAHN ======
+-- Del Perro: lokale Props, nur in der Nähe aktiv. Server merkt sich nur Sitze und die Abfahrt.
+Config.PierRides = {
+    Enabled = true,
+    Center = vector3(-1656.0, -1128.0, 18.0),
+    StreamDistance = 180.0,
+    NearDistance = 120.0,
+
+    Ferris = {
+        Position = vector3(-1663.97, -1126.7, 30.7),
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816","channelId":"1557386352226598913"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497","channelId":"1557386335512305664"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652","channelId":"1551161570439208960"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901","channelId":"1467556343492640830"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","webhookId":"1552971088328392714","channelId":"1552971085937381431"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","webhookId":"1474547103081566412","channelId":"1474547082076622979"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582","channelId":"1557386339866120252"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708","channelId":"1552971120460828763"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789","channelId":"1512475286229356617"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","webhookId":"1457180941750632469","channelId":"1457180906816012401"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194","channelId":"1557386329686413342"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005","channelId":"1551161595436990575"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715","channelId":"1552989823604756600"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264","channelId":"1552971094267527169"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046","channelId":"1552971099317211136"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220","channelId":"1552971110457286766"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552","channelId":"1448120760391565352"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284","channelId":"1551520126367572008"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879","channelId":"1551161580324921455"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709","channelId":"1552971081491419187"},"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","webhookId":"1551624352477225113","channelId":"1551624348660531240"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490","channelId":"1513950191936344245"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400","channelId":"1471556817061544068"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353","channelId":"1551161585614061618"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076","channelId":"1557386346782265425"}},"updatedAt":"2026-10-09T08:01:21Z"}
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-09T14:19:57Z","webhooks":{"basicneeds":{"channelId":"1417917687723724872","webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***"},"clothing_strip":{"channelId":"1551161585614061618","webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"esx_chat":{"channelId":"1557386335512305664","webhookId":"1557386337580220497","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"bell":{"channelId":"1471556817061544068","webhookId":"1471556835994767400","url":"https://discord.com/api/webhooks/1471556835994767400/***"},"ausbluten":{"channelId":"1552971076718297200","webhookId":"1552971079239077968","url":"https://discord.com/api/webhooks/1552971079239077968/***"},"afk":{"channelId":"1512475286229356617","webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***"},"esx_test":{"channelId":"1557386329686413342","webhookId":"1557386332483887194","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"marriage":{"channelId":"1467556343492640830","webhookId":"1467556382038429901","url":"https://discord.com/api/webhooks/1467556382038429901/***"},"troll":{"channelId":"1552971103910236172","webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/1552971107500433498/***"},"freecam_photo":{"channelId":"1551520126367572008","webhookId":"1551520132319412284","url":"https://discord.com/api/webhooks/1551520132319412284/***"},"join":{"channelId":"1448120760391565352","webhookId":"1552971091771924552","url":"https://discord.com/api/webhooks/1552971091771924552/***"},"chopshop":{"channelId":"1552971071882399744","webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***"},"default":{"channelId":"1551161550096699392","webhookId":"1551161552537653269","url":"https://discord.com/api/webhooks/1551161552537653269/***"},"staff":{"channelId":"1552971120460828763","webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***"},"sozialstunden":{"channelId":"1552971081491419187","webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***"},"esx_paycheck":{"channelId":"1557386352226598913","webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***"},"sperrzone":{"channelId":"1552971110457286766","webhookId":"1552971115209564220","url":"https://discord.com/api/webhooks/1552971115209564220/***"},"expose":{"channelId":"1551624348660531240","webhookId":"1551624352477225113","url":"https://discord.com/api/webhooks/1551624352477225113/***"},"frak":{"channelId":"1552971094267527169","webhookId":"1552971096847028264","url":"https://discord.com/api/webhooks/1552971096847028264/***"},"support":{"channelId":"1552971099317211136","webhookId":"1552971101741654046","url":"https://discord.com/api/webhooks/1552971101741654046/***"},"esx_useractions":{"channelId":"1557386339866120252","webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***"},"esx":{"channelId":"1420103430562910370","webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***"},"esx_jobs":{"channelId":"1557386361172918374","webhookId":"1557386364578955274","url":"https://discord.com/api/webhooks/1557386364578955274/***"},"versicherung":{"channelId":"1457180906816012401","webhookId":"1457180941750632469","url":"https://discord.com/api/webhooks/1457180941750632469/***"},"faction":{"channelId":"1551161570439208960","webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"willkommen":{"channelId":"1551161595436990575","webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***"},"esx_resources":{"channelId":"1557386346782265425","webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"einreise":{"channelId":"1552971085937381431","webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***"},"lager":{"channelId":"1551161580324921455","webhookId":"1551161582942158879","url":"https://discord.com/api/webhooks/1551161582942158879/***"},"adminjail":{"channelId":"1551161575690211428","webhookId":"1551161578009796630","url":"https://discord.com/api/webhooks/1551161578009796630/***"},"me":{"channelId":"1513950191936344245","webhookId":"1513950212480307490","url":"https://discord.com/api/webhooks/1513950212480307490/***"},"txadmin":{"channelId":"1552989823604756600","webhookId":"1552989826213617715","url":"https://discord.com/api/webhooks/1552989826213617715/***"},"hotdog":{"channelId":"1474547082076622979","webhookId":"1474547103081566412","url":"https://discord.com/api/webhooks/1474547103081566412/***"}}}
```

## 2026-10-09 15:24 Uhr
**+226** neu · **~1** geändert · **-230** gelöscht
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
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/.fxap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/fxmanifest.lua`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/_manifest.ymf`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/bushes_txt.ytd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_12.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_bchrks_5.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_land01b.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_pier_endmain01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_pier_stilts.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_11_slod1b_children.ydd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_occl_00.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_occl_01.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_occl_02.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/ch1_occl_03.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/changer_ch1_malpier29.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/changer_ch1_malpier29.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_11.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_11_critical_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_11_long_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_11_strm_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_12_critical_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_12_long_0.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hei_ch1_12_strm_2.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/hi@ch1_11_0.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/maiq_yakuza.ymf`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_back_exterior.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_back_exterior_dec.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_block.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes04.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes05.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_bushes06.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_dirt_a.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_dirt_b.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_dirt_c.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_dirt_d.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_ext_door_l.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_ext_door_r.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_exteriorlight.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_faketowerinterior.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_main.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_main02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_main03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal04.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal05.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal06.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal07.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal08.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal09.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal10.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal11.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_metal12.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_place.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_place.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_place.ytd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_place.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_sakuraflower.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/n_yak_sakuratree.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza.ybn`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza.ymf`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza.ytd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza.ytyp`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza_milo_.ymap`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_yakuza_props.ytd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_bigframe.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_bombscreen.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_bosschair.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_floorlamp_a.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_glassdoor.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_gongo.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_katana01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_katana02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_katana03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_katana04.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_metalframe.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_mirror01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_mirror02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_mirror03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_mirror04.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r01details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r01details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r02details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r02details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r03details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r03details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r04details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r04details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r05details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r05details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r05details03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r06details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r06details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r06details03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r07details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r07details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r07details03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r08details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r08details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details02.ycd`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r09details04.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r10details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r10details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r10details03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r11details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r11details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r11details03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r12details01.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r12details02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_r12details03.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_redlight.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_shell.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_shell02.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_sidedoor.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_sidedoor_ext_l.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_sidedoor_ext_r.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_smallframe.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/v_ykz_wingchun.ydr`
```diff
+ Neue Datei
```
`+ resources/[stream]/[mlo]/[tj]/hydrus_yakuza_map/stream/yakuza_doors.ytyp`
```diff
+ Neue Datei
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558066488404086906"}
+{"channelId":"1550507281396011150","messageId":"1558103708397736039"}
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/.fxap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/as_vw_villa_entityset.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/_manifest.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_06b_0.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_06b_4.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_06b_plot4.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_06b_plot4_dtls_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_06b_plot4_dtls_03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_06b_plot4_woodhi_lod.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_06b_props_props04_dslod_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_06b_slod1_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_lod_0106_slod2_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/ch1_occl_03.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/hei_ch1_06b_critical_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/hei_ch1_06b_long_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/hei_ch1_06b_strm_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/hi@ch1_06b_0.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/hi@ch1_06b_4.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/vw_distlodlights_medium008.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/base/vw_lodlights_medium008.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/textures/as_vw_villa_txd.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ybn/as_vw_villa_build_col.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ybn/as_vw_villa_garage_shell_col.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ybn/as_vw_villa_shell_col.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ybn/as_vw_villa_terrain_col.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_bedroom.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_bedroom_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_emissive.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_b_lod.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_b_slod2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_b_slod3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_barriers.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_c.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_dtls_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_dtls_02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_dtls_03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_ground_tiles.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_gutters.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_lod.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_pool.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_poolwtr.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_slod2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_slod3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_build_window.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_chrismas_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_decals.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_desk.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_diningroom.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_door_entry.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_door_garage.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_door_interrior_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_door_interrior_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_door_l.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_door_r.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_frame.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_fridge.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_bench_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_bench_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_build.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_build_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_build_lod.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_build_slod2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_build_slod3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_deta.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_shell.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_garage_window.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_halloween_prop_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_halloween_prop_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_kitchen.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_living.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_mirror.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_mirror_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_prop_map_01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_prop_map_02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_prop_xmas_tree_int.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_rug_round.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_shell.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_shell_bedroom_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stage bathroom_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stage_bathroom.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stage_bedroom.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stage_bedroom_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stage_bedroom_a_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stage_bedroom_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stage_bedroom_b_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stage_bedroom_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stair_corridor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stair_corridor_a.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_stair_corridor_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_switch.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_toilet.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_toilet_light.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ydr/as_vw_villa_window.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ymap/as_vw_villa_ext_placement.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ymap/as_vw_villa_garage_milo_.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ymap/as_vw_villa_lod.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ymap/as_vw_villa_milo_.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ymap/as_vw_villa_slod.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ytyp/as_vw_villa.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ytyp/as_vw_villa_ext.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tj]/as_vw_villa/stream/ytyp/as_vw_villa_garage.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/.fxap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/adr0o_kebabking_manifest.ymf`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ybn/adr0o_kebabking_col.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ybn/adr0o_kebabking_col_outside.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ycd/clip@adr0o_drehspies.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ycd/clip@drehspies.ycd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_art_frames.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_ayran.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_ayran_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_backdoor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_deep_fryer.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_doener_stecken.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_drehspies.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_drehspies_schild.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_drehspies_schild_holder.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kabinen_door.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebab_teller.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebab_teller_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_abzug.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_chair.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_counter.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_counter_klein.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_fenster.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_fridge.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_frontdoor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_frontschild.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_glaswall.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_kitchen.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_lights.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_lp.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_lp_room2.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_lp_room3.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_markise.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_mirror.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_outdoor_lighting.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_pizzaofen.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_shell.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_shell_lod.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_sitztheke.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_standingtable.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_standingtable_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten01.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten02.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten03.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten04.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten05.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten06.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten07.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten08.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten09.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten10.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten11.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_theke_zutaten12.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_kebabking_wcdoor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_menutafel_doener.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_menutafel_pizza.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_middoor.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_register.yft`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_saltpepper.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_saltpepper_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_sink.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_siracha_souce.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_siracha_souce_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_sitztrenner.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_spiceholder.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_spiceholder_b.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_spiesmaschine.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_theke_door.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ydr/adr0o_wc_kabine.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ymap/adr0o_kebabking_mlo.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ymap/adr0o_kebabking_outside.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ytd/adr0o_kebabking_customize.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ytd/adr0o_kebabking_lod.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ytd/adr0o_kebabking_textures.ytd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ytyp/adr0o_kebabking.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ytyp/adr0o_kebabking_assets.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ytyp/adr0o_kebabking_lod.ytyp`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_06_0.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_06_b1_gluea.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_06_b1_glueb.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_06_build1b_1.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_06_g1_detail.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_06_gd1_ns.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_06_ground1.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_06_slod_1_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_22_slod1_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_rd1_4.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/dt1_rd1_r1_09.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/hei_dt1_06_long_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/hei_dt1_06_strm_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/hei_dt1_occl_07.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/hei_dt1_rd1_critical_1.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/hei_dt1_rd1_strm_6.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/hi@dt1_06_0.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/hi@dt1_rd1_9.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/vanilla/rc12b_default.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/dt1_lod_18_19_24_25_26_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/dt1_lod_slod3_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/dt1_props_combo0505_slod_children.ydd`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/dt1_rd1_3.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/dt1_rd1_8.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/dt1_rd1_cablemesh115623_thvy.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/dt1_rd1_r1_28.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/hei_dt1_lod.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/hei_dt1_occl_05.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/hei_dt1_rd1.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/hei_dt1_rd1_critical_1.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/hei_dt1_rd1_long_1.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/hei_dt1_rd1_strm_5.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/hei_dt1_rd1_strm_6.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_mrpark_kebab_ls_mrpd/stream/hi@dt1_rd1_9.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/fxmanifest.lua`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/stream/dt1_06_0.ybn`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/stream/dt1_06_b1_glueb.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/stream/dt1_06_g1_detail.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/stream/dt1_06_gd1_ns.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/stream/dt1_06_ground1.ydr`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/stream/hei_dt1_06_long_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/stream/hei_dt1_06_strm_0.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/stream/hei_dt1_occl_07.ymap`
```diff
- Gelöscht
```
`− resources/[stream]/[mlo]/[tstudio]/tstudio_zpatch_pillbox_garage_kebab/stream/hi@dt1_06_0.ybn`
```diff
- Gelöscht
```

## 2026-10-09 13:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558039956495147038"}
+{"channelId":"1550507281396011150","messageId":"1558066488404086906"}
```

## 2026-10-09 11:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1558026502875127910"}
+{"channelId":"1550507281396011150","messageId":"1558039956495147038"}
```

## 2026-10-09 10:22 Uhr
**+0** neu · **~3** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1557994129999532136"}
+{"channelId":"1550507281396011150","messageId":"1558026502875127910"}
```
`~ resources/[okok]/okokBanking/transactions.json`
```diff
-    "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38": [
-        {
-            "value": 3,
-            "sender_identifier": "bank",
-            "reason": "Savings account interest payment (Period 38)",
-            "sender_name": "Savings Interest",
-            "date": "2026/10/01 - 10:00:31",
-            "receiver_name": "Savings Account",
-            "type": "interest_savings",
-            "receiver_identifier": "char2:51a4fca1e0d1af9e02314c787e76ada4e063cd38"
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"join":{"webhookId":"1552971091771924552","url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352"},"versicherung":{"webhookId":"1457180941750632469","url":"https://discord.com/api/webhooks/1457180941750632469/***","channelId":"1457180906816012401"},"adminjail":{"webhookId":"1551161578009796630","url":"https://discord.com/api/webhooks/1551161578009796630/***","channelId":"1551161575690211428"},"freecam_photo":{"webhookId":"1551520132319412284","url":"https://discord.com/api/webhooks/1551520132319412284/***","channelId":"1551520126367572008"},"marriage":{"webhookId":"1467556382038429901","url":"https://discord.com/api/webhooks/1467556382038429901/***","channelId":"1467556343492640830"},"bell":{"webhookId":"1471556835994767400","url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068"},"basicneeds":{"webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"1417917687723724872"},"txadmin":{"webhookId":"1552989826213617715","url":"https://discord.com/api/webhooks/1552989826213617715/***","channelId":"1552989823604756600"},"einreise":{"webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431"},"expose":{"webhookId":"1551624352477225113","url":"https://discord.com/api/webhooks/1551624352477225113/***","channelId":"1551624348660531240"},"clothing_strip":{"webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618"},"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913"},"esx_useractions":{"webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252"},"esx_test":{"webhookId":"1557386332483887194","url":"https://discord.com/api/webhooks/1557386332483887194/***","channelId":"1557386329686413342"},"sozialstunden":{"webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"1552971081491419187"},"staff":{"webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763"},"lager":{"webhookId":"1551161582942158879","url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455"},"esx_chat":{"webhookId":"1557386337580220497","url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664"},"me":{"webhookId":"1513950212480307490","url":"https://discord.com/api/webhooks/1513950212480307490/***","channelId":"1513950191936344245"},"ausbluten":{"webhookId":"1552971079239077968","url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200"},"hotdog":{"webhookId":"1474547103081566412","url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979"},"esx_resources":{"webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557386346782265425"},"troll":{"webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/1552971107500433498/***","channelId":"1552971103910236172"},"frak":{"webhookId":"1552971096847028264","url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169"},"willkommen":{"webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575"},"faction":{"webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***","channelId":"1551161570439208960"},"esx":{"webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370"},"chopshop":{"webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744"},"afk":{"webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617"},"support":{"webhookId":"1552971101741654046","url":"https://discord.com/api/webhooks/1552971101741654046/***","channelId":"1552971099317211136"},"default":{"webhookId":"1551161552537653269","url":"https://discord.com/api/webhooks/1551161552537653269/***","channelId":"1551161550096699392"},"esx_jobs":{"webhookId":"1557386364578955274","url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374"},"sperrzone":{"webhookId":"1552971115209564220","url":"https://discord.com/api/webhooks/1552971115209564220/***","channelId":"1552971110457286766"}},"updatedAt":"2026-10-08T23:07:36Z","categoryId":"1551161549018759170"}
+{"categoryId":"1551161549018759170","webhooks":{"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816","channelId":"1557386352226598913"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497","channelId":"1557386335512305664"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652","channelId":"1551161570439208960"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901","channelId":"1467556343492640830"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","webhookId":"1552971088328392714","channelId":"1552971085937381431"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","webhookId":"1474547103081566412","channelId":"1474547082076622979"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582","channelId":"1557386339866120252"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708","channelId":"1552971120460828763"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789","channelId":"1512475286229356617"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","webhookId":"1457180941750632469","channelId":"1457180906816012401"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194","channelId":"1557386329686413342"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005","channelId":"1551161595436990575"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715","channelId":"1552989823604756600"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264","channelId":"1552971094267527169"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046","channelId":"1552971099317211136"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220","channelId":"1552971110457286766"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552","channelId":"1448120760391565352"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284","channelId":"1551520126367572008"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879","channelId":"1551161580324921455"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709","channelId":"1552971081491419187"},"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","webhookId":"1551624352477225113","channelId":"1551624348660531240"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490","channelId":"1513950191936344245"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400","channelId":"1471556817061544068"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353","channelId":"1551161585614061618"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076","channelId":"1557386346782265425"}},"updatedAt":"2026-10-09T08:01:21Z"}
```

## 2026-10-09 08:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1557953968288833579"}
+{"channelId":"1550507281396011150","messageId":"1557994129999532136"}
```

## 2026-10-09 05:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1557933677806358601"}
+{"channelId":"1550507281396011150","messageId":"1557953968288833579"}
```

## 2026-10-09 04:23 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1557888280693842059"}
+{"channelId":"1550507281396011150","messageId":"1557933677806358601"}
```

## 2026-10-09 01:23 Uhr
**+3** neu · **~8** geändert · **-0** gelöscht
`+ resources/[selfcode]/rmc_core/client/sit.lua`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/data/sits.json`
```diff
+ Neue Datei
```
`+ resources/[selfcode]/rmc_core/server/sit.lua`
```diff
+ Neue Datei
```
`~ resources/[manuell_start]/es_extended/client/modules/callback.lua`
```diff
+        local msg = tostring(errorString)
+        -- Resource wurde neu gestartet, die Callback-Funktion gehört zum alten Script.
+        if msg:find('script host failed', 1, true) then
+            return
+        end
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1557875447251861626"}
+{"channelId":"1550507281396011150","messageId":"1557888280693842059"}
```
`~ resources/[manuell_start]/ox_inventory/server.lua`
```diff
+        local adminId = source
+
+        TriggerEvent('ox_inventory_discord_logs:adminItem', {
+            source = adminId,
+            target = args.target,
+            itemName = item.name,
+            itemLabel = item.label,
+            count = count,
+            action = 'give',
+        })
```
`~ resources/[selfcode]/ox_inventory_discord_logs/server.lua`
```diff
+    admin = 15105570,
+local FLAG_COMPONENTS_V2 = 32768
+
+---@param url string
+---@return string
+local function webhookExecuteUrl(url)
+    if url:find('with_components=', 1, true) then return url end
+    if url:find('?', 1, true) then
+        return url .. '&with_components=true'
+    end
```
`~ resources/[selfcode]/rmc_core/client/marry.lua`
```diff
+local partnerBlipPending = false
+local partnerBlipActive = true
+    if not partnerBlipActive or partnerBlipPending then return end
+    partnerBlipPending = true
+        partnerBlipPending = false
+        if not partnerBlipActive then return end
+        partnerBlipActive = false
```
`~ resources/[selfcode]/rmc_core/config.lua`
```diff
+-- ====== SITZ-CREATOR ======
+-- /sitzcreator: Admin setzt sich mit Animation, justiert exakt und speichert den Platz.
+-- Gespeicherte Plätze: ox_target „Hinsetzen“, Aufstehen mit Enter.
+Config.Sit = {
+    Enabled = true,
+    Command = 'sitzcreator',
+    AllowedGroups = { owner = true, superadmin = true, admin = true },
+    AcePermission = 'rmc.sit',
+    File = 'data/sits.json',
+    TargetRadius = 0.8,
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-08T22:01:06Z","webhooks":{"me":{"webhookId":"1513950212480307490","channelId":"1513950191936344245","url":"https://discord.com/api/webhooks/1513950212480307490/***"},"expose":{"webhookId":"1551624352477225113","channelId":"1551624348660531240","url":"https://discord.com/api/webhooks/1551624352477225113/***"},"marriage":{"webhookId":"1467556382038429901","channelId":"1467556343492640830","url":"https://discord.com/api/webhooks/1467556382038429901/***"},"hotdog":{"webhookId":"1474547103081566412","channelId":"1474547082076622979","url":"https://discord.com/api/webhooks/1474547103081566412/***"},"afk":{"webhookId":"1512475306554953789","channelId":"1512475286229356617","url":"https://discord.com/api/webhooks/1512475306554953789/***"},"esx":{"webhookId":"1557386326951592027","channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***"},"troll":{"webhookId":"1552971107500433498","channelId":"1552971103910236172","url":"https://discord.com/api/webhooks/1552971107500433498/***"},"staff":{"webhookId":"1552971123233394708","channelId":"1552971120460828763","url":"https://discord.com/api/webhooks/1552971123233394708/***"},"faction":{"webhookId":"1551161573194731652","channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"willkommen":{"webhookId":"1551161597853049005","channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/1551161597853049005/***"},"einreise":{"webhookId":"1552971088328392714","channelId":"1552971085937381431","url":"https://discord.com/api/webhooks/1552971088328392714/***"},"clothing_strip":{"webhookId":"1551161592467423353","channelId":"1551161585614061618","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"versicherung":{"webhookId":"1457180941750632469","channelId":"1457180906816012401","url":"https://discord.com/api/webhooks/1457180941750632469/***"},"esx_test":{"webhookId":"1557386332483887194","channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"basicneeds":{"webhookId":"1552971931869777932","channelId":"1417917687723724872","url":"https://discord.com/api/webhooks/1552971931869777932/***"},"sperrzone":{"webhookId":"1552971115209564220","channelId":"1552971110457286766","url":"https://discord.com/api/webhooks/1552971115209564220/***"},"esx_chat":{"webhookId":"1557386337580220497","channelId":"1557386335512305664","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"frak":{"webhookId":"1552971096847028264","channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/***"},"txadmin":{"webhookId":"1552989826213617715","channelId":"1552989823604756600","url":"https://discord.com/api/webhooks/1552989826213617715/***"},"freecam_photo":{"webhookId":"1551520132319412284","channelId":"1551520126367572008","url":"https://discord.com/api/webhooks/1551520132319412284/***"},"bell":{"webhookId":"1471556835994767400","channelId":"1471556817061544068","url":"https://discord.com/api/webhooks/1471556835994767400/***"},"esx_resources":{"webhookId":"1557386349395583076","channelId":"1557386346782265425","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"lager":{"webhookId":"1551161582942158879","channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***"},"esx_jobs":{"webhookId":"1557386364578955274","channelId":"1557386361172918374","url":"https://discord.com/api/webhooks/1557386364578955274/***"},"join":{"webhookId":"1552971091771924552","channelId":"1448120760391565352","url":"https://discord.com/api/webhooks/1552971091771924552/***"},"support":{"webhookId":"1552971101741654046","channelId":"1552971099317211136","url":"https://discord.com/api/webhooks/1552971101741654046/***"},"ausbluten":{"webhookId":"1552971079239077968","channelId":"1552971076718297200","url":"https://discord.com/api/webhooks/1552971079239077968/***"},"chopshop":{"webhookId":"1552971074814218312","channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***"},"esx_paycheck":{"webhookId":"1557386357381533816","channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***"},"esx_useractions":{"webhookId":"1557386342755991582","channelId":"1557386339866120252","url":"https://discord.com/api/webhooks/1557386342755991582/***"},"adminjail":{"webhookId":"1551161578009796630","channelId":"1551161575690211428","url":"https://discord.com/api/webhooks/1551161578009796630/***"},"default":{"webhookId":"1551161552537653269","channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***"},"sozialstunden":{"webhookId":"1552971083731181709","channelId":"1552971081491419187","url":"https://discord.com/api/webhooks/1552971083731181709/***"}},"categoryId":"1551161549018759170"}
+{"webhooks":{"join":{"webhookId":"1552971091771924552","url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352"},"versicherung":{"webhookId":"1457180941750632469","url":"https://discord.com/api/webhooks/1457180941750632469/***","channelId":"1457180906816012401"},"adminjail":{"webhookId":"1551161578009796630","url":"https://discord.com/api/webhooks/1551161578009796630/***","channelId":"1551161575690211428"},"freecam_photo":{"webhookId":"1551520132319412284","url":"https://discord.com/api/webhooks/1551520132319412284/***","channelId":"1551520126367572008"},"marriage":{"webhookId":"1467556382038429901","url":"https://discord.com/api/webhooks/1467556382038429901/***","channelId":"1467556343492640830"},"bell":{"webhookId":"1471556835994767400","url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068"},"basicneeds":{"webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"1417917687723724872"},"txadmin":{"webhookId":"1552989826213617715","url":"https://discord.com/api/webhooks/1552989826213617715/***","channelId":"1552989823604756600"},"einreise":{"webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431"},"expose":{"webhookId":"1551624352477225113","url":"https://discord.com/api/webhooks/1551624352477225113/***","channelId":"1551624348660531240"},"clothing_strip":{"webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618"},"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913"},"esx_useractions":{"webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252"},"esx_test":{"webhookId":"1557386332483887194","url":"https://discord.com/api/webhooks/1557386332483887194/***","channelId":"1557386329686413342"},"sozialstunden":{"webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"1552971081491419187"},"staff":{"webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763"},"lager":{"webhookId":"1551161582942158879","url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455"},"esx_chat":{"webhookId":"1557386337580220497","url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664"},"me":{"webhookId":"1513950212480307490","url":"https://discord.com/api/webhooks/1513950212480307490/***","channelId":"1513950191936344245"},"ausbluten":{"webhookId":"1552971079239077968","url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200"},"hotdog":{"webhookId":"1474547103081566412","url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979"},"esx_resources":{"webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557386346782265425"},"troll":{"webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/1552971107500433498/***","channelId":"1552971103910236172"},"frak":{"webhookId":"1552971096847028264","url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169"},"willkommen":{"webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575"},"faction":{"webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***","channelId":"1551161570439208960"},"esx":{"webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370"},"chopshop":{"webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744"},"afk":{"webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617"},"support":{"webhookId":"1552971101741654046","url":"https://discord.com/api/webhooks/1552971101741654046/***","channelId":"1552971099317211136"},"default":{"webhookId":"1551161552537653269","url":"https://discord.com/api/webhooks/1551161552537653269/***","channelId":"1551161550096699392"},"esx_jobs":{"webhookId":"1557386364578955274","url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374"},"sperrzone":{"webhookId":"1552971115209564220","url":"https://discord.com/api/webhooks/1552971115209564220/***","channelId":"1552971110457286766"}},"updatedAt":"2026-10-08T23:07:36Z","categoryId":"1551161549018759170"}
```
`~ resources/[selfcode]/rmc_core/fxmanifest.lua`
```diff
+    'data/sits.json',
```

## 2026-10-09 00:23 Uhr
**+0** neu · **~4** geändert · **-0** gelöscht
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1557866174803476521"}
+{"channelId":"1550507281396011150","messageId":"1557875447251861626"}
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","channelId":"1551624348660531240","webhookId":"1551624352477225113"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374","webhookId":"1557386364578955274"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068","webhookId":"1471556835994767400"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557386346782265425","webhookId":"1557386349395583076"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763","webhookId":"1552971123233394708"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913","webhookId":"1557386357381533816"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","channelId":"1551161575690211428","webhookId":"1551161578009796630"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","channelId":"1513950191936344245","webhookId":"1513950212480307490"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370","webhookId":"1557386326951592027"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","channelId":"1551161550096699392","webhookId":"1551161552537653269"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","channelId":"1557386329686413342","webhookId":"1557386332483887194"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617","webhookId":"1512475306554953789"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455","webhookId":"1551161582942158879"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","channelId":"1467556343492640830","webhookId":"1467556382038429901"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","channelId":"1457180906816012401","webhookId":"1457180941750632469"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252","webhookId":"1557386342755991582"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","channelId":"1552971110457286766","webhookId":"1552971115209564220"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664","webhookId":"1557386337580220497"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","channelId":"1551161570439208960","webhookId":"1551161573194731652"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618","webhookId":"1551161592467423353"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924552"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744","webhookId":"1552971074814218312"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"1417917687723724872","webhookId":"1552971931869777932"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","channelId":"1552971103910236172","webhookId":"1552971107500433498"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","channelId":"1551520126367572008","webhookId":"1551520132319412284"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"1552971081491419187","webhookId":"1552971083731181709"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979","webhookId":"1474547103081566412"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200","webhookId":"1552971079239077968"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","channelId":"1552989823604756600","webhookId":"1552989826213617715"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431","webhookId":"1552971088328392714"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169","webhookId":"1552971096847028264"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","channelId":"1552971099317211136","webhookId":"1552971101741654046"}},"updatedAt":"2026-10-08T19:54:27Z","categoryId":"1551161549018759170"}
+{"updatedAt":"2026-10-08T22:01:06Z","webhooks":{"me":{"webhookId":"1513950212480307490","channelId":"1513950191936344245","url":"https://discord.com/api/webhooks/1513950212480307490/***"},"expose":{"webhookId":"1551624352477225113","channelId":"1551624348660531240","url":"https://discord.com/api/webhooks/1551624352477225113/***"},"marriage":{"webhookId":"1467556382038429901","channelId":"1467556343492640830","url":"https://discord.com/api/webhooks/1467556382038429901/***"},"hotdog":{"webhookId":"1474547103081566412","channelId":"1474547082076622979","url":"https://discord.com/api/webhooks/1474547103081566412/***"},"afk":{"webhookId":"1512475306554953789","channelId":"1512475286229356617","url":"https://discord.com/api/webhooks/1512475306554953789/***"},"esx":{"webhookId":"1557386326951592027","channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***"},"troll":{"webhookId":"1552971107500433498","channelId":"1552971103910236172","url":"https://discord.com/api/webhooks/1552971107500433498/***"},"staff":{"webhookId":"1552971123233394708","channelId":"1552971120460828763","url":"https://discord.com/api/webhooks/1552971123233394708/***"},"faction":{"webhookId":"1551161573194731652","channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"willkommen":{"webhookId":"1551161597853049005","channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/1551161597853049005/***"},"einreise":{"webhookId":"1552971088328392714","channelId":"1552971085937381431","url":"https://discord.com/api/webhooks/1552971088328392714/***"},"clothing_strip":{"webhookId":"1551161592467423353","channelId":"1551161585614061618","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"versicherung":{"webhookId":"1457180941750632469","channelId":"1457180906816012401","url":"https://discord.com/api/webhooks/1457180941750632469/***"},"esx_test":{"webhookId":"1557386332483887194","channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"basicneeds":{"webhookId":"1552971931869777932","channelId":"1417917687723724872","url":"https://discord.com/api/webhooks/1552971931869777932/***"},"sperrzone":{"webhookId":"1552971115209564220","channelId":"1552971110457286766","url":"https://discord.com/api/webhooks/1552971115209564220/***"},"esx_chat":{"webhookId":"1557386337580220497","channelId":"1557386335512305664","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"frak":{"webhookId":"1552971096847028264","channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/***"},"txadmin":{"webhookId":"1552989826213617715","channelId":"1552989823604756600","url":"https://discord.com/api/webhooks/1552989826213617715/***"},"freecam_photo":{"webhookId":"1551520132319412284","channelId":"1551520126367572008","url":"https://discord.com/api/webhooks/1551520132319412284/***"},"bell":{"webhookId":"1471556835994767400","channelId":"1471556817061544068","url":"https://discord.com/api/webhooks/1471556835994767400/***"},"esx_resources":{"webhookId":"1557386349395583076","channelId":"1557386346782265425","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"lager":{"webhookId":"1551161582942158879","channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***"},"esx_jobs":{"webhookId":"1557386364578955274","channelId":"1557386361172918374","url":"https://discord.com/api/webhooks/1557386364578955274/***"},"join":{"webhookId":"1552971091771924552","channelId":"1448120760391565352","url":"https://discord.com/api/webhooks/1552971091771924552/***"},"support":{"webhookId":"1552971101741654046","channelId":"1552971099317211136","url":"https://discord.com/api/webhooks/1552971101741654046/***"},"ausbluten":{"webhookId":"1552971079239077968","channelId":"1552971076718297200","url":"https://discord.com/api/webhooks/1552971079239077968/***"},"chopshop":{"webhookId":"1552971074814218312","channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***"},"esx_paycheck":{"webhookId":"1557386357381533816","channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***"},"esx_useractions":{"webhookId":"1557386342755991582","channelId":"1557386339866120252","url":"https://discord.com/api/webhooks/1557386342755991582/***"},"adminjail":{"webhookId":"1551161578009796630","channelId":"1551161575690211428","url":"https://discord.com/api/webhooks/1551161578009796630/***"},"default":{"webhookId":"1551161552537653269","channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***"},"sozialstunden":{"webhookId":"1552971083731181709","channelId":"1552971081491419187","url":"https://discord.com/api/webhooks/1552971083731181709/***"}},"categoryId":"1551161549018759170"}
```
`~ server.cfg`
```diff
(Secrets — Inhalt unterdrückt)
```
`~ server.cfg.bkp`
```diff
(Secrets — Inhalt unterdrückt)
```

## 2026-10-08 23:24 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[jaksam_scripte]/jobs_creator/_modules/stash/ox-inventory/sv_stash.lua`
```diff
-    slots = 50,
-    weight = 100000,
+    slots = 500,
+    weight = 10000000000,
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1557849594405191745"}
+{"channelId":"1550507281396011150","messageId":"1557866174803476521"}
```

## 2026-10-08 22:24 Uhr
**+0** neu · **~123** geändert · **-0** gelöscht
`~ resources/[jaksam_scripte]/jobs_creator/.fxap`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/billing.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/checkidentity.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/checkvehicleowner.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/handcuffs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/heal.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/impoundvehicle.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/licenses.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/lockpick.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/placeableobjects.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/repairvehicle.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/revive.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/rob.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/washvehicle.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/main.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/armory.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/boss.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/crafting_table.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/delivery.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/harvest.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/job_outfit.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/job_shop.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/market.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/permanent_garage.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/process.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/safe.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/shop.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/stash.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/teleport.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/temporary_garage.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/wardrobe.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/weapon_upgrader.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/nui_callbacks.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/fxmanifest.lua`
```diff
-version '9.0.1'
+version '9.0.2'
```
`~ resources/[jaksam_scripte]/jobs_creator/server/actions.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/code_integrator.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/functions.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/gangs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/main.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/armory.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/boss.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/crafting_table.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/delivery.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/duty.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/harvest.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/job_outfit.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/job_shop.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/market.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/permanent_garage.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/process.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/safe.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/shop.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/stash.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/teleport.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/temporary_garage.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/wardrobe.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/weapon_upgrader.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/migration.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/sv_statistics.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/shared/shared.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/stream/L1_1.ydr`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/callbacks/cl_callbacks.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/callbacks/sv_callbacks.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/database/database.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/animations/cl_animations.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/announcements/cl_announcements.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/announcements/sv_announcements.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/blips/cl_blips.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/blips/sv_blips.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/boss_menu/cl_boss_menu.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/choose_object/cl_choose_object.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/choose_object/sv_choose_object.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/cl_dialogs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/controls/cl_controls.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/external_scripts_names/cl_external_scripts_names.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/external_scripts_names/sv_external_scripts_names.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/items/cl_items.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/items/sv_items.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/jobs/cl_jobs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/jobs/sv_jobs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/markers/cl_markers.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/markers/sv_markers.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/menu/cl_menu.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/misc/cl_misc.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/misc/sv_misc.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/missing_menu/cl_missing_menu.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/missing_menu/sv_missing_menu.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/modules/cl_modules.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/modules/sv_modules.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/multijob/cl_multijob.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/not_allowed/cl_not_allowed.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/not_allowed/sv_not_allowed.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/objects/cl_objects.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/peds/cl_peds.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/peds/sv_peds.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/place_entity/cl_place_entity.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/progressbar/cl_progressbar.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/progressbar/sv_progressbar.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/single_job/cl_single_job.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/single_job/sv_single_job.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/skillcheck/cl_skillcheck.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/sv_dialogs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/weapons/cl_weapons.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/weapons/sv_weapons.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/framework/cl_framework.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/framework/sh_framework.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/framework/sv_framework.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/miscellaneous/cl_miscellaneous.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/miscellaneous/sh_miscellaneous.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/miscellaneous/sv_miscellaneous.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/settings/cl_settings.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/settings/sv_settings.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/targeting/cl_targeting.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/warnings/sv_escrow.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/warnings/sv_framework_checker.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/wrapper/sv_wrapper.js`
```diff
-		]
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/wrapper/sv_wrapper.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1557835257644847185"}
+{"channelId":"1550507281396011150","messageId":"1557849594405191745"}
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"webhooks":{"expose":{"webhookId":"1551624352477225113","url":"https://discord.com/api/webhooks/1551624352477225113/***","channelId":"1551624348660531240"},"esx":{"webhookId":"1557386326951592027","url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370"},"bell":{"webhookId":"1471556835994767400","url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068"},"txadmin":{"webhookId":"1552989826213617715","url":"https://discord.com/api/webhooks/1552989826213617715/***","channelId":"1552989823604756600"},"marriage":{"webhookId":"1467556382038429901","url":"https://discord.com/api/webhooks/1467556382038429901/***","channelId":"1467556343492640830"},"clothing_strip":{"webhookId":"1551161592467423353","url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618"},"afk":{"webhookId":"1512475306554953789","url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617"},"me":{"webhookId":"1513950212480307490","url":"https://discord.com/api/webhooks/1513950212480307490/***","channelId":"1513950191936344245"},"frak":{"webhookId":"1552971096847028264","url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169"},"einreise":{"webhookId":"1552971088328392714","url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431"},"sozialstunden":{"webhookId":"1552971083731181709","url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"1552971081491419187"},"default":{"webhookId":"1551161552537653269","url":"https://discord.com/api/webhooks/1551161552537653269/***","channelId":"1551161550096699392"},"chopshop":{"webhookId":"1552971074814218312","url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744"},"adminjail":{"webhookId":"1551161578009796630","url":"https://discord.com/api/webhooks/1551161578009796630/***","channelId":"1551161575690211428"},"esx_test":{"webhookId":"1557386332483887194","url":"https://discord.com/api/webhooks/1557386332483887194/***","channelId":"1557386329686413342"},"esx_jobs":{"webhookId":"1557386364578955274","url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374"},"basicneeds":{"webhookId":"1552971931869777932","url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"1417917687723724872"},"esx_resources":{"webhookId":"1557386349395583076","url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557386346782265425"},"faction":{"webhookId":"1551161573194731652","url":"https://discord.com/api/webhooks/1551161573194731652/***","channelId":"1551161570439208960"},"support":{"webhookId":"1552971101741654046","url":"https://discord.com/api/webhooks/1552971101741654046/***","channelId":"1552971099317211136"},"ausbluten":{"webhookId":"1552971079239077968","url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200"},"sperrzone":{"webhookId":"1552971115209564220","url":"https://discord.com/api/webhooks/1552971115209564220/***","channelId":"1552971110457286766"},"hotdog":{"webhookId":"1474547103081566412","url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979"},"esx_useractions":{"webhookId":"1557386342755991582","url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252"},"freecam_photo":{"webhookId":"1551520132319412284","url":"https://discord.com/api/webhooks/1551520132319412284/***","channelId":"1551520126367572008"},"esx_paycheck":{"webhookId":"1557386357381533816","url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913"},"willkommen":{"webhookId":"1551161597853049005","url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575"},"join":{"webhookId":"1552971091771924552","url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352"},"troll":{"webhookId":"1552971107500433498","url":"https://discord.com/api/webhooks/1552971107500433498/***","channelId":"1552971103910236172"},"lager":{"webhookId":"1551161582942158879","url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455"},"staff":{"webhookId":"1552971123233394708","url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763"},"versicherung":{"webhookId":"1457180941750632469","url":"https://discord.com/api/webhooks/1457180941750632469/***","channelId":"1457180906816012401"},"esx_chat":{"webhookId":"1557386337580220497","url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664"}},"categoryId":"1551161549018759170","updatedAt":"2026-10-08T18:19:20Z"}
+{"webhooks":{"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","channelId":"1551624348660531240","webhookId":"1551624352477225113"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","channelId":"1557386361172918374","webhookId":"1557386364578955274"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","channelId":"1471556817061544068","webhookId":"1471556835994767400"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","channelId":"1557386346782265425","webhookId":"1557386349395583076"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","channelId":"1552971120460828763","webhookId":"1552971123233394708"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","channelId":"1557386352226598913","webhookId":"1557386357381533816"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","channelId":"1551161575690211428","webhookId":"1551161578009796630"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","channelId":"1513950191936344245","webhookId":"1513950212480307490"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","channelId":"1420103430562910370","webhookId":"1557386326951592027"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","channelId":"1551161550096699392","webhookId":"1551161552537653269"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","channelId":"1557386329686413342","webhookId":"1557386332483887194"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","channelId":"1512475286229356617","webhookId":"1512475306554953789"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","channelId":"1551161580324921455","webhookId":"1551161582942158879"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","channelId":"1467556343492640830","webhookId":"1467556382038429901"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","channelId":"1457180906816012401","webhookId":"1457180941750632469"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","channelId":"1557386339866120252","webhookId":"1557386342755991582"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","channelId":"1552971110457286766","webhookId":"1552971115209564220"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","channelId":"1557386335512305664","webhookId":"1557386337580220497"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","channelId":"1551161570439208960","webhookId":"1551161573194731652"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","channelId":"1551161585614061618","webhookId":"1551161592467423353"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","channelId":"1448120760391565352","webhookId":"1552971091771924552"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","channelId":"1552971071882399744","webhookId":"1552971074814218312"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","channelId":"1417917687723724872","webhookId":"1552971931869777932"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","channelId":"1552971103910236172","webhookId":"1552971107500433498"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","channelId":"1551520126367572008","webhookId":"1551520132319412284"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","channelId":"1552971081491419187","webhookId":"1552971083731181709"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","channelId":"1474547082076622979","webhookId":"1474547103081566412"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","channelId":"1552971076718297200","webhookId":"1552971079239077968"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","channelId":"1552989823604756600","webhookId":"1552989826213617715"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","channelId":"1552971085937381431","webhookId":"1552971088328392714"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","channelId":"1551161595436990575","webhookId":"1551161597853049005"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","channelId":"1552971094267527169","webhookId":"1552971096847028264"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","channelId":"1552971099317211136","webhookId":"1552971101741654046"}},"updatedAt":"2026-10-08T19:54:27Z","categoryId":"1551161549018759170"}
```
`~ resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ytd/adr0o_kebabking_customize.ytd`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[stream]/[mlo]/[tstudio]/tstudio_kebabking/stream/custom/ytd/adr0o_kebabking_textures.ytd`
```diff
(Binärdatei / kein Text-Diff)
```
`~ server.cfg`
```diff
(Secrets — Inhalt unterdrückt)
```
`~ server.cfg.bkp`
```diff
(Secrets — Inhalt unterdrückt)
```

## 2026-10-08 21:24 Uhr
**+0** neu · **~123** geändert · **-0** gelöscht
`~ resources/[esx_addons]/EasyAdmin/backups/_backups.json`
```diff
-            "backupTimestamp": 1791051635,
-            "id": 11,
-            "backupDate": "20_20_03_10_2026",
-            "backupFile": "banlist_20_20_03_10_2026.json"
-        },
-        {
-            "backupTimestamp": 1791051760,
-            "id": 11,
-            "backupDate": "20_22_03_10_2026",
-            "backupFile": "banlist_20_22_03_10_2026.json"
```
`~ resources/[jaksam_scripte]/jobs_creator/.fxap`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/_modules/stash/ox-inventory/sv_stash.lua`
```diff
-    slots = 500,
-    weight = 100000000000,
+    slots = 50,
+    weight = 100000,
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/billing.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/checkidentity.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/checkvehicleowner.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/handcuffs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/heal.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/impoundvehicle.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/licenses.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/lockpick.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/placeableobjects.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/repairvehicle.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/revive.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/rob.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/actions/washvehicle.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/main.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/armory.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/boss.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/crafting_table.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/delivery.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/harvest.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/job_outfit.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/job_shop.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/market.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/permanent_garage.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/process.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/safe.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/shop.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/stash.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/teleport.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/temporary_garage.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/wardrobe.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/markers/weapon_upgrader.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/client/nui_callbacks.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/fxmanifest.lua`
```diff
-version '9.0'
+version '9.0.1'
```
`~ resources/[jaksam_scripte]/jobs_creator/server/actions.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/code_integrator.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/functions.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/gangs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/main.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/armory.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/boss.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/crafting_table.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/delivery.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/duty.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/harvest.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/job_outfit.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/job_shop.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/market.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/permanent_garage.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/process.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/safe.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/shop.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/stash.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/teleport.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/temporary_garage.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/wardrobe.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/markers/weapon_upgrader.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/migration.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/server/sv_statistics.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/shared/shared.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/sql/jobs_action_history.sql`
```diff
-)
+) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
```
`~ resources/[jaksam_scripte]/jobs_creator/sql/jobs_society_logs.sql`
```diff
-) ENGINE=InnoDB;
+) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
```
`~ resources/[jaksam_scripte]/jobs_creator/stream/L1_1.ydr`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/callbacks/cl_callbacks.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/callbacks/sv_callbacks.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/database/database.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/animations/cl_animations.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/announcements/cl_announcements.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/announcements/sv_announcements.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/blips/cl_blips.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/blips/sv_blips.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/boss_menu/cl_boss_menu.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/choose_object/cl_choose_object.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/choose_object/sv_choose_object.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/cl_dialogs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/controls/cl_controls.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/external_scripts_names/cl_external_scripts_names.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/external_scripts_names/sv_external_scripts_names.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/items/cl_items.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/items/sv_items.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/jobs/cl_jobs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/jobs/sv_jobs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/markers/cl_markers.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/markers/sv_markers.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/menu/cl_menu.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/misc/cl_misc.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/misc/sv_misc.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/missing_menu/cl_missing_menu.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/missing_menu/sv_missing_menu.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/modules/cl_modules.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/modules/sv_modules.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/multijob/cl_multijob.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/not_allowed/cl_not_allowed.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/not_allowed/sv_not_allowed.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/objects/cl_objects.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/peds/cl_peds.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/peds/sv_peds.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/place_entity/cl_place_entity.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/progressbar/cl_progressbar.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/progressbar/sv_progressbar.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/single_job/cl_single_job.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/single_job/sv_single_job.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/skillcheck/cl_skillcheck.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/sv_dialogs.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/weapons/cl_weapons.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/dialogs/weapons/sv_weapons.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/framework/cl_framework.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/framework/sh_framework.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/framework/sv_framework.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/miscellaneous/cl_miscellaneous.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/miscellaneous/sh_miscellaneous.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/miscellaneous/sv_miscellaneous.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/settings/cl_settings.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/settings/sv_settings.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/targeting/cl_targeting.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/warnings/sv_escrow.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/warnings/sv_framework_checker.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/wrapper/sv_wrapper.js`
```diff
-const {Worker} = require('worker_threads')
-const pathModule = require('path')
-
-const worker = new Worker(pathModule.join(GetResourcePath(GetCurrentResourceName()), 'utils', 'wrapper', 'sv_fs_worker.js'))
-const signal = new SharedArrayBuffer(4)
-
-function workerCall(op, args) {
-	const view = new Int32Array(signal)
-	Atomics.store(view, 0, 0)
-	worker.postMessage({op, args, signal})
```
`~ resources/[jaksam_scripte]/jobs_creator/utils/wrapper/sv_wrapper.lua`
```diff
(Binärdatei / kein Text-Diff)
```
`~ resources/[manuell_start]/es_extended/server/modules/discord/panel.json`
```diff
-{"channelId":"1550507281396011150","messageId":"1557818913251659848"}
+{"channelId":"1550507281396011150","messageId":"1557835257644847185"}
```
`~ resources/[rtx]/rtx_gym/config.lua`
```diff
-		coords = vector3(330.84, -601.04, 43.40),-- Jonas
+		coords = vector3(-2764.40, 3749.08, 4.50),-- Jonas
```

## 2026-10-08 18:24 Uhr
**+0** neu · **~2** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/client/personalmenu.lua`
```diff
-        SetCreateRandomCops(true)
-        SetCreateRandomCopsNotOnScenarios(true)
-        DistantCopCarSirens(true)
+        SetCreateRandomCops(false)
+        SetCreateRandomCopsNotOnScenarios(false)
+        SetCreateRandomCopsOnScenarios(false)
+        DistantCopCarSirens(false)
```
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"categoryId":"1551161549018759170","webhooks":{"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901","channelId":"1467556343492640830"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709","channelId":"1552971081491419187"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552","channelId":"1448120760391565352"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652","channelId":"1551161570439208960"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046","channelId":"1552971099317211136"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264","channelId":"1552971094267527169"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194","channelId":"1557386329686413342"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715","channelId":"1552989823604756600"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284","channelId":"1551520126367572008"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490","channelId":"1513950191936344245"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353","channelId":"1551161585614061618"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220","channelId":"1552971110457286766"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497","channelId":"1557386335512305664"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708","channelId":"1552971120460828763"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400","channelId":"1471556817061544068"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879","channelId":"1551161580324921455"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076","channelId":"1557386346782265425"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","webhookId":"1474547103081566412","channelId":"1474547082076622979"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816","channelId":"1557386352226598913"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","webhookId":"1457180941750632469","channelId":"1457180906816012401"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005","channelId":"1551161595436990575"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582","channelId":"1557386339866120252"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789","channelId":"1512475286229356617"},"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","webhookId":"1551624352477225113","channelId":"1551624348660531240"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","webhookId":"1552971088328392714","channelId":"1552971085937381431"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"}},"updatedAt":"2026-10-08T13:23:39Z"}
+{"categoryId":"1551161549018759170","updatedAt":"2026-10-08T16:09:18Z","webhooks":{"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","webhookId":"1552971088328392714","channelId":"1552971085937381431"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708","channelId":"1552971120460828763"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076","channelId":"1557386346782265425"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194","channelId":"1557386329686413342"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400","channelId":"1471556817061544068"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497","channelId":"1557386335512305664"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","webhookId":"1474547103081566412","channelId":"1474547082076622979"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046","channelId":"1552971099317211136"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715","channelId":"1552989823604756600"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","webhookId":"1457180941750632469","channelId":"1457180906816012401"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901","channelId":"1467556343492640830"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816","channelId":"1557386352226598913"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284","channelId":"1551520126367572008"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490","channelId":"1513950191936344245"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552","channelId":"1448120760391565352"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789","channelId":"1512475286229356617"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879","channelId":"1551161580324921455"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652","channelId":"1551161570439208960"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353","channelId":"1551161585614061618"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005","channelId":"1551161595436990575"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709","channelId":"1552971081491419187"},"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","webhookId":"1551624352477225113","channelId":"1551624348660531240"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582","channelId":"1557386339866120252"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264","channelId":"1552971094267527169"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220","channelId":"1552971110457286766"}}}
```

## 2026-10-08 16:22 Uhr
**+0** neu · **~1** geändert · **-0** gelöscht
`~ resources/[selfcode]/rmc_core/data/discord_webhooks.json`
```diff
-{"updatedAt":"2026-10-08T08:01:02Z","webhooks":{"esx_useractions":{"webhookId":"1557386342755991582","channelId":"1557386339866120252","url":"https://discord.com/api/webhooks/1557386342755991582/***"},"me":{"webhookId":"1513950212480307490","channelId":"1513950191936344245","url":"https://discord.com/api/webhooks/1513950212480307490/***"},"bell":{"webhookId":"1471556835994767400","channelId":"1471556817061544068","url":"https://discord.com/api/webhooks/1471556835994767400/***"},"join":{"webhookId":"1552971091771924552","channelId":"1448120760391565352","url":"https://discord.com/api/webhooks/1552971091771924552/***"},"faction":{"webhookId":"1551161573194731652","channelId":"1551161570439208960","url":"https://discord.com/api/webhooks/1551161573194731652/***"},"esx":{"webhookId":"1557386326951592027","channelId":"1420103430562910370","url":"https://discord.com/api/webhooks/1557386326951592027/***"},"basicneeds":{"webhookId":"1552971931869777932","channelId":"1417917687723724872","url":"https://discord.com/api/webhooks/1552971931869777932/***"},"freecam_photo":{"webhookId":"1551520132319412284","channelId":"1551520126367572008","url":"https://discord.com/api/webhooks/1551520132319412284/***"},"esx_resources":{"webhookId":"1557386349395583076","channelId":"1557386346782265425","url":"https://discord.com/api/webhooks/1557386349395583076/***"},"frak":{"webhookId":"1552971096847028264","channelId":"1552971094267527169","url":"https://discord.com/api/webhooks/1552971096847028264/***"},"default":{"webhookId":"1551161552537653269","channelId":"1551161550096699392","url":"https://discord.com/api/webhooks/1551161552537653269/***"},"troll":{"webhookId":"1552971107500433498","channelId":"1552971103910236172","url":"https://discord.com/api/webhooks/1552971107500433498/***"},"willkommen":{"webhookId":"1551161597853049005","channelId":"1551161595436990575","url":"https://discord.com/api/webhooks/1551161597853049005/***"},"hotdog":{"webhookId":"1474547103081566412","channelId":"1474547082076622979","url":"https://discord.com/api/webhooks/1474547103081566412/***"},"txadmin":{"webhookId":"1552989826213617715","channelId":"1552989823604756600","url":"https://discord.com/api/webhooks/1552989826213617715/***"},"versicherung":{"webhookId":"1457180941750632469","channelId":"1457180906816012401","url":"https://discord.com/api/webhooks/1457180941750632469/***"},"esx_test":{"webhookId":"1557386332483887194","channelId":"1557386329686413342","url":"https://discord.com/api/webhooks/1557386332483887194/***"},"expose":{"webhookId":"1551624352477225113","channelId":"1551624348660531240","url":"https://discord.com/api/webhooks/1551624352477225113/***"},"sozialstunden":{"webhookId":"1552971083731181709","channelId":"1552971081491419187","url":"https://discord.com/api/webhooks/1552971083731181709/***"},"esx_chat":{"webhookId":"1557386337580220497","channelId":"1557386335512305664","url":"https://discord.com/api/webhooks/1557386337580220497/***"},"chopshop":{"webhookId":"1552971074814218312","channelId":"1552971071882399744","url":"https://discord.com/api/webhooks/1552971074814218312/***"},"adminjail":{"webhookId":"1551161578009796630","channelId":"1551161575690211428","url":"https://discord.com/api/webhooks/1551161578009796630/***"},"afk":{"webhookId":"1512475306554953789","channelId":"1512475286229356617","url":"https://discord.com/api/webhooks/1512475306554953789/***"},"support":{"webhookId":"1552971101741654046","channelId":"1552971099317211136","url":"https://discord.com/api/webhooks/1552971101741654046/***"},"clothing_strip":{"webhookId":"1551161592467423353","channelId":"1551161585614061618","url":"https://discord.com/api/webhooks/1551161592467423353/***"},"einreise":{"webhookId":"1552971088328392714","channelId":"1552971085937381431","url":"https://discord.com/api/webhooks/1552971088328392714/***"},"esx_jobs":{"webhookId":"1557386364578955274","channelId":"1557386361172918374","url":"https://discord.com/api/webhooks/1557386364578955274/***"},"lager":{"webhookId":"1551161582942158879","channelId":"1551161580324921455","url":"https://discord.com/api/webhooks/1551161582942158879/***"},"staff":{"webhookId":"1552971123233394708","channelId":"1552971120460828763","url":"https://discord.com/api/webhooks/1552971123233394708/***"},"marriage":{"webhookId":"1467556382038429901","channelId":"1467556343492640830","url":"https://discord.com/api/webhooks/1467556382038429901/***"},"ausbluten":{"webhookId":"1552971079239077968","channelId":"1552971076718297200","url":"https://discord.com/api/webhooks/1552971079239077968/***"},"esx_paycheck":{"webhookId":"1557386357381533816","channelId":"1557386352226598913","url":"https://discord.com/api/webhooks/1557386357381533816/***"},"sperrzone":{"webhookId":"1552971115209564220","channelId":"1552971110457286766","url":"https://discord.com/api/webhooks/1552971115209564220/***"}},"categoryId":"1551161549018759170"}
+{"categoryId":"1551161549018759170","webhooks":{"marriage":{"url":"https://discord.com/api/webhooks/1467556382038429901/***","webhookId":"1467556382038429901","channelId":"1467556343492640830"},"ausbluten":{"url":"https://discord.com/api/webhooks/1552971079239077968/***","webhookId":"1552971079239077968","channelId":"1552971076718297200"},"sozialstunden":{"url":"https://discord.com/api/webhooks/1552971083731181709/***","webhookId":"1552971083731181709","channelId":"1552971081491419187"},"default":{"url":"https://discord.com/api/webhooks/1551161552537653269/***","webhookId":"1551161552537653269","channelId":"1551161550096699392"},"join":{"url":"https://discord.com/api/webhooks/1552971091771924552/***","webhookId":"1552971091771924552","channelId":"1448120760391565352"},"faction":{"url":"https://discord.com/api/webhooks/1551161573194731652/***","webhookId":"1551161573194731652","channelId":"1551161570439208960"},"support":{"url":"https://discord.com/api/webhooks/1552971101741654046/***","webhookId":"1552971101741654046","channelId":"1552971099317211136"},"frak":{"url":"https://discord.com/api/webhooks/1552971096847028264/***","webhookId":"1552971096847028264","channelId":"1552971094267527169"},"chopshop":{"url":"https://discord.com/api/webhooks/1552971074814218312/***","webhookId":"1552971074814218312","channelId":"1552971071882399744"},"esx_test":{"url":"https://discord.com/api/webhooks/1557386332483887194/***","webhookId":"1557386332483887194","channelId":"1557386329686413342"},"esx":{"url":"https://discord.com/api/webhooks/1557386326951592027/***","webhookId":"1557386326951592027","channelId":"1420103430562910370"},"txadmin":{"url":"https://discord.com/api/webhooks/1552989826213617715/***","webhookId":"1552989826213617715","channelId":"1552989823604756600"},"freecam_photo":{"url":"https://discord.com/api/webhooks/1551520132319412284/***","webhookId":"1551520132319412284","channelId":"1551520126367572008"},"troll":{"url":"https://discord.com/api/webhooks/1552971107500433498/***","webhookId":"1552971107500433498","channelId":"1552971103910236172"},"basicneeds":{"url":"https://discord.com/api/webhooks/1552971931869777932/***","webhookId":"1552971931869777932","channelId":"1417917687723724872"},"me":{"url":"https://discord.com/api/webhooks/1513950212480307490/***","webhookId":"1513950212480307490","channelId":"1513950191936344245"},"clothing_strip":{"url":"https://discord.com/api/webhooks/1551161592467423353/***","webhookId":"1551161592467423353","channelId":"1551161585614061618"},"adminjail":{"url":"https://discord.com/api/webhooks/1551161578009796630/***","webhookId":"1551161578009796630","channelId":"1551161575690211428"},"sperrzone":{"url":"https://discord.com/api/webhooks/1552971115209564220/***","webhookId":"1552971115209564220","channelId":"1552971110457286766"},"esx_chat":{"url":"https://discord.com/api/webhooks/1557386337580220497/***","webhookId":"1557386337580220497","channelId":"1557386335512305664"},"staff":{"url":"https://discord.com/api/webhooks/1552971123233394708/***","webhookId":"1552971123233394708","channelId":"1552971120460828763"},"bell":{"url":"https://discord.com/api/webhooks/1471556835994767400/***","webhookId":"1471556835994767400","channelId":"1471556817061544068"},"lager":{"url":"https://discord.com/api/webhooks/1551161582942158879/***","webhookId":"1551161582942158879","channelId":"1551161580324921455"},"esx_resources":{"url":"https://discord.com/api/webhooks/1557386349395583076/***","webhookId":"1557386349395583076","channelId":"1557386346782265425"},"hotdog":{"url":"https://discord.com/api/webhooks/1474547103081566412/***","webhookId":"1474547103081566412","channelId":"1474547082076622979"},"esx_paycheck":{"url":"https://discord.com/api/webhooks/1557386357381533816/***","webhookId":"1557386357381533816","channelId":"1557386352226598913"},"versicherung":{"url":"https://discord.com/api/webhooks/1457180941750632469/***","webhookId":"1457180941750632469","channelId":"1457180906816012401"},"willkommen":{"url":"https://discord.com/api/webhooks/1551161597853049005/***","webhookId":"1551161597853049005","channelId":"1551161595436990575"},"esx_useractions":{"url":"https://discord.com/api/webhooks/1557386342755991582/***","webhookId":"1557386342755991582","channelId":"1557386339866120252"},"afk":{"url":"https://discord.com/api/webhooks/1512475306554953789/***","webhookId":"1512475306554953789","channelId":"1512475286229356617"},"expose":{"url":"https://discord.com/api/webhooks/1551624352477225113/***","webhookId":"1551624352477225113","channelId":"1551624348660531240"},"einreise":{"url":"https://discord.com/api/webhooks/1552971088328392714/***","webhookId":"1552971088328392714","channelId":"1552971085937381431"},"esx_jobs":{"url":"https://discord.com/api/webhooks/1557386364578955274/***","webhookId":"1557386364578955274","channelId":"1557386361172918374"}},"updatedAt":"2026-10-08T13:23:39Z"}
```
