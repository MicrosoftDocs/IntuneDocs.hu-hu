---
title: A Microsoft Managed Home Screen alkalmazás konfigurálása
titleSuffix: Microsoft Intune
description: Ismerje meg, hogyan konfigurálhatja a Microsoft Managed Home Screen alkalmazást.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 865c7f03-f525-4dfa-b3a8-d088a9106502
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e97e88ad78e1b914543b7fa283f47863dce185fc
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813483"
---
# <a name="configure-the-microsoft-managed-home-screen-app-for-android-enterprise"></a>Az Android Enterprise rendszerhez készült Microsoft Managed Home Screen alkalmazás konfigurálása

A felügyelt kezdőképernyő a vállalat által birtokolt, az Intune-ban regisztrált és a többalkalmazásos kioszk módban futó, vállalati tulajdonú Android-eszközökhöz használt alkalmazás. Ezekhez az eszközökhöz a felügyelt kezdőképernyő indítóként működik más jóváhagyott alkalmazások futtatásához. A felügyelt kezdőképernyő lehetővé teszi a rendszergazdák számára az eszközök testreszabását és a végfelhasználók által elérhető képességek korlátozását. 

## <a name="when-to-configure-the-microsoft-managed-home-screen-app"></a>Mikor kell konfigurálni a Microsoft Managed Home Screen alkalmazást

Ha a beállítások az eszköz konfigurációjától függően érhetők el, konfigurálja a beállításokat. Ezzel időt takaríthat meg, és csökkentheti a hibákat, és jobb Intune-támogatási élményt nyújt. A felügyelt kezdőképernyő egyes beállításai azonban jelenleg csak az Intune-konzol alkalmazás- **konfigurációs házirendek** paneljén érhetők el. Ebből a dokumentumból megtudhatja, hogyan konfigurálhatja a különböző beállításokat a Configuration Designer vagy egy JSON-parancsfájl használatával. 

> [!NOTE]
> Jelenleg lehetőség van arra, hogy az engedélyezze a felsorolt alkalmazásokat és a rögzített webhivatkozásokat az **ügyfélalkalmazások** és az **eszközök konfigurációjával**. A felügyelt kezdőképernyő **eszköz konfigurációjában** elérhető beállítások teljes listáját a [dedikált eszközbeállítások](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings)című részben tekintheti meg.  

Először navigáljon Azure Portal Intune-konzolra, és válassza az **ügyfélalkalmazások** > **alkalmazás-konfigurációs szabályzatok**lehetőséget. Adja hozzá az **Android** rendszerű **felügyelt eszközökhöz** tartozó konfigurációs szabályzatot, és válassza a **felügyelt kezdőképernyő** lehetőséget a társított alkalmazásként. Kattintson a **konfigurációs beállítások** elemre a különböző elérhető felügyelt kezdőképernyő-beállítások konfigurálásához. 

## <a name="choosing-a-configuration-settings-format"></a>Konfigurációs beállítások formátumának kiválasztása

A felügyelt kezdőképernyő konfigurációs beállításainak definiálására két módszer használható:

- A **Configuration Designer** lehetővé teszi, hogy a beállításokat egy könnyen használható kezelőfelülettel konfigurálja, amely lehetővé teszi a szolgáltatások be-és kikapcsolását, valamint az értékek beállítását. Ebben a metódusban néhány letiltott konfigurációs kulcs van `BundleArray` típusú értékkel. Ezeket a konfigurációs kulcsokat csak a JSON-adatokat megadásával lehet konfigurálni. 
- A **JSON-adatai** lehetővé teszik az összes lehetséges konfigurációs kulcs megadását JSON-parancsfájl használatával. 

Ha a Configuration Designer használatával ad hozzá tulajdonságokat, automatikusan átalakíthatja ezeket a tulajdonságokat a JSON-ba a **konfigurációs beállítások formátuma** legördülő menüből a **JSON-adatok megadása** lehetőség kiválasztásával.

![Képernyőkép a konfigurációs beállítások formátumáról](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_01.png)

## <a name="using-configuration-designer"></a>A Configuration Designer használata

