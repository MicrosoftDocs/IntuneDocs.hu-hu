---
title: Intune-adattárházgyűjtemények
titlesuffix: Microsoft Intune
description: Az Intune adattárház-gyűjteményekkel a Data Warehouse API-val kapcsolatos adatokat lehet megszerezni.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/04/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 29f09230-dc56-43db-b599-d961967bda49
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune
ms.openlocfilehash: 4df55309587ac079cfeaec299d70635b090e300b
ms.sourcegitcommit: 443b4cb3390da47bf1e497b1f0c0137a5ddda7bd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43821631"
---
#  <a name="intune-data-warehouse-collections"></a>Intune adattárház-gyűjtemények

Az alábbi Intune adattárház-gyűjteményekkel a Data Warehouse API 1.0-ás verziójú gyűjteményeihez kínálnak tulajdonságokat, leírásokat és példákat. 

## <a name="apprevisions"></a>appRevisions
Az **AppRevision** entitás listázza az alkalmazások összes verzióját.

|          Tulajdonság          |                                      Description                                      |                Példa               |
|:--------------------------:|:-------------------------------------------------------------------------------------:|:------------------------------------:|
| AppKey                     | Az alkalmazás egyedi azonosítója.                                                         | 123                                  |
| ApplicationId              | Az alkalmazás egyedi azonosítója – Az AppKey-hez hasonlít, de természetes kulcs.        | b66bc706-ffff-7437-0340-032819502773 |
| Változat                   | A bináris feltöltése során a rendszergazda által említett verzió.                   | 2                                    |
| Cím                      | Az alkalmazás címe.                                                                     | Excel                                |
| Kiadó                  | Az alkalmazás kiadója.                                                                 | Microsoft                            |
| UploadState                | Az alkalmazás feltöltésének állapota.                                                              | 1                                    |
| AppTypeKey                 | A következő szakaszban leírt AppType érték hivatkozása.                            | 1                                    |
| VppProgramTypeKey          | A következő szakaszban leírt VppProgramType érték hivatkozása.                                        | 30876                                |
| CreationTime               | A jelen változat létrehozásának ideje.                                            | 2016. 11. 23. 0:00                      |
| ModifiedTime               | A legutóbbi, jelen változattal kapcsolatos bármilyen módosítás ideje.                            | 2016. 11. 23. 0:00                      |
| Méret                       | A bináris mérete bájtokban.                                                          | 120.392.000                          |
| StartDateInclusiveUTC      | A jelen változat adattárházban történő létrehozásának dátuma és időpontja (UTC).      | 2016. 11. 23. 0:00                      |
| EndDateExclusiveUTC        | A jelen változat elavulásának dátuma és időpontja (UTC).                        | 2016. 11. 23. 0:00                      |
| IsCurrent                  | Jelzi, hogy az alkalmazásverzió aktuális-e az adattárházban.         | Igaz/hamis                           |
| RowLastModifiedDateTimeUTC | Az alkalmazásverzió legutóbbi módosításának dátuma és időpontja (UTC) az adattárházban. | 2016. 11. 23. 0:00                      |

## <a name="apptypes"></a>appTypes
Az **appType** entitás az alkalmazás telepítési forrásait listázza.

|   Tulajdonság  |        Description        |
|:-----------:|:-------------------------:|
| AppTypeID   | A típus azonosítója           |
| AppTypeKey  | A kulcs helyettes kulcsa |
| AppTypeName | Alkalmazás típusa                  |

### <a name="example"></a>Példa

| AppTypeID |                Név               |                     Description                     |
|:---------:|:---------------------------------:|:---------------------------------------------------:|
| 0         | Android store app               | Android Áruházbeli alkalmazás.                             |
| 1         | Android   LOB app                 | Üzletági Android-alkalmazás.                  |
| 2         | Managed   Android store app (MAM) | Android Áruházbeli alkalmazás, amelyen engedélyezve van a felügyelet. |
| 3         | iOS   store app                   | iOS Store-alkalmazás.                                 |
| 4         | iOS   LOB app                     | Üzletági iOS-alkalmazás.                      |
| 5         | Managed   iOS store app (MAM)     | iOS-alkalmazás, amelyen engedélyezve van a felügyelet.       |
| 6         | O365   Pro Plus Suite             | A Windows 10-hez készült Office 365 Pro Plus Csomag.     |
| 7         | Webalkalmazás                         | Webes alkalmazás.                                        |
| 8         | Windows   Phone 8.1 store app     | Windows Phone 8.1-es Áruházbeli alkalmazás.                    |
| 9         | Windows   store app               | Windows Áruházbeli alkalmazás.                              |
| 10        | Windows   LOB apps                | AppX-alapú üzletági Windows-alkalmazás.              |
| 11        | Windows   Mobile MSI              | MSI-alapú üzletági alkalmazás.                      |
| 12        | Windows   Phone LOB app           | Üzletági Windows Phone-alkalmazás.             |

## <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities
Az alábbi táblázatban foglaltuk össze az eszközökhöz rendelt megfelelőségi szabályzatok hozzárendelési állapotát. A lista felsorolja az egyes megfelelőségi állapotokban található eszközök számát is.

|    Tulajdonság   |                                                                                      Description                                                                                     |  Példa |
|:-------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey       | A megfelelőségi szabályzat összefoglalójának létrehozási dátumkulcsa.                                                                                                                   | 20161204 |
| Ismeretlen       | Azoknak az eszközöknek a száma, amelyek offline állapotban vannak, vagy valamilyen más okból nem sikerült kapcsolatba lépniük az Intune-nal vagy az Azure AD-vel.                                                                           | 5        |
| Nem alkalmazható | Azoknak az eszközöknek a száma, amelyeknél a rendszergazda által meghatározott eszközmegfelelőségi szabályzatok nem alkalmazhatók.                                                                                     | 201      |
| Compliant (Megfelelő)     | Azoknak az eszközöknek a száma, amelyek megfelelnek a rendszergazda által meghatározott egy vagy több eszközmegfelelőségi szabályzatnak.                                                                        | 4083     |
| Türelmi időszakban | Azoknak az eszközöknek a száma, amelyek nem megfelelőek, de a rendszergazda által meghatározott türelmi időszakban vannak.                                                                                  | 57       |
| Nem megfelelő  | Azoknak az eszköznek a száma, amelyek nem felelnek meg a rendszergazda által meghatározott egy vagy több eszközmegfelelőségi szabályzatnak, vagy a felhasználó nem a rendszergazda által meghatározott szabályzatoknak megfelelően járt el. | 43       |
|    Hiba      |    Azoknak az eszközöknek a száma, amelyeknek nem sikerült kapcsolatba lépniük az Intune-nal vagy az Azure AD-vel, és hibaüzenetet küldtek.                                                                          |    3     |

## <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities
Az alábbi táblázatban foglaltuk össze az eszközökhöz rendelt megfelelőségi szabályzatok hozzárendelési állapotát szabályzatonként és szabályzattípusonként. A lista szabályzatonként felsorolja az egyes megfelelőségi állapotokban található eszközök számát.

|      Tulajdonság     |                                                                                      Description                                                                                     |  Példa |
|:-----------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey           | A megfelelőségi szabályzat összefoglalójának létrehozási dátumkulcsa.                                                                                                                   | 20161219 |
| PolicyKey         | Annak a megfelelőségi szabályzatnak a kulcsa, amelyhez az összefoglalás készült.                                                                                                                   | 10178    |
| PolicyPlatformKey | Annak a megfelelőségi szabályzathoz tartozó platformnak a kulcsa, amelyhez az összefoglalás készült.                                                                                            | 5        |
| Ismeretlen           | Azoknak az eszközöknek a száma, amelyek offline állapotban vannak, vagy valamilyen más okból nem sikerült kapcsolatba lépniük az Intune-nal vagy az Azure AD-vel.                                                                           | 13       |
| Nem alkalmazható     | Azoknak az eszközöknek a száma, amelyeknél a rendszergazda által meghatározott eszközmegfelelőségi szabályzatok nem alkalmazhatók.                                                                                     | 3        |
| Compliant (Megfelelő)         | Azoknak az eszközöknek a száma, amelyek megfelelnek a rendszergazda által meghatározott egy vagy több eszközmegfelelőségi szabályzatnak.                                                                        | 45       |
| Türelmi időszakban     | Azoknak az eszközöknek a száma, amelyek nem megfelelőek, de a rendszergazda által meghatározott türelmi időszakban vannak.                                                                                  | 3        |
| Nem megfelelő      | Azoknak az eszköznek a száma, amelyek nem felelnek meg a rendszergazda által meghatározott egy vagy több eszközmegfelelőségi szabályzatnak, vagy a felhasználó nem a rendszergazda által meghatározott szabályzatoknak megfelelően járt el. | 7        |
| Hiba             | Azoknak az eszközöknek a száma, amelyeknek nem sikerült kapcsolatba lépniük az Intune-nal vagy az Azure AD-vel, és hibaüzenetet küldtek.                                                                             | 3        |
## <a name="compliancestates"></a>complianceStates

|      Tulajdonság      |                       Description                      |
|:------------------:|:------------------------------------------------------:|
| complianceStatus   | Az mdmStatusKey kulcsot használó eszközök megfelelőségi állapota       |
| complianceStateKey | Az eszköz és a megfelelőségi állapot megfeleltetéséhez használt megfelelőségi kulcs |
| complianceStateID  | Azonosító ennek a megfelelőségi állapotnak a megfeleltetéséhez                |

### <a name="example"></a>Példa

|  complianceStatus  |                       Description                      |
|:------------------:|:------------------------------------------------------:|
|    Ismeretlen         |    Ismeretlen.                                                                        |
|    Compliant (Megfelelő)       |    Compliant (Megfelelő).                                                                      |
|    Noncompliant (Nem megfelelő)    |       Az eszköz nem megfelelő, és le van tiltva a vállalati erőforrásoknál.             |
|    Ütközés        |    Ütközés más szabályokkal.                                                      |
|    Hiba           |       HIba.                                                                       |
|    ConfigManager   |    A Config Manager kezeli.                                                      |
|    Türelmi időszakban   |       Az eszköz nem megfelelő, de hozzáfér a vállalati erőforrásokhoz          |

## <a name="dates"></a>dátumok
A **date** entitás olyan dátumokat jelöl, amelyekre több adattárház-entitás is hivatkozik.

|     Tulajdonság    |                       Description                      |    Példa    |
|:---------------:|:------------------------------------------------------:|:-------------:|
| DateKey         | A dátum egyedi azonosítója az adattárházban. | 20160703      |
| FullDate        | Az adott dátum teljes dátum/idő formátumban kifejezve.        | 2016. 7. 3. 0:00 |
| DayOfWeek       | A hét hányadik napja                                            | 1             |
| DayOfMonth      | A hónap hányadik napja                                           | 3             |
| DayOfYear       | Az év hányadik napja                                            | 185           |
| WeekOfYear      | Az év hányadik hete                                           | 28            |
| MonthOfYear     | Az év hányadik hónapja                                      | 7             |
| CalendarQuarter | Naptári negyedév                                       | 3             |
| CalendarYear    | Naptári év                                          | 2016          |
| DateKey         | A dátum egyedi azonosítója az adattárházban. | 20160703      |
| FullDate        | Az adott dátum teljes dátum/idő formátumban kifejezve.        | 2016. 7. 3. 0:00 |
| DayOfWeek       | A hét hányadik napja                                            | 1             |
| DayOfMonth      | A hónap hányadik napja                                           | 3             |
| DayOfYear       | Az év hányadik napja                                            | 185           |
| WeekOfYear      | Az év hányadik hete                                           | 28            |
| MonthOfYear     | Az év hányadik hónapja                                      | 7             |
| CalendarQuarter | Naptári negyedév                                       | 3             |
| CalendarYear    | Naptári év                                          | 2016          |

## <a name="devicecategories"></a>deviceCategories

|      Tulajdonság      |                                    Description                                   |                Példa               |
|:------------------:|:--------------------------------------------------------------------------------:|:------------------------------------:|
| deviceCategoryID   | Egyedi azonosító az eszközkategóriához.                                       | fb415ba2-7c08-41f6-a5e5-685b50da2c4c |
| deviceCategoryKey  | Az eszközkategória egyedi azonosítója az adattárházban – helyettes kulcs | 1                                    |
| deviceCategoryName | Az eszközkategória megjelenített neve.                                            | Smartphones                          |

## <a name="deviceconfigurationprofiledeviceactivities"></a>deviceConfigurationProfileDeviceActivities
A **DeviceConfigurationProfileDeviceActivity** entitás a napi sikeres, függő, sikertelen vagy hibás állapotú eszközök számát sorolja fel. A szám az entitáshoz rendelt eszközkonfigurációs profilokat jelöli. Ha például az adott eszköz valamennyi hozzárendelt szabályzata tekintetében sikeres állapotú, akkor az entitás azon a napon eggyel növeli az értéket a sikeres állapotot jelző számlálón. Ha az adott eszköz két hozzárendelt profillal rendelkezik, amelyek közül az egyik sikeres, míg a másik hibás állapotú, akkor az entitás növeli az értéket a sikeres állapotot jelző számlálón, és hibás állapotba helyezi az eszközt. Az entitás azt sorolja fel, hogy hány eszköz van az egyes állapotokban az elmúlt 30 napon belüli adott napon.