A Configuration Designer lehetővé teszi az előre megadott beállítások és a hozzájuk tartozó értékek kiválasztását. 

![Képernyőkép a hozzáadott konfigurációs beállításokról](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_02.png)

A következő táblázat felsorolja a felügyelt kezdőképernyő elérhető konfigurációs kulcsait, az értékek típusát, az alapértelmezett értékeket és a leírásokat. A leírás a kiválasztott értékek alapján biztosítja a várt eszköz viselkedését. A Configuration Designerben letiltott konfigurációs kulcsok nem szerepelnek a táblázatban.

| Konfigurációs kulcs | Érték típusa | Alapértelmezett érték | Description |
|---------------------------------------------------------------------------------------------------------------------------|-------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Rácsvonal méretének beállítása | sztring | Automatikus | Lehetővé teszi az alkalmazások rácsos méretének beállítását a felügyelt kezdőképernyőn. Megadhatja az alkalmazás sorainak és oszlopainak számát a rács méretének meghatározásához a következő formátumban: `columns;rows`. Ha a rács méretét határozza meg, a kezdőképernyő egy sorában megjelenő alkalmazások maximális száma lesz a beállított sorok száma, és a kezdőképernyő egyik oszlopában megjelenő alkalmazások maximális száma a beállított oszlopok száma. |
| Értesítések engedélyezése jelvény | bool | HAMIS | Engedélyezi az alkalmazás ikonjainak értesítési jelvényét, amely az alkalmazás új értesítéseinek számát jeleníti meg. Ha engedélyezi ezt a beállítást, a végfelhasználók értesítési jelvényeket fognak látni azokon az alkalmazásokon, amelyek olvasatlan értesítésekkel rendelkeznek. Ha megtartja ezt a konfigurációs kulcsot, a végfelhasználó nem fogja látni az olyan alkalmazásokhoz tartozó értesítéseket, amelyek nem tartalmazhatnak olvasatlan értesítéseket. |
| Kezdőképernyő zárolása | bool | IGAZ | Megszünteti a végfelhasználók számára az alkalmazás ikonjainak áthelyezését a kezdőképernyőn. Ha engedélyezi ezt a konfigurációs kulcsot, a rendszer zárolja az alkalmazás ikonját a kezdőképernyőn, és a végfelhasználó nem fogja tudni áthúzni a kezdőképernyő különböző rácsvonalait. Ha `false` értékre vált, a végfelhasználók az alkalmazás és a Webhivatkozás ikonjait a felügyelt kezdőképernyőn helyezhetik át.  |
| Az eszköz falra vonatkozó papírjának beállítása | sztring | Alapértelmezett | Lehetővé teszi, hogy tetszőleges háttérképet állítson be a háttérképként beállítani kívánt rendszerkép URL-címének megadásával. |
| Alkalmazás ikonjának méretének beállítása | integer | 2 | Ezzel a beállítással beállíthatja a kezdőképernyőn megjelenő alkalmazások ikonjának méretét. A konfigurációban a következő értékeket adhatja meg különböző méreteknél – 0 (legkisebb), 1 (kis), 2 (normál), 3 (nagy) és 4 (legnagyobb). |
| Az alkalmazás mappájának beállítása ikon | integer | 0 | Lehetővé teszi az alkalmazás-mappák megjelenésének megadását a kezdőképernyőn. Kiválaszthatja a következő értékek megjelenését: Dark Square (0);   Sötét kör (1); Light Square (2); Világos kör (3). |
| Képernyő tájolásának beállítása | integer | 1 | Lehetővé teszi, hogy beállítsa a kezdőképernyő tájolását álló módba, fekvő módba vagy automatikus elforgatást engedélyezzen. A tájolást beállíthatja úgy, hogy az 1 (álló mód), a 2 (fekvő mód), a 3 (az autoforgatás) értéket írja be. |
| Eszköz telemetria engedélyezése | bool | HAMIS | Engedélyezi a felügyelt kezdőképernyő számára rögzített összes telemetria. Ha engedélyezi ezt a lehetőséget, a Microsoft képes lesz rögzíteni az eszköz használati telemetria, például egy adott alkalmazás indításának számát az adott eszközön. |
| Engedélyezett alkalmazások beállítása | bundleArray | HAMIS | Lehetővé teszi a kezdőképernyőn látható alkalmazások készletének megadását az eszközön telepített alkalmazások közül. Megadhatja az alkalmazásokat a láthatóvá tenni kívánt alkalmazások alkalmazáscsomag-nevének megadásával, például a com. microsoft. emmx a kezdőképernyőn elérhetővé tenné a beállításokat. Az engedélyezett alkalmazások listája már telepítve van az eszközön, hogy láthatóvá váljon a kezdőképernyőn. |
| Rögzített webes hivatkozások beállítása | bundleArray | HAMIS | Lehetővé teszi a webhelyek gyors indítási ikonként való rögzítését a kezdőképernyőn. Ezzel a konfigurációval megadhatja az URL-címet, és hozzáadhatja azt a kezdőképernyőn, hogy a végfelhasználó egyetlen koppintással induljon el a böngészőben. |
| Képernyőkímélő engedélyezése | bool | HAMIS | A képernyővédő mód engedélyezése vagy nem. Ha igaz értékre van állítva, konfigurálhatja a **screen_saver_image**, a **screen_saver_show_time**, a **inactive_time_to_show_screen_saver**és a **media_detect_screen_saver**. |
| Képernyőkímélő képe | sztring |   | Állítsa be a képernyőkímélő rendszerképének URL-címét. Ha nincs beállítva URL-cím, az eszközök megjelenítik az alapértelmezett képernyőkímélő rendszerképet, amikor a képernyővédő aktiválva van. Az alapértelmezett képen a felügyelt kezdőképernyő alkalmazás ikon látható.  |
| Képernyőkímélő időpontjának megjelenítése | integer | 0 | Megadja azt az időtartamot másodpercben, ameddig az eszköz megjelenítheti a képernyővédőt a képernyővédő módban. Ha a 0 értékre van állítva, a képernyőkímélő határozatlan időre megjelenhet a képernyőkímélőben, amíg az eszköz nem aktiválódik.  |
| A képernyőkímélő engedélyezésének inaktív ideje | integer | 30 | Azon másodpercek száma, ameddig az eszköz inaktív a képernyőkímélő elindítása előtt. Ha a 0 értékre van állítva, az eszköz soha nem fog bekerülni a képernyővédő módba. |
| Adathordozó észlelése a képernyővédő megjelenítése előtt | bool | IGAZ | Válassza ki, hogy az eszköz képernyőjén megjelenjen-e a képernyőkímélő, ha a hang/videó lejátszása az eszközön történik. Ha az értéke TRUE (igaz), az eszköz nem játssza le a hang-és video-értékeket, a **inactive_time_to_show_scree_saver**értéktől függetlenül. Ha false (hamis) értékre van állítva, az eszköz képernyője a **inactive_time_to_show_screen_saver**-ben beállított érték szerint jeleníti meg a képernyővédőt.   |
| Virtuális otthoni gomb engedélyezése | bool | HAMIS | Ha ezt a beállítást `True` értékre állítja, akkor a végfelhasználó hozzáférhet a felügyelt kezdőképernyő Kezdőlap gombhoz, amely a felhasználót az aktuális feladatból a Managed Home (felügyelt kezdőképernyő) képernyőre fogja visszaadni.  |
| A virtuális otthoni gomb típusa | sztring | swipe_up | A **swipe_up** használatával érheti el a Kezdőlap gombot egy felugró kézmozdulattal. Az **úszó** használatával elérheti a végfelhasználó által a képernyőn áthelyezhető ragacsos, állandó Kezdőlap gombot. |
| Akkumulátor-és jelerősség jelző sáv | bool | Igaz  | Ha ezt a beállítást `True` értékre állítja, megjelenik az akkumulátor és a jel erősségének mutató sáv. |
| Zárja be a zárolási feladat üzemmódjának jelszavát | sztring |   | A hibaelhárításhoz adjon meg egy 4-6 számjegyű kódot, amellyel átmenetileg kiléphet a zárolási feladat módból. |
| Wi-Fi-beállítás megjelenítése | bool | HAMIS | Ha ezt a beállítást `True` értékre állítja, a végfelhasználó be-vagy kikapcsolhatja a Wi-Fi-t, vagy csatlakozhat a különböző Wi-Fi-hálózatokhoz.  |
| Bluetooth-beállítás megjelenítése | bool | HAMIS | Ha ezt a beállítást `True` értékre állítja, a végfelhasználó be-és kikapcsolhatja a Bluetooth-t, és csatlakozhat a különböző Bluetooth-kompatibilis eszközökhöz.   |
| A mappában lévő alkalmazások a név szerint vannak rendezve | bool | IGAZ | Ha ezt a beállítást `False` értékre állítja, lehetővé teszi, hogy a mappában lévő elemek a megadott sorrendben jelenjenek meg. Ellenkező esetben a mappában betűrendben fog megjelenni.   |
| Alkalmazás-megrendelés engedélyezve | bool | HAMIS | Ha ezt a beállítást `True` értékre állítja, lehetővé teszi az alkalmazások, webhivatkozások és mappák sorrendjét a felügyelt kezdőképernyőn. Ha engedélyezve van, állítsa be a rendelést a **app_order**. a végfelhasználó be-és kikapcsolhatja a Bluetooth-t, és csatlakozhat a különböző Bluetooth-kompatibilis eszközökhöz.   |
| Alkalmazás sorrendje | bundleArray | HAMIS | Lehetővé teszi az alkalmazások, webhivatkozások és mappák sorrendjének megadását a felügyelt kezdőképernyőn. Ennek a beállításnak a használatához engedélyezni kell a **kezdőképernyő zárolását** , meg kell adni a **rácsvonal méretének** meghatározását, és az **alkalmazás-rendelés engedélyezését** `True` értékre kell állítani.   |