|  Tulajdonság |                                          Description                                          |  Példa |
|:---------:|:---------------------------------------------------------------------------------------------:|:--------:|
| DateKey   | A dátumkulcs azt jelzi, hogy az adattárházban mikor lett rögzítve az eszközkonfigurációs profil bejelentkezése. | 20160703 |
| Függőben   | A függő állapotú egyedi eszközök száma.                                                    | 123      |
| Sikerült | A sikeres állapotú egyedi eszközök száma.                                                    | 12       |
| Hiba     | A hibás állapotú egyedi eszközök száma.                                                      | 10       |
| Sikertelen    | A sikertelen állapotú egyedi eszközök száma.                                                     | 2        |

## <a name="deviceconfigurationprofileuseractivities"></a>deviceConfigurationProfileUserActivities 
A  **DeviceConfigurationProfileUserActivity** entitás a napi sikeres, függő, sikertelen vagy hibás állapotú felhasználók számát sorolja fel. A szám az entitáshoz rendelt eszközkonfigurációs profilokat jelöli. Ha például az egyik felhasználó valamennyi hozzárendelt szabályzata tekintetében sikeres állapotú, akkor az entitás azon a napon eggyel növeli az értéket a sikeres állapotot jelző számlálón. Ha az adott felhasználó két hozzárendelt profillal rendelkezik, amelyek közül az egyik sikeres, míg a másik hibás állapotú, akkor a felhasználót hibás állapotúnak számítjuk. A  **DeviceConfigurationProfileUserActivity** entitás azt sorolja fel, hogy hány felhasználó van az egyes állapotokban az elmúlt 30 napon belüli adott napon. 

| Tulajdonság  | Description  | Példa  |
|------------|----------------------------------------------------------------------------------------------|-----------|
| DateKey  | A dátumkulcs azt jelzi, hogy az adattárházban mikor lett rögzítve az eszközkonfigurációs profil bejelentkezése.  | 20160703  |
| Függőben  | A függő állapotú egyedi felhasználók száma.  | 123  |
| Sikerült  | A sikeres állapotú egyedi felhasználók száma.  | 12  |
| Hiba  | A hibás állapotú egyedi felhasználók száma.  | 10  |
| Sikertelen  | A sikertelen állapotú egyedi felhasználók száma.  | 2  |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

|          Tulajdonság          |                                                                                      Description                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DateKey                    | A napot megadó dátumtáblázat-hivatkozás.                                                                                                                                          |
| DeviceKey                  | Az eszköz egyedi azonosítója az adattárházban – helyettes kulcs. Az Intune-eszközazonosítót tartalmazó eszköztáblára mutató hivatkozás.                               |
| DeviceName                 | Az eszköz neve az eszközök elnevezését megengedő platformokon. Más platformokon az Intune hoz létre nevet más tulajdonságok alapján. Ez az attribútum nem lehet elérhető az összes eszköz számára. |
| DeviceRegistrationStateKey | Az eszközhöz tartozó eszközregisztrációs állapot attribútum kulcsa.                                                                                                                    |
| OwnerTypeKey               | Az eszközhöz tartozó tulajdonostípus attribútum kulcsa: corporate (vállalati), personal (személyes), vagy unknown (ismeretlen).                                                                                                  |
| ManagementStateKey         | Az eszközhöz társított kezelési állapot, beleértve a távoli műveletek utolsó állapotát, és hogy az eszköz jailbreakelt vagy rootolt-e.                                                |
| AzureADRegistered          | Regisztrálva van-e az eszköz az Azure Active Directoryban.                                                                                                                             |
| ComplianceStateKey         | Kulcs a ComplianceState-hez.                                                                                                                                                            |
| OSVersion                  | Operációs rendszer verziója.                                                                                                                                                                          |
| JailBroken                 | Az, hogy az eszköz jailbreakelve vagy rootolva van-e.                                                                                                                                         |
| DeviceCategoryKey          | Az eszközhöz tartozó eszközkategória attribútum kulcsa.                                                                                                                                    |
## <a name="deviceregistrationstates"></a>deviceRegistrationStates
A **DeviceRegistrationState** entitás az adattárház más gyűjteményei által hivatkozott regisztrációtípust jelöli. 

|           Tulajdonság          |                                     Description                                     |
|:---------------------------:|:-----------------------------------------------------------------------------------:|
| deviceRegistrationStateID   | Regisztrációs állapot egyedi azonosítója                                            |
| deviceRegistrationStateKey  | A regisztrációs állapot egyedi azonosítója az adattárházban – helyettes kulcs |
| deviceRegistrationStateName | Regisztráció állapota                                                                  |
|    NotRegistered                     |    Nincs regisztrálva                                                                                                                                                                  |
|    Regisztrálva                        |       Regisztrálva                                                                                                                                                                   |
|    Revoked                           |       Ez az állapot azt jelzi, hogy a rendszergazda letiltotta az ügyfelet, és az ügyfél tiltása feloldható. Egy eszköz a törlését vagy kivonását követően is Revoked (visszavonva) állapotban lehet.        |
|    KeyConflict                       |    Kulcs ütközés                                                                                                                                                                    |
|    ApprovalPending                   |    Jóváhagyás függőben                                                                                                                                                                |
|    CertificateReset                  |    Tanúsítvány alaphelyzetbe állítása                                                                                                                                                               |
|    NotRegisteredPendingEnrollment    |    Nincs regisztrálva, regisztráció folyamatban                                                                                                                                               |
|    Ismeretlen                           |    Ismeretlen állapot                                                                                                                                                                   |

## <a name="devices"></a>eszközök
A **device** entitás felsorolja az összes kezelt regisztrált eszközt és azok lényeges tulajdonságait.

|          Tulajdonság          |                                                                                       Description                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DeviceKey                  | Az eszköz egyedi azonosítója az adattárházban – helyettes kulcs.                                                                                                               |
| DeviceId                   | Az eszköz egyedi azonosítója.                                                                                                                                                     |
| DeviceName                 | Az eszköz neve az eszközök elnevezését megengedő platformokon. Más platformokon az Intune más tulajdonságok alapján hoz létre nevet. Ez az attribútum nem lehet elérhető az összes eszköz számára. |
| DeviceTypeKey              | Az eszközhöz tartozó eszköztípus attribútum kulcsa.                                                                                                                                    |
| DeviceRegistrationState    | Az eszközhöz tartozó ügyfél-regisztrációs állapot attribútum kulcsa.                                                                                                                      |
| OwnerTypeKey               | Az eszközhöz tartozó tulajdonostípus attribútum (corporate, personal, vagy unknown) kulcsa.                                                                                                    |
| EnrolledDateTime           | Az eszköz regisztrálásának dátuma és időpontja.                                                                                                                                         |
| LastSyncDateTime           | Az eszköz utolsó Intune-bejelentkezése.                                                                                                                                              |
| ManagementAgentKey         | Az eszközhöz társított kezelőügynök kulcsa.                                                                                                                             |
| ManagementStateKey         | Az eszközhöz társított kezelési állapot, beleértve a távoli műveletek utolsó állapotát, és hogy az eszköz jailbreakelt vagy rootolt-e.                                                |
| AzureADDeviceId            | Az Azure-eszközazonosító ehhez az eszközhöz.                                                                                                                                                  |
| AzureADRegistered          | Regisztrálva van-e az eszköz az Azure Active Directoryban.                                                                                                                             |
| DeviceCategoryKey          | Az eszközhöz társított kategória kulcsa.                                                                                                                                     |
| DeviceEnrollmentType       | Az eszközhöz társított, a regisztráció módját jelző regisztrációtípus kulcsa.                                                                                             |
| ComplianceStateKey         | Az eszközhöz társított megfelelőségi állapot kulcsa.                                                                                                                             |
| OSVersion                  | Az eszközön futó operációs rendszer verziószáma.                                                                                                                                                |
| EasDeviceId                | Az eszköz Exchange ActiveSync-azonosítója.                                                                                                                                                  |
| Sorozatszám               | Sorozatszám                                                                                                                                                                           |
| UserId                     | Az eszközhöz társított felhasználó egyedi azonosítója.                                                                                                                           |
| RowLastModifiedDateTimeUTC | Az eszköz adattárházban történő utolsó módosításának dátuma és időpontja (UTC).                                                                                                       |
| Gyártó               | Az eszköz gyártója                                                                                                                                                             |
| Modell                      | Az eszköz típusa                                                                                                                                                                    |
| OperatingSystem            | Az eszközön futó operációs rendszer. Windows, iOS stb.                                                                                                                                   |
| IsDeleted                  | Bináris érték, amely azt jelzi, hogy az eszköz törölve van vagy sem.                                                                                                                                 |
| AndroidSecurityPatchLevel  | Az Android biztonsági javítási szintje                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| isSupervised               | Az eszköz felügyeleti állapota                                                                                                                                                               |
| FreeStorageSpaceInBytes    | Szabad tárterület bájtban.                                                                                                                                                                 |
| TotalStorageSpaceInBytes   | Összes tárterület bájtban.                                                                                                                                                                |
| EncryptionState            | Az eszköz titkosítási állapota.                                                                                                                                                      |
| SubscriberCarrier          | Az eszköz előfizetői szolgáltatója                                                                                                                                                       |
| PhoneNumber                | Az eszköz telefonszáma                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| CellularTechnology         | Az eszköz mobiltechnológiája                                                                                                                                                    |
| WiFiMacAddress             | Wi-Fi MAC                                                                                                                                                                              |


## <a name="devicetypes"></a>deviceTypes
A **deviceType** entitás az adattárház más entitásai által hivatkozott eszköztípust jelöli. Az eszköztípus általában leírja az eszköz típusát, gyártóját vagy mindkettőt.

|    Tulajdonság    |                                  Description                                 |
|:--------------:|:----------------------------------------------------------------------------:|
| DeviceTypeID   | Az eszköztípus egyedi azonosítója                                       |
| DeviceTypeKey  | Az eszköztípus egyedi azonosítója az adattárházban – helyettes kulcs |
| DeviceTypeName | Eszköz típusa                                                                |

### <a name="example"></a>Példa

| DeviceTypeID |        Név       |                      Description                      |
|:------------:|:-----------------:|:-----------------------------------------------------:|
| -1           | Nem érhető el   | Az eszköz típusa nem érhető el.                     |
| 0            | Asztali           | Windows asztali eszköz                              |
| 1            | Windows           | Windows-eszköz                                      |
| 2            | WinMO6            | Windows Mobile 6.0 rendszerű eszköz                           |
| 3            | Nokia             | Nokia-eszköz                                        |
| 4            | WindowsPhone      | Windows Phone rendszerű eszköz                                |
| 5            | Mac               | Mac rendszerű eszköz                                          |
| 6            | WinCE             | Windows CE rendszerű eszköz                                   |
| 7            | WinEmbedded       | Windows Embedded-eszköz                             |
| 8            | IPhone            | iPhone-eszköz                                       |
| 9            | IPad              | iPad-eszköz                                         |
| 10           | IPod              | iPod-eszköz                                         |
| 11           | Android           | Az Eszközadminisztrátorral felügyelt Android-eszköz   |
| 12           | ISocConsumer      | iSoc Consumer-eszköz                                |
| 13           | Unix              | UNIX rendszerű eszköz                                         |
| 14           | MacMDM            | A beépített MDM-ügynökkel felügyelt Mac OS X-eszköz |
| 15           | HoloLens          | Holo Lens-eszköz                                    |
| 16           | SurfaceHub        | Surface Hub-eszköz                                  |
| 17           | AndroidForWork    | Android Profile Owner használatával felügyelt Android-eszköz  |
| 18           | AndroidEnterprise | Vállalati Android-eszköz.                          |
| 100          | Blackberry        | Blackberry-eszköz                                   |
| 101          | Palm              | Palm-eszköz                                         |
| 255          | Ismeretlen           | Ismeretlen eszköztípus                                 |

## <a name="deviceenrollmenttypes"></a>deviceEnrollmentTypes
A **deviceEnrollmentType** entitás egy eszköz regisztrálásának módját jelöli. A regisztrációtípus a regisztrálás módszerét rögzíti. A felsorolt példák a különböző regisztrációtípusokat és azok jelentését mutatják be.

|         Tulajdonság         |                                    Description                                    |
|:------------------------:|:---------------------------------------------------------------------------------:|
| deviceEnrollmentTypeID   | A regisztrációs típus egyedi azonosítója.                                       |
| deviceEnrollmentTypeKey  | A regisztrációtípus egyedi azonosítója az adattárházban – helyettes kulcs. |
| deviceEnrollmentTypeName | Regisztrációs típus neve.                                                           |