## <a name="enter-json-data"></a>JSON-adatbevitel

Adja meg a JSON-beállításokat a felügyelt kezdőképernyő összes elérhető beállításának, valamint a **Configuration Designerben**letiltott beállítások megadásához.

![A JSON-adatmennyiség képernyőképe](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_03.png)

A **Configuration Designer** táblában (fent) található konfigurálható beállítások listáján kívül az alábbi táblázat azokat a konfigurációs kulcsokat tartalmazza, amelyeket csak JSON-adatokkal lehet konfigurálni.

|    Konfigurációs kulcs    |    Érték típusa    |    Alapértelmezett érték    |    Description    |
|-------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Engedélyezett alkalmazások beállítása    |    bundleArray    | <img alt="JSON - Example 1" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson01.png" width="300"> |    Lehetővé teszi a kezdőképernyőn látható alkalmazások készletének megadását az eszközön telepített alkalmazások közül. Megadhatja az alkalmazásokat a láthatóvá tenni kívánt alkalmazások alkalmazáscsomag-nevének megadásával, például: com. Android. a beállítások a kezdőképernyőn elérhetővé tehetik a beállításokat. Az engedélyezett alkalmazások listája már telepítve van az eszközön, hogy láthatóvá váljon a kezdőképernyőn.    |
|    Rögzített webes hivatkozások beállítása    |    bundleArray    | <img alt="JSON - Example 2" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson02.png" width="300"> |    Lehetővé teszi a webhelyek gyors indítási ikonként való rögzítését a kezdőképernyőn. Ezzel a konfigurációval megadhatja az URL-címet, és hozzáadhatja azt a kezdőképernyőn, hogy a végfelhasználó egyetlen koppintással induljon el a böngészőben.    |
|    Felügyelt mappa létrehozása az alkalmazások csoportosításához    |    bundleArray    | <img alt="JSON - Example 3" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson03.png" width="300"> |    Lehetővé teszi mappák és alkalmazások létrehozását és elnevezését ezeken a mappákon belül. A végfelhasználók nem helyezhetik át a mappákat, átnevezhetik a mappákat, vagy áthelyezhetik az alkalmazásokat a mappákon belül.   A mappák a létrehozásuk sorrendjében jelennek meg, a mappákban lévő alkalmazások pedig betűrendben jelennek meg.         Megjegyzés: a mappákba csoportosítani kívánt összes alkalmazást hozzá kell rendelni az eszközhöz, és hozzá kell adni őket a felügyelt kezdőképernyő.     |