### <a name="example"></a>Példa

| enrollmentTypeID |                Név                |                                        Description                                       |
|:----------------:|:----------------------------------:|:----------------------------------------------------------------------------------------:|
| 0                | Ismeretlen                            | Regisztrálás típusa nem volt gyűjtve                                                      |
| 1                | UserEnrollment                     | Felhasználó által vezérelt regisztráció BYOD-csatornán keresztül.                                           |
| 2                | DeviceEnrollmentManager            | Felhasználói regisztrálás eszközregisztráció-kezelői fiókkal.                              |
| 3                | AppleBulkWithUser                  | Tömeges alkalmazásregisztrálás felhasználói beavatkozással. (DEP, Apple Configurator)                   |
| 4                | AppleBulkWithoutUser               | Tömeges alkalmazásregisztrálás felhasználói beavatkozás nélkül.   (DEP, Apple Configurator, Mobile Config) |
| 5                | WindowsAzureADJoin                 | Windows 10 Azure AD-csatlakoztatás.                                                                |
| 6                | WindowsBulkUserless                | A Windows 10-es csoportos regisztrálás ICD-n keresztül tanúsítvánnyal.                               |
| 7                | WindowsAutoEnrollment              | Windows 10-es eszközök automatikus regisztrálás.   (Munkahelyi fiók hozzáadása)                                    |
| 8                | WindowsBulkAzureDomainJoin         | Windows 10-es tömeges, az Azure AD-csatlakoztatás.                                                           |
| 9                | WindowsCoManagement                | Windows 10-es megosztott kezelés AutoPilot vagy csoportházirend által aktiválva.                       |
| 10               | WindowsAzureADJoinsUsingDeviceAuth | Windows 10-es Azure AD-csatlakoztatás Device Auth használatával.                                            |


## <a name="intunemanagementextensions"></a>intuneManagementExtensions
Az **intuneManagementExtension** az **intuneManagementExtension**-állapotok az egyes Windows 10 rendszerű eszközökön naponta készülő listája. Az entitás az utolsó 60 nap adatait őrzi meg.

|       Tulajdonság      |                          Description                          | Példa |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| DateKey             | A dátum egyedi azonosítója.                                | 123     |
| TenantKey           | A bérlő egyedi azonosítója.                              | 456     |
| DeviceKey           | Az eszköz egyedi azonosítója.                              | 789     |
| ExtensionVersionKey | Az IntuneManagementExtension verziójának egyedi azonosítója. | 1       |
| ExtensionStateKey   | Az állapot egyedi azonosítója.                            | 2       |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates
Az **IntuneManagementExtensionHealthState** az **IntuneManagementExtension** valamennyi lehetséges állapotának listáját tartalmazza.

|      Tulajdonság     |                   Description                  | Példa |
|:-----------------:|:----------------------------------------------:|:-------:|
| ExtensionStateKey | Az állapot egyedi azonosítója.           | 2       |
| ExtensionState    | Az IntuneManagementExtension állapota. | Kifogástalan |

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions
Az **IntuneManagementExtensionVersion** entitás az **IntuneManagementExtension** által használt valamennyi verzió listáját tartalmazza.

|       Tulajdonság      |                          Description                          | Példa |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| ExtensionVersionKey | Az IntuneManagementExtension verziójának egyedi azonosítója. | 1       |
| ExtensionVersion    | A négyjegyű verziószám.                                   | 1.0.2.0 |

## <a name="managementagenttypes"></a>managementAgentTypes
A **managementAgentTypes** az eszköz kezelésére szolgáló ügynököket jelöli.

|         Tulajdonság        |                                       Description                                       |
|:-----------------------:|:---------------------------------------------------------------------------------------:|
| ManagementAgentTypeID   | A kezelőügynök típusának egyedi azonosítója.                                         |
| ManagementAgentTypeKey  | A kezelőügynök típusának egyedi azonosítója az adattárházban – helyettes kulcs. |
| ManagementAgentTypeName | Megadja, hogy milyen ügynök szolgál az eszköz kezelésére.                              |

### <a name="example"></a>Példa

| ManagementAgentTypeID |                Név               |                                  Description                                 |
|:---------------------:|:---------------------------------:|:----------------------------------------------------------------------------:|
| 1                     | EAS                               | Az Exchange Active Sync szolgáltatással kezelt eszköz                         |
| 2                     | MDM                               | MDM-ügynökkel kezelt eszköz                                   |
| 3                     | EasMdm                            | Az Exchange Active Sync szolgáltatással és MDM-ügynökkel kezelt eszköz        |
| 4                     | IntuneClient                      | Az Intune PC-ügynökkel kezelt eszköz                               |
| 5                     | EasIntuneClient                   | Az Exchange Active Sync szolgáltatással és Intune PC-ügynökkel kezelt eszköz |
| 8                     | ConfigManagerClient               | A System Center Configuration Manager-ügynökkel kezelt eszköz     |
| 10                    | ConfigurationManagerClientMdm     | Az eszköz a Configuration Managerrel és az MDM-mel van felügyelve.                    |
| 11                    | ConfigurationManagerCLientMdmEas  | Az eszköz a Configuration Managerrel, az MDM-mel és az EAS-szal van felügyelve.               |
| 16                    | Ismeretlen                           | A kezelőügynök típusa ismeretlen                                              |
| 32                    | Jamf                              | Az eszköz attribútumai a Jamf-ből vannak beolvasva.                               |
| 64                    | GoogleCloudDevicePolicyController |  Az eszközt a Google CloudDPC kezeli.                                 |

## <a name="managementstates"></a>managementStates
A **ManagementStates** entitás az eszköz állapotáról ad információt. Ezek a részletek hasznosak lehetnek távoli műveletek végrehajtásakor és jailbreakelt vagy rootolt eszköz esetén.

|       Tulajdonság      |                                     Description                                    |
|:-------------------:|:----------------------------------------------------------------------------------:|
| managementStateID   | A kezelés állapotának egyedi azonosítója.                                       |
| managementStateKey  | A kezelés állapotának egyedi azonosítója az adattárházban – helyettes kulcs. |
| managementStateName | Az eszközön végrehajtott távoli művelet állapotát jelöli.                 |

### <a name="example"></a>Példa

| managementStateID |      Név      |                                                   Description                                                   |
|:-----------------:|:--------------:|:---------------------------------------------------------------------------------------------------------------:|
| 0                 | Kezelt        | Kezelt, függőben lévő távoli műveletek nélkül.                                                                       |
| 1                 | RetirePending  | Az eszköz kivonására vonatkozó parancs van függőben.                                                             |
| 2                 | RetireFailed   | A kivonás parancs sikertelen volt az eszközön.                                                                      |
| 3                 | WipePending    | Az eszközön lévő összes adat törlésére vonatkozó parancs van függőben.                                                               |
| 4                 | WipeFailed     | Az eszközön lévő összes adat törlésére vonatkozó parancs sikertelen volt az eszközön.                                                                        |
| 5                 | Sérült      | Nem kifogástalan állapot.                                                                                              |
| 6                 | DeletePending  | Törlés parancs van függőben.                                                             |
| 7                 | RetireIssued   | Kivonás parancs van kiadva az eszközre.                                                               |
| 8                 | WipeIssued     | Parancs van kiadva az összes adat törlésére.                                                                               |
| 9                 | WipeCanceled   | Az összes adat törlésére vonatkozó parancsot visszavonták.                                                                               |
| 10                | RetireCanceled | A kivonási parancsot visszavonták.                                                                             |
| 11                | Discovered     | Az eszközt újonnan derítette fel az Intune, és amint az első alkalommal bejelentkezik, Managed (kezelt) állapotba fog kerülni. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates
A MobileAppInstallState entitás egy mobilalkalmazás telepítési állapotát jelöli, miután az hozzá lett rendelve egy eszközöket, felhasználókat vagy mindkettőt tartalmazó csoporthoz.

|       Tulajdonság      |                        Description                       |
|:-------------------:|:--------------------------------------------------------:|
| AppInstallStateKey  | A fiókhoz tartozó alkalmazástelepítési állapot egyedi azonosítója. |
| AppInstallState     | Az alkalmazástelepítési állapot felsorolásértéke.                     |
| AppInstallStateName | Az alkalmazástelepítési állapot neve.                           |

## <a name="mobileappinstallstatuscounts"></a>mobileAppInstallStatusCounts
Mobilalkalmazás telepítési állapotot jelöli egy adott céleszköztípushoz, a Mobilakalmazás-kezelés Microsoft Intune-nal való használatával.

|      Tulajdonság      |                                                          Description                                                          |
|:------------------:|:-----------------------------------------------------------------------------------------------------------------------------:|
| DateKey            | Az alkalmazástelepítési állapot rögzítési dátumának kulcsa.                                                                     |
| AppKey             | A mobilalkalmazás kulcsa, mely az AppRevision osztály egy példányát azonosítja.                                                          |
| DeviceTypeKey      | A mobilalkalmazáshoz társított eszköztípus kulcsa.                                                              |
| AppInstallStateKey | Az alkalmazástelepítési állapot kulcsa, mely a MobileAppInstallState osztály egy példányát azonosítja.                                         |
| ErrorCode          | Az alkalmazástelepítő, a mobilplatform vagy a szolgáltatás által az alkalmazás telepítésével kapcsolatban visszaadott hibakód. |
| Mennyiség              | Összesített szám.                                                                                                                  |

## <a name="ownertypes"></a>ownerTypes
Az **ownerType** entitás jelzi, hogy az eszköz tulajdonosa a vállalat, magánszemély vagy ismeretlen.

|    Tulajdonság   |                                                                                     Description                                                                                    |           Példa          |
|:-------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------:|
| ownerTypeID   | A tulajdonostípus egyedi azonosítója.                                                                                                                                               |                            |
| ownerTypeKey  | A tulajdonostípus egyedi azonosítója az adattárházban – helyettes kulcs.                                                                                                       |                            |
| ownerTypeName | Az eszközök tulajdonosának típusát jelzi: Company – az eszköz vállalati tulajdonban van.  Personal – az eszköz saját tulajdonban van (BYOD).   Unknown – nincs információ az eszközről. | Company Personal Unknown |

## <a name="policies"></a>policies
A **Szabályzat** entitás eszköz- és alkalmazáskonfigurációs profilokat, valamint megfelelőségi szabályzatokat tartalmaz. A szabályzatokat a Mobileszköz-kezelési (MDM) megoldás segítségével rendelheti hozzá a vállalat valamely csoportjához.

|          Tulajdonság          |                                                                       Description                                                                      |                Példa               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| PolicyKey                  | A szabályzat adattárházban való jelölésére szolgáló egyedi kulcs.                                                                                              | 123                                  |
| PolicyId                   | A szabályzat egyedi azonosítója az adattárházban.                                                                                                 | b66bc706-ffff-7437-0340-032819502773 |
| PolicyName                 | A szabályzat neve.                                                                                                                                    | „Windows 10 Baseline”                |
| PolicyVersion              | A szabályzat verziója. A szabályzat szerkesztésekor vagy módosításakor új verzió jön létre.                                                             | 1, 2, 3                              |
| IsDeleted                  | Jelzi, hogy frissítve lett-e a szabályzatrekord.  Igaz – a szabályzat új, frissített mezőkkel ellátott rekorddal rendelkezik.  Hamis – a szabályzat legújabb rekordja. | Igaz/hamis                           |
| StartDateInclusiveUTC      | A szabályzat adattárházban történt létrehozásának dátuma és időpontja (UTC).                                                                              | 2016. 11. 23. 0:00                      |
| DeletedDateUTC             | Az IsDeleted paraméter True (Igaz) értékre módosulásának dátuma és időpontja (UTC).                                                                                                   | 2016. 11. 23. 0:00                      |
| RowLastModifiedDateTimeUTC | A szabályzat adattárházban történt utolsó módosításának dátuma és időpontja (UTC).                                                                        | 2016. 11. 23. 0:00                      |

## <a name="policydeviceactivities"></a>policyDeviceActivities
Az alábbi táblázat a sikeres, függő, sikertelen vagy hibás állapotú eszközök napi számát tartalmazza. A szám a szabályzattípus-profilok szerinti adatot jelöli. Ha például az adott eszköz valamennyi hozzárendelt szabályzata tekintetében sikeres állapotú, akkor az entitás azon a napon eggyel növeli az értéket a sikeres állapotot jelző számlálón. Ha az adott eszköz két hozzárendelt profillal rendelkezik, amelyek közül az egyik sikeres, míg a másik hibás állapotú, akkor az entitás növeli az értéket a sikeres állapotot jelző számlálón, és hibás állapotba helyezi az eszközt. A **policyDeviceActivity** entitás azt sorolja fel, hogy hány eszköz van az egyes állapotokban az elmúlt 30 napon belüli adott napon.