A következő példa egy JSON-szkriptet tartalmaz, amely tartalmazza az összes elérhető konfigurációs kulcsot:

```json
{
    "kind": "androidenterprise#managedConfiguration",
    "productId": "com.microsoft.launcher.enterprise",
    "managedProperty": [
        {
            "key": "lock_home_screen",
            "valueBool": true
        },
        {
            "key": "wallpaper",
            "valueString": "default"
        },
        {
            "key": "icon_size",
            "valueInteger": 2
        },
        {
            "key": "app_folder_icon",
            "valueInteger": 0
        },
        {
            "key": "screen_orientation",
            "valueInteger": 1
        },
        {
            "key": "enable_telemetry",
            "valueBool": false
        },
        {
            "key": "applications",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": “app package name here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "weblinks",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "link",
                            "valueString": “link here”
                        },
                        {
                            "key": "label",
                            "valueString": “weblink label here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "show_virtual_home",
            "valueBool": false
        },
        {
            "key": "virtual_home_type",
            "valueString": "swipe_up"
        },
        {
            "key": "show_virtual_status_bar",
            "valueBool": true
        },
        {
            "key": "exit_lock_task_mode_code",
            "valueString": ""
        },
        {
            "key": "show_wifi_setting",
            "valueBool": false
        },
        {
            "key": "show_bluetooth_setting",
            "valueBool": false
        },
        {
            "key": "grid_size",
            "valueString": "4;5"
        },
        {
            "key": "app_order_enabled",
            "valueBool": true
        },
        {
            "key": "apps_in_folder_ordered_by_name",
            "valueBool": true
        },
        {
            "key": "app_orders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.Microsoft.emmx"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 1
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Work"
                        },
                        {
                            "key": "type",
                            "valueString": "managed_folder"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 2
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.microsoft.launcher.enterprise"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "class",
                            "valueString": "com.microsoft.launcher.launcher"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 3
                        }
                    ]
                }
            ]
        },
        {
            "key": "managed_folders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Folder name here"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.emmx"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.bing"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "link",
                                            "valueString": "https://microsoft.com/"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Example folder name 2"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.office.word"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    ]
}
```