|  Tulajdonság |                                           Description                                           |        Példa        |
|:---------:|:-----------------------------------------------------------------------------------------------:|:---------------------:|
| DateKey   | A dátumkulcs azt jelzi, hogy az adattárházban mikor lett rögzítve az eszközkonfigurációs profil bejelentkezése. | 20160703              |
| Függőben   | A függő állapotú egyedi eszközök száma.                                                    | 123                   |
| Sikerült | A sikeres állapotú egyedi eszközök száma.                                                    | 12                    |
| PolicyKey | Szabályzatkulcs, amely összekapcsolható a szabályzattal a policyName paraméter lekérése érdekében.                                  | Windows 10 baseline |
| Hiba     | A hibás állapotú egyedi eszközök száma.                                                      | 10                    |
| Sikertelen    | A sikertelen állapotú egyedi eszközök száma.                                                     | 2                     |

## <a name="policyplatformtypes"></a>policyPlatformTypes

|        Tulajdonság        |                      Description                      |     Példa    |
|:----------------------:|:-----------------------------------------------------:|:--------------:|
| PolicyPlatformTypeKey  | A szabályzatplatform típusának egyedi kulcsa.        | 20170519       |
| PolicyPlatformTypeId   | A szabályzatplatform típusának egyedi azonosítója. | 1              |
| PolicyPlatformTypeName | A szabályzatplatform típusának neve.              | AndroidForWork |

## <a name="policytypeactivities"></a>policyTypeActivities
A **PolicyTypeActivity** entitás a sikeres, függő, sikertelen vagy hibás állapotú eszközök számát sorolja fel összesítve. Ezeket az állapotokat az adott eszköz-, illetve alkalmazáskonfigurációs profilra, valamint megfelelőségi szabályzatra vonatkozóan ismerteti.

|    Tulajdonság   |                                          Description                                          |           Példa           |
|:-------------:|:---------------------------------------------------------------------------------------------:|:---------------------------:|
| DateKey       | A dátumkulcs azt jelzi, hogy az adattárházban mikor lett rögzítve az eszközkonfigurációs profil bejelentkezése. | 20160703                    |
| PolicyKey     | Szabályzatkulcs, amely összekapcsolható a szabályzattal a policyName paraméter lekérése érdekében.                                | Windows 10 baseline         |
| PolicyTypeKey | Szabályzatkulcs típusa, amely összekapcsolható a szabályzattípussal a szabályzattípus nevének lekérése érdekében.             | Windows 10-es megfelelőségi szabályzat |
| Függőben       | A függő állapotú egyedi eszközök száma.                                                    | 123                         |
| Sikerült     | A sikeres állapotú egyedi eszközök száma.                                                    | 12                          |
| Hiba         | A hibás állapotú egyedi eszközök száma.                                                      | 10                          |
| Sikertelen        | A sikertelen állapotú egyedi eszközök száma.                                                     | 2                           |

## <a name="policytypes"></a>policyTypes
A **PolicyType** entitás az eszköz- és alkalmazáskonfigurációs profilok, valamint a megfelelőségi szabályzatok típusait tartalmazza. A szabályzatokat a Mobileszköz-kezelési (MDM) megoldás segítségével rendelheti hozzá a vállalat valamely csoportjához.

|    Tulajdonság    |                       Description                      |            Példa            |
|:--------------:|:------------------------------------------------------:|:-----------------------------:|
| PolicyTypeId   | A szabályzat egyedi azonosítója a forrásrendszerben.  | 123                           |
| PolicyTypeKey  | A szabályzat egyedi azonosítója az adattárházban. | 1                             |
| PolicyTypeName | A szabályzattípus neve.                               | A Windows 10-re vonatkozó megfelelőségi szabályzat. |

## <a name="policyuseractivities"></a>policyUserActivities
Az alábbi táblázat a sikeres, függő, sikertelen vagy hibás állapotú felhasználók napi számát tartalmazza. A szám a szabályzattípus-profilok szerinti adatot jelöli. Ha például az egyik felhasználó valamennyi hozzárendelt szabályzata tekintetében sikeres állapotú, akkor az entitás azon a napon eggyel növeli az értéket a sikeres állapotot jelző számlálón. Ha az adott felhasználó két hozzárendelt profillal rendelkezik, amelyek közül az egyik sikeres, míg a másik hibás állapotú, akkor a felhasználót hibás állapotúnak számítjuk. A **PolicyUserActivity** entitás azt sorolja fel, hogy hány felhasználó van az egyes állapotokban az elmúlt 30 napon belüli adott napon.

|  Tulajdonság |                                          Description                                          |       Példa       |
|:---------:|:---------------------------------------------------------------------------------------------:|:-------------------:|
| DateKey   | A dátumkulcs azt jelzi, hogy az adattárházban mikor lett rögzítve az eszközkonfigurációs profil bejelentkezése. | 20160703            |
| Függőben   | A függő állapotú egyedi eszközök száma.                                                    | 123                 |
| Sikerült | A sikeres állapotú egyedi eszközök száma.                                                    | 12                  |
| PolicyKey | Szabályzatkulcs, amely összekapcsolható a szabályzattal a policyName paraméter lekérése érdekében.                                | Windows 10 baseline |
| Hiba     | A hibás állapotú egyedi eszközök száma.                                                      | 10                  |

## <a name="termsandconditions"></a>termsAndConditions
A **termsAndConditions** entitás adott feltételek és kikötések (T&C) szabályzat tartalmának metaadatait és tartalmát jelöli. A T&C-szabályzatok tartalma megjelenik a felhasználóknak, amikor először próbálnak regisztrálni az Intune-ban, majd később a szerkesztéseknél is, amennyiben a rendszergazda kötelezővé tette az újbóli elfogadást. Ez lehetővé teszi, hogy a rendszergazda közzétegye azokat a feltételeket, amelyeket a felhasználónak el kell fogadnia ahhoz, hogy az eszközük regisztrálható legyen az Intune-ban.

|    Tulajdonság        |    Description    |    Példa        |
|----------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------------|
|    termsAndConditionsKey    |    Egy, a „userTermsAndConditionsAcceptances” gyűjteményben lévő egyik tételhez tartozó kulcs    |    123    |
|    termsAndCondidionsId    |    Ennek a termsAndConditions-bejegyzésnek az azonosítója    |    276edcb7-7440-4339-b6c5-8b6fc556fee6    |
|    termsAndConditionsVersion    |    A feltételek és kikötések bejegyzés verziója    |    1    |
|    name    |    A feltételek és kikötések bejegyzés neve.        |    Az Intune használati feltételei     |
|    leírás    |    A feltételek és kikötések leírása.     |         |
|    title    |    A feltételek és kikötések címe.     |    Eszközkezelési vállalati szabályzat        |
|    summaryOfTerms    |    A felhasználók számára készült feltételek összefoglalása.     |    Elfogadom a használati feltételeket.    |
|    termsAndConditionsBodyText    |    A feltételek és kikötések szövegtörzse.       |    * Eszköztitkosítás * 6 számjegyű PIN-kód megkövetelése    |
|    isDeleted    |    Igaz vagy hamis érték arra, hogy ez az érték törölve van-e.     |    Hamis    |
|    startDateInclusiveUTC    |    A feltételek és kikötések kezdő dátuma.     |    2018. 08. 23. 04:01:34    |
|    endDateEclusiveUTC    |    A feltételek és kikötések záró dátuma.     |    9999. 12. 31. 00:00:00    |

## <a name="userdeviceassociations"></a>userDeviceAssociations
A **UserDeviceAssociation** entitás tartalmazza a szervezet felhasználói hozzárendeléseit.

|        Név        |                                             Description                                            |     Példa     |
|:------------------:|:--------------------------------------------------------------------------------------------------:|:---------------:|
| UserKey            | A felhasználó egyedi azonosítója az adattárházban.   (Helyettes kulcs).                            | 123             |
| DeviceKey          | Az eszköz egyedi azonosítója az adattárházban.                                             | 123             |
| CreatedDateTimeUTC | A felhasználói eszköztársítás létrehozásának dátuma és időpontja. UTC formátumban.                     | 2016. 11. 23. 0:00 |
| IsDeleted          | Azt jelzi, hogy a felhasználó megszüntette az eszköz regisztrációját, és a társítás már nem aktuális. | Igaz/hamis      |
| EndedDateTimeUTC   | Az IsDeleted paraméter True (Igaz) értékre módosulásának dátuma és időpontja (UTC).                                               | 2017. 06. 23. 00:00  |

## <a name="users"></a>felhasználók
A **user** entitás a vállalaton belül hozzárendelt licenccel rendelkező összes Azure Active Directory- (Azure AD-) felhasználót kilistázza.

A **user** entitásgyűjtemény felhasználói adatokat tartalmaz. A rekordok között akkor is ott vannak az adatgyűjtési időszakon belüli felhasználói állapotok, ha a felhasználót azóta eltávolították. Például az elmúlt egy hónap során hozzáadhattak az Intune-hoz egy felhasználót, majd el is távolíthatták onnan. Az elmúlt hónap adatai tartalmazzák a felhasználót és állapotát annak ellenére, hogy a felhasználó a jelentés időpontjában nincs jelen. Ekkor létrehozhat egy olyan jelentést, amely megjeleníti a felhasználó korábbi jelenlétének időtartamát az adatokban.

|          Tulajdonság          |                                                                                                           Description                                                                                                          |                Példa               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| UserKey                    | A felhasználó egyedi azonosítója az adattárházban – helyettes kulcs.                                                                                                                                                         | 123                                  |
| UserId                     | A felhasználó egyedi azonosítója – a UserKey-hez hasonló, de természetes kulcs.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| UserEmail                  | A felhasználó e-mail címe.                                                                                                                                                                                                     | John@constoso.com                    |
| UPN                        | A felhasználó egyszerű felhasználóneve.                                                                                                                                                                                               | John@constoso.com                    |
| DisplayName                | A felhasználó megjelenítendő neve.                                                                                                                                                                                                      | István                                 |
| IntuneLicensed             | Megadja, hogy a felhasználó rendelkezik-e Intune-licenccel.                                                                                                                                                                              | Igaz/hamis                           |
| IsDeleted                  | Azt jelzi, hogy a felhasználó összes engedélye lejárt-e, és a felhasználót emiatt eltávolították-e az Intune-ból. Egyetlen rekord esetén ez a jelölő nem változik. Ehelyett új rekord jön létre egy új felhasználói állapothoz. | Igaz/hamis                           |
| RowLastModifiedDateTimeUTC | A rekord adattárházban történt utolsó módosításának dátuma és időpontja (UTC)                                                                                                                                                 | 2016. 11. 23. 0:00                      |

## <a name="usertermsandconditionsacceptances"></a>userTermsAndConditionsAcceptances
A **userTermsAndConditionsAcceptance** entitás egy adott Feltételek és kikötések szabályzat adott felhasználó általi elfogadásának állapotát jelzi. A felhasználónak a feltételek legfrissebb verzióját kell elfogadnia ahhoz, hogy továbbra is hozzáférése legyen a Céges portálhoz.

|    Tulajdonság    |    Description    |    Példa    |
|-------------------------------|--------------------------------------------------------------------------------|----------------------------|
|    dateKey    |    A „dates” gyűjteményen belüli dátumértéknek megfelelő kulcs.     |    20180823    |
|    userKey    |    A „users” gyűjtemény egy felhasználójának leképezésére használt felhasználói kulcs.     |    20000    |
|    termsAndConditionsKey    |    Egy, a „termsAndConditions” gyűjteményben lévő egyik bejegyzéshez tartozó kulcs    |    1    |
|    acceptedDateTimeUTC    |    Az az idő amikor a felhasználó elfogadta ezeket a feltételeket és kikötéseket    |    2018. 08. 23. 04:01:34    |
|    lastModifiedDateTimeUTC    |    A bejegyzés utolsó módosításának ideje.     |    2018. 08. 23. 04:01:34    |

## <a name="vppprogramtypes"></a>vppProgramTypes 
A **vppProgramType** entitás az alkalmazás lehetséges VPP-programtípusait listázza.

|      Tulajdonság      |          Description         |
|:------------------:|:----------------------------:|
| VppProgramTypeID   | A típus azonosítója.           |
| VppProgramTypeKey  | A kulcs helyettes kulcsa. |
| VppProgramTypeName | A VPP program típusa.          |

### <a name="example"></a>Példa

|             VppProgramID             |         Név        | Description                |
|:------------------------------------:|:-------------------:|----------------------------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft           | A Microsoft VPP-programja. |
| 00000000-0000-0000-0000-000000000000 | Not Yet Available (Még nem érhető el) | Alapértelmezett érték, nincs VPP.   |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple               | Az Apple VPP-programja.     |

## <a name="next-steps"></a>További lépések

Az Intune Adattárházról további információt talál [Az adattárház adatmodellje](https://docs.microsoft.com/intune/reports-ref-data-model) című témakörben.