## <a name="googles-android-device-policy-app"></a>Google Android-eszköz házirend-alkalmazás
A felügyelt kezdőképernyő alkalmazás mostantól hozzáférést biztosít a Google androidos eszköz házirend-alkalmazásához. A felügyelt kezdőképernyő alkalmazás egy egyéni indító, amelyet az Intune-ban regisztrált eszközökhöz az Android Enterprise (AE) dedikált eszközként használnak többalkalmazásos kioszk mód használatával. Elérheti az Android-eszköz házirend-alkalmazását, vagy megtekintheti a felhasználókat az Android-eszközök házirend-alkalmazásához, támogatási és hibakeresési célból. Ez az indítási képesség akkor érhető el, amikor az eszköz regisztrálja és zárolja a felügyelt kezdőképernyőn. A funkció használatához nincs szükség további telepítésekre.

## <a name="managed-home-screen-debug-screen"></a>Felügyelt kezdőképernyő hibakeresési képernyője
A felügyelt kezdőképernyő hibakeresési képernyőjét a **vissza** gombra kattintva érheti el, amíg meg nem jelenik a hibakeresési képernyő (kattintson a **vissza** gombra 15 vagy több alkalommal). Ebből a hibakeresési képernyőből elindíthatja az Android-eszköz házirend-alkalmazását, naplókat tekinthet meg és tölthet fel, vagy ideiglenesen szüneteltetheti a kioszk módot az eszköz frissítéséhez. A kioszk mód felfüggesztésével kapcsolatos további információkért tekintse meg a **kioszk mód kihagyása** az Android Enterprise [dedikált eszköz beállításaiban](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings)című témakört.

## <a name="next-steps"></a>További lépések

- További információ az Android Enterprise dedikált eszközökről: [az androidos vállalati dedikált eszközök Intune-regisztrációjának beállítása](../enrollment/android-kiosk-enroll.md).