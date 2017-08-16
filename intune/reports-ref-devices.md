---
title: "Eszközök | Microsoft Docs"
description: "Az Intune-adattárház API-ban található entitásgyűjtemények eszközkategóriájára vonatkozó referencia-témakör."
keywords: "Intune-adattárház"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8013d7f091c154709f0dd98dcda2e7f5f09056d2
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-devices-entities"></a>Eszközök típusú entitások referenciája

Az **Eszközök** kategória az információkat nyomon követő mobileszközökhöz tartozó entitásokat tartalmazza, egyebek mellett az alábbiakat:

  -  Eszköz típusa
  -  Eszköz regisztrációja és a regisztráció állapota
  -  Az eszközök tulajdonjoga
  -  Eszközkezelés állapota
  -  Az eszköz Azure AD-tagságának állapota
  -  Beléptetés állapota
  -  Előzményadatok az eszközről
  -  Az eszközön lévő alkalmazások listája

## <a name="devicetypes"></a>DeviceTypes

A **DeviceTypes** entitás az adattárház más entitásai által hivatkozott eszköztípust jelöli. Az eszköztípus általában leírja az eszköz típusát, gyártóját vagy mindkettőt.

| Tulajdonság  | Leírás |
|---------|------------|
| DeviceTypeID |Az eszköztípus egyedi azonosítója |
| DeviceTypeKey |Az eszköztípus egyedi azonosítója az adattárházban – helyettes kulcs |
| DeviceTypeName |Eszköz típusa |

## <a name="example"></a>Példa

| DeviceTypeID  | Név | Leírás |
|---------|------------|--------|
| 0 |Asztali |Windows asztali eszköz |
| 1 |WindowsRT |Windows RT rendszerű eszköz |
| 2 |WinMO6 |Windows Mobile 6.0 rendszerű eszköz |
| 3 |Nokia |Nokia-eszköz |
| 4 |WindowsPhone |Windows Phone rendszerű eszköz |
| 5 |Mac |Mac rendszerű eszköz |
| 6 |WinCE |Windows CE rendszerű eszköz |
| 7 |WinEmbedded |Windows Embedded-eszköz |
| 8 |IPhone |iPhone-eszköz |
| 9 |IPad |iPad-eszköz |
| 10 |IPod |iPod-eszköz |
| 11 |Android |Az Eszközadminisztrátorral felügyelt Android-eszköz |
| 12 |ISocConsumer |iSoc Consumer-eszköz |
| 14 |MacMDM |A beépített MDM-ügynökkel felügyelt Mac OS X-eszköz |
| 15 |HoloLens |Holo Lens-eszköz |
| 16 |SurfaceHub |Surface Hub-eszköz |
| 17 |AndroidForWork |Android for Work Profile Owner használatával felügyelt Android-eszköz |
| 100 |Blackberry |Blackberry-eszköz |
| 101 |Palm |Palm-eszköz |
| 255 |Ismeretlen |Ismeretlen eszköztípus |

## <a name="clientregistrationstatetypes"></a>ClientRegistrationStateTypes

A **ClientRegistrationStateTypes** entitás az adattárház más táblái által hivatkozott eszköztípust jelöli.

| Tulajdonság  | Leírás |
|---------|------------|
| clientRegisterationStateID |Regisztrációs állapot egyedi azonosítója |
| clientRegisterationStateKey |A regisztrációs állapot egyedi azonosítója az adattárházban – helyettes kulcs |
| clientRegisterationStateName |Regisztráció állapota |

## <a name="example"></a>Példa

| ClientRegisterationStateID  | Név | Leírás |
|---------|------------|--------|
| 0 |NotRegistered |Nincs regisztrálva |
| 1 |SMSIDConflict |SMS ID-ütközés |
| 2 |Regisztrálva |Regisztrálva |
| 3 |Revoked |Ez az állapot azt jelzi, hogy a rendszergazda letiltotta az ügyfelet, és az ügyfél tiltása feloldható. Egy eszköz a törlését vagy kivonását követően is Revoked (visszavonva) állapotban lehet. |
| 4 |KeyConflict |Kulcs ütközés |
| 5 |ApprovalPending |Jóváhagyás függőben |
| 6 |ResetCert |Tanúsítvány alaphelyzetbe állítása |
| 7 |NotRegisteredPendingEnrollment |Nincs regisztrálva, regisztráció folyamatban |
| 8 |Ismeretlen |Ismeretlen állapot |

## <a name="enrollmenttypes"></a>EnrollmentTypes

Az **EnrollmentTypes** entitás egy eszköz regisztrálásának módját jelöli. A regisztrációtípus a regisztrálás módszerét rögzíti. A felsorolt példák a különböző regisztrációtípusokat és azok jelentését mutatják be.

| Tulajdonság  | Leírás |
|---------|------------|
| managementStateID |A kezelés állapotának egyedi azonosítója. |
| managementStateKey |A kezelés állapotának egyedi azonosítója az adattárházban – helyettes kulcs. |
| managementStateName |Az eszközön végrehajtott távoli művelet állapotát jelöli. |

## <a name="example"></a>Példa

| enrollmentTypeID  | Név | Leírás |
|---------|------------|--------|
| 0 |Ismeretlen |Ismeretlen regisztrációtípus |
| 1 |UserEnrollment |Felhasználó által kezdeményezett regisztráció |
| 2 |DeviceEnrollment |Eszközregisztráció felhasználó nélküli profillal |
| 3 |DeviceEnrollmentWithUDA |Eszközregisztráció UDA-profillal. |
| 4 |AzureDomainJoined |Felhasználó által kezdeményezett regisztráció Azure Active Directoryn keresztül |
| 5 |UserEnrollmentWithServiceAccount |Felhasználó által kezdeményezett regisztráció szolgáltatásfiókon keresztül |
| 6 |DepDeviceEnrollment |DEP-eszközregisztráció felhasználó nélküli profillal |
| 7 |DepDeviceEnrollmentWithUDA |DEP-eszközregisztráció UDA-profillal |
| 8 |AutoEnrollment |Kombinált DRS- és MDM-regisztráció saját eszköz használata esetén |

## <a name="ownertypes"></a>OwnerTypes

Az **EnrollmentTypes** entitás jelzi, hogy az eszköz tulajdonosa a vállalat, magánszemély vagy ismeretlen.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| ownerTypeID |A tulajdonostípus egyedi azonosítója | |
| ownerTypeKey |A tulajdonostípus egyedi azonosítója az adattárházban – helyettes kulcs | |
| ownerTypeName |Az eszközök tulajdonosának típusát jelzi: Company – az eszköz vállalati tulajdonban van. Personal – az eszköz saját tulajdonban van (BYOD).  Unknown – nincs információ az eszközről. |Company Personal Unknown |

## <a name="mdmstatuses"></a>MdmStatuses

Az **MdmStatuses** entitás az eszköz megfelelőségi állapotát jelzi.

| Tulajdonság  | Leírás | Példa |
|---------|------------|--------|
| MdmStatusName |MdmStatus azonosító |0 - Unknown (nem ismert) 1 – Compliant (megfelelő) 2 – Not Compliant (nem megfelelő) |
| MdmStatusKey |A megfelelőségi állapot egyedi azonosítója az adattárházban – helyettes kulcs | |

## <a name="managementstates"></a>ManagementStates

A **ManagementStates** entitás az eszköz állapotáról ad információt. Ezek a részletek hasznosak lehetnek távoli műveletek végrehajtásakor és jailbreakelt vagy rootolt eszköz esetén.

| Tulajdonság  | Leírás |
|---------|------------|
| managementStateID |A kezelés állapotának egyedi azonosítója |
| managementStateKey |A kezelés állapotának egyedi azonosítója az adattárházban – helyettes kulcs |
| managementStateName |Az eszközön végrehajtott távoli művelet állapotát jelöli. |

## <a name="example"></a>Példa

| managementStateID  | Név | Leírás |
|---------|------------|--------|
| 0 |Kezelt |Kezelt, függőben lévő távoli műveletek nélkül. |
| 1 |RetirePending |Az eszköz kivonására vonatkozó parancs van függőben. |
| 2 |RetireFailed |A kivonás parancs sikertelen volt az eszközön. |
| 3 |WipePending |Az eszközön lévő összes adat törlésére vonatkozó parancs van függőben. |
| 4 |WipeFailed |Az eszközön lévő összes adat törlésére vonatkozó parancs sikertelen volt az eszközön. |
| 5 |Sérült |Nem kifogástalan állapot |
| 6 |DeletePending |Törlés parancs van függőben. |
| 7 |RetireIssued |Kivonás parancs van kiadva az eszközre. |
| 8 |WipeIssued |Parancs van kiadva az összes adat törlésére. |
| 9 |WipeCanceled |Az összes adat törlésére vonatkozó parancsot visszavonták. |
| 10 |RetireCanceled |A kivonási parancsot visszavonták. |
| 11 |Discovered |Az eszközt újonnan derítette fel az Intune, és amint az első alkalommal bejelentkezik, Managed (kezelt) állapotba fog kerülni |

## <a name="workplacejoinstatetypes"></a>WorkPlaceJoinStateTypes

A **WorkPlaceJoinStateTypes** entitás az eszköz Azure Active Directory munkahelyi csatlakozási állapotát jelöli.  A regisztrációs folyamat egy vagy több tanúsítványt is felhasználhat ellenőrzés vagy hitelesítés céljára. Amikor egy eszköz munkahelyi csatlakozást hajt végre, ezek a tanúsítványok szolgálnak az eszköz és a felhasználó érvényesítésére. A tanúsítványok kiadása egy SCEP (Egyszerű tanúsítvány-beiktatási protokoll) kiszolgálón keresztül történik. Az entitásban lévő értékek a folyamaton átmenő eszköz lehetséges állapotait jelölik. Néhány ilyen állapot azt jelzi, hogy a munkahelyi csatlakozás a kívánt tanúsítvány SCEP-kiszolgáló általi kiadásának hibája miatt meghiúsult. Ha az eszköz még nem ment át ezen a folyamaton, akkor a beállított érték Unknown (Ismeretlen) lesz.

| Tulajdonság  | Leírás |
|---------|------------|
| WorkPlaceJoinStateID |A munkahelyi csatlakozás állapotának egyedi azonosítója |
| WorkPlaceJoinStateKey |A munkahelyi csatlakozás állapotának egyedi azonosítója az adattárházban – helyettes kulcs |
| WorkPlaceJoinStateName |Munkahelyi csatlakoztatás állapota |

## <a name="example"></a>Példa

| workPlaceJoinStateID  | Név | Leírás |
|---------|------------|--------|
| 0 |Ismeretlen |Ha az eszköz nem végzett munkahelyi csatlakozást, akkor Unknown (Ismeretlen) állapotban van |
| 1 |Sikerült |A munkahelyi csatlakozás sikerült |
| 2 |FailureToGetScepMetadata |A SCEP-metaadatok lekérése nem sikerült |
| 3 |FailureToGetScepChallenge |A SCEP-kérdés lekérése nem sikerült |
| 4 |DeviceFailureToInstallScepCommand |A SCEP-parancs telepítése az eszközön sikertelen |
| 5 |DeviceFailureToGetCertificate |Az eszköz nem jutott tanúsítványhoz a SCEP-en keresztül |
| 6 |DeviceScepPending |Függő állapot; az eszköz még a SCEP-folyamatot végzi |
| 7 |DeviceScepFailed |A tanúsítvány SCEP-en keresztül történő telepítése nem sikerült az eszközön |
| 8 |AADValidationFailed |Nem sikerült ellenőrizni, hogy az eszköz létezik-e az AAD-ben |

## <a name="managementagenttypes"></a>ManagementAgentTypes

A **ManagementAgentTypes** az eszköz kezelésére szolgáló ügynököket jelöli.

| Tulajdonság  | Leírás |
|---------|------------|
| ManagementAgentTypeID |A kezelőügynök típusának egyedi azonosítója |
| ManagementAgentTypeKey |A kezelőügynök típusának egyedi azonosítója az adattárházban – helyettes kulcs |
| ManagementAgentTypeName |Megadja, hogy milyen ügynök szolgál az eszköz kezelésére. |

## <a name="example"></a>Példa

| ManagementAgentTypeID  | Név | Leírás |
|---------|------------|--------|
| 1 |EAS |Az Exchange Active Sync szolgáltatással kezelt eszköz |
| 2 |MDM |MDM-ügynökkel kezelt eszköz |
| 3 |EasMdm |Az Exchange Active Sync szolgáltatással és MDM-ügynökkel kezelt eszköz |
| 4 |IntuneClient |Az Intune PC-ügynökkel kezelt eszköz |
| 5 |EasIntuneClient |Az Exchange Active Sync szolgáltatással és Intune PC-ügynökkel kezelt eszköz |
| 8 |ConfigManagerClient |A System Center Configuration Manager-ügynökkel kezelt eszköz |
| 16 |Ismeretlen |A kezelőügynök típusa ismeretlen |

## <a name="devices"></a>Eszközök

A **Devices** entitás felsorolja az összes kezelt regisztrált eszközt és azok lényeges tulajdonságait.

| Tulajdonság  | Leírás |
|---------|------------|
| DeviceKey |Az eszköz egyedi azonosítója az adattárházban – helyettes kulcs |
| DeviceId |Az eszköz egyedi azonosítója |
| DeviceName |Az eszköz neve az eszközök elnevezését megengedő platformokon. Más platformokon az Intune hoz létre nevet más tulajdonságok alapján. Ez az attribútum nem minden eszköz esetén elérhető. |
| DeviceTypeKey |Az eszközhöz tartozó eszköztípus attribútum kulcsa |
| ClientRegisterationStateKey |Az eszközhöz tartozó ügyfélregisztrációs állapot attribútum kulcsa |
| OwnerTypeKey |Az eszközhöz tartozó tulajdonostípus attribútum (corporate, personal, vagy unknown) kulcsa. |
| objectSourceKey |Hagyja figyelmen kívül ezt az oszlopot. |
| CreatedDate |Az eszköz regisztrálásának dátuma |
| LastContact |Az eszköz utolsó Intune-bejelentkezése |
| LastContactNotification |Az utolsó alkalom, amikor az Intune értesítette ez eszközt, hogy jelentkezzen be az Intune-ba |
| LastContactWorkplaceJoin |Az eszköz utolsó ismert munkahelyi csatlakozási állapotának időbélyege. |
| ManagementAgentKey |Az eszközhöz társított kezelőügynök kulcsa. |
| ManagementStateKey |Az eszközhöz társított kezelési állapot, beleértve a távoli műveletek utolsó állapotát, és hogy az eszköz jailbreakelt vagy rootolt-e. |
| ReferenceId |Az eszköz azonosítója az Azure Active Directoryban |
| WorkPlaceJoinStateKey |Az eszközhöz társított munkahelyi csatlakozási állapot kulcsa. |
| CategoryId |Hagyja figyelmen kívül ezt az oszlopot. |
| EnrollmentTypeKey |Az eszközhöz társított, a regisztráció módját jelző regisztrációtípus kulcsa. |
| CertExpirationDate |Az MDM-felügyeleti tanúsítvány lejárati dátuma. |
| MdmStatusKey |Az MdmStatus kulcsa |
| OSFamily |Operációsrendszer-család (Windows, iOS, Android, stb.) |
| OSVersion |Operációs rendszer verziója |
| OSMajorVersion |Az operációs rendszer verziószámának főverzió összetevője (főverzió.alverzió.build.változat) |
| OSMinorVersion |Az operációs rendszer verziószámának alverzió összetevője (főverzió.alverzió.build.változat) |
| OSBuildNumber |Az operációs rendszer verziószámának build összetevője (főverzió.alverzió.build.változat) |
| OSRevisionNumber |Az operációs rendszer verziószámának változat összetevője (főverzió.alverzió.build.változat) |
| EasID |Az eszköz EAS-azonosítója, amennyiben az eszközt az Exchange Active Sync szolgáltatás kezeli. |
| GraphDeviceIsManaged |Az Intune által az AAD-ban utoljára beállított kezelési állapot |
| GraphDeviceIsCompliant |Az Intune által az AAD-ban utoljára beállított megfelelőségi állapot |
| Sorozatszám |Az eszköz sorozatszáma, ha elérhető |
| EnrolledByUser |Az eszközt regisztráló felhasználónak a Felhasználó tábla userId oszlopára hivatkozó azonosítója. |
| RowLastModifiedDateTimeUTC |A rekord utolsó módosításának időpontja. |
| ProcessorArchitecture |Processzor architektúrája |
| DeviceAction |Az utoljára kiadott eszközművelet, egyelőre figyelmen kívül hagyható. |
| Gyártó |Az eszköz gyártója |
| Modell |Az eszköz típusa |
| LastPolicyUpdateUtc |Az utolsó időpont, amikor az eszközön szabályzat frissült |
| LastExchangeStatusUtc |Az utolsó időpont, amikor az eszköz szinkronizált az Exchange-dzsel. |
| IsDeleted |Értéke True, ha az eszközt már nem az Intune kezeli. Megőrzi az utolsó ismert állapotot. |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

A **DevicePropertyHistory** entitásban ugyanazon tulajdonságok szerepelnek, mint a Devices (Eszközök) táblában, amely minden eszközről napi pillanatképet tárol 90 napra visszamenőleg. A DateKey mező az egyes sorok napját jelzi.

| Tulajdonság  | Leírás |
|---------|------------|
| DateKey |A napot megadó dátumtáblázat-hivatkozás |
| DeviceKey |Az eszköz egyedi azonosítója az adattárházban – helyettes kulcs. Az Intune-eszközazonosítót tartalmazó eszköztáblára mutató hivatkozás |
| DeviceModel |Az eszköz típusa |
| Operációs rendszer |Az eszköz operációs rendszere |
| DeviceName |Az eszköz neve az eszközök elnevezését megengedő platformokon. Más platformokon az Intune hoz létre nevet más tulajdonságok alapján. Ez az attribútum nem minden eszköz esetén elérhető. |
| SoftwareVersion |Az esetek többségében ez az operációs rendszer verziója, kivéve az Apple-platformoknál, ahol ez eltér az operációs rendszer verziójától. |
| Imei |IMEI-szám |
| HardwareInventoryTimeUtc |Az eszköz első leltári jelentésének időpontja. |
| InventoryModifiedTimeUtc |Az utolsó időpont, amikor leltár tárolódott a pillanatkép készítésekor |
| InventoryReportingTimeUtc |Az eszköz utolsó leltárba vételének időpontja. |
| ExchangeActiveSyncId |Exchange ActiveSync eszközazonosító |
| ComputerSystemDescription |Rendszerleírás |
| ComputerSystemName |Rendszer neve |
| ComputerSystemManufacturer |Rendszer gyártója |
| ComputerSystemModel |Rendszermodell |
| UserName |Felhasználónév |
| OSType |Operációs rendszer típusa |
| OSCaption |Operációs rendszer felirata |
| OSName |Operációs rendszer neve |
| OSManufacturer |Operációs rendszer gyártója |
| OSProductSuite |Operációs rendszer termékcsomagja |
| OSProductType |Operációs rendszer terméktípusa |
| Területi beállítás |Operációs rendszer területi beállítása |
| PhysicalMemoryCapacity |Fizikai memória-kapacitás (bájt) |
| PhysicalMemoryRemovable |Fizikai cserélhető memória (bájt) |
| SystemEnclosureChassisTypesInnerText |Az eszköz rendszerháztípusát adja meg. A számok a következő értékeket jelölik: 0 vagy üres = ismeretlen  1 = asztali gép  2 = laptop  3 = munkaállomás  4 = Enterprise Server  100 = telefon  101 = tablet  102/103 = más ismeretlen mobileszköz-típus |
| SystemEnclosureModel |Rendszerház típusa |
| SystemEnclosureSerialNumber |Rendszerház sorozatszáma |
| NetworkAdapterConfigurationText |Konfigurációs szöveg a hálózati adapterről |
| MacAddress |MAC-cím |
| SmsID |Intune-eszközazonosító |
| CertExpiry |Az MDM-felügyeleti tanúsítvány lejárati dátuma |
| DeviceClientAgentVersion |Ügyfélügynök verziója |
| DeviceClientID |Eszköz ügyfélazonosító |
| Sorozatszám |Sorozatszám |
| DeviceManufacturer |Eszköz gyártója |
| DMVersion |DM-verzió |
| FirmwareVersion |Belső vezérlőprogram verziója |
| HardwareVersion |Hardver verziója |
| PlatformType |Platform típusa |
| ProcessorLevel |Processzor szint |
| ProcessorRevision |Processzor-változat |
| Termék |Termék |
| ProductVersion |Termékváltozat |
| OEM |Eredeti gyártó |
| DeviceBuildVersion |Eszköz build-verziószáma |
| MEID |Mobilkészülék-azonosító szám. |
| PhoneNumber |Telefonszám |
| SubscriberCarrierNetwork |Telefonszolgáltatás hálózati neve |
| CellularTechnology |Telefonszolgáltató hálózat típusa (CDMA/GSM) |
| IMSI |IMSI-szám |
| JailBroken |Értéke True, ha az eszköz jailbreakelt vagy rootolt. |
| IsActivationLockEnabled |Értéke True, ha az aktiválási zár engedélyezve van |
| DeviceType |Eszköz típusa |
| IsSupervised |Felügyelt |
| DeviceDisplayNumberOfColors |Kijelzőn megjeleníthető színek száma |
| HorizontalResolution |Az eszköz vízszintes képernyőfelbontása |
| VerticalResolution |Az eszköz függőleges képernyőfelbontása |
| StorageFree |Szabad tárterület (bájt) |
| StorageTotal |Összes tárterület (bájt) |
| ProgramFree |Szabad programmemória (bájt) |
| ProgramTotal |Összes programmemória (bájt) |
| RemovableStorageFree |Szabad tárterület cserélhető tárolón (bájt) |
| RemovableStorageTotal |Összes tárterület cserélhető tárolón (bájt) |
| DeviceMemoryDeviceCapacity |Eszköz memóriakapacitása |
| DeviceMemoryAvailableDeviceCapacity |Eszköz rendelkezésre álló memóriakapacitása |
| DeviceOSVersion |Operációs rendszer verziója |
| DeviceOSPlatform |Operációs rendszer platformja |
| DeviceOSLanguage |Operációs rendszer megjelenítési nyelve |
| PasswordMaxAttemptsBeforeWipe |Jelszó-próbálkozások maximálisan engedélyezett száma az eszközön lévő adatok törlése előtt |
| PasswordMinComplexChars |A jelszóban használandó speciális karakterek minimális száma |
| PasswordMinLength |Jelszó minimális megkövetelt hossza |
| PasswordHistory |Jelszó – legalább ennyi korábbi jelszó nem használható |
| PasswordEnabled |Jelszó – Engedélyezett? |
| PasswordExpiration |Jelszó – Lejárat dátuma |
| AllowRecoveryPassword |Jelszó-visszaállítás engedélyezése |
| PasswordAutoLockTimeout |Jelszó – Automatikus lezárás időkorlátja |
| PasswordType |Jelszótípus |
| BacklightACTimeout |Háttérvilágítás időkorlátja áramforrásról üzemeltetve |
| BacklightBatTimeout |Háttérvilágítás időkorlátja akkumulátorról üzemeltetve |
| PowerBackupPercent |Energiatartalék százalékban |
| BatteryPercent |Akkumulátortöltés százalékban. |
| PlatformID |Platformazonosító |
| ExchangeDeviceID |Exchange-eszközazonosító |
| SmsProcessorDescription |Processzor leírása |
| OwnerEmailAddress |Tulajdonos e-mail-címe |
| DeviceOSName |Operációs rendszer neve |
| WifiMac |WiFi MAC-címe |
| EthernetMac |Ethernet MAC-cím |
| RequireEncryption |Jelzi, hogy az eszköz titkosítva van-e. |
| ActivationLockBypassCode |Kód az aktiválási zár megkerüléséhez |

## <a name="mdmdeviceinventoryhistories"></a>MdmDeviceInventoryHistories

Az **MdmDeviceInventoryHistories** entitás 90 napra visszamenőleg napi pillanatképeket tartalmaz az MDM-kezelésű eszközök leltáradatairól. A DateKey mező a sor napját jelzi. Egyes tulajdonságok esetleg nem vonatkoztathatók vagy tölthetők ki minden eszközre, ezért olvassa át alaposan a ezt az oldalt. További információ: [A regisztrált eszközök áttekintése a Microsoft Intune leltárfunkciójával](https://docs.microsoft.com/Intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-Intune).

| Tulajdonság  | Leírás |
|---------|------------|
| DateKey |A napot megadó dátumtáblázat-hivatkozás |
| DeviceKey |Az eszköz egyedi azonosítója az adattárházban – helyettes kulcs. Az Intune-eszközazonosítót tartalmazó eszköztáblára mutató hivatkozás |
| DeviceModel |Az eszköz típusa |
| Operációs rendszer |Az eszköz operációs rendszere |
| DeviceName |Az eszköz neve az eszközök elnevezését megengedő platformokon. Más platformokon az Intune hoz létre nevet más tulajdonságok alapján. Ez az attribútum nem minden eszköz esetén elérhető. |
| SoftwareVersion |Az esetek többségében ez az operációs rendszer verziója, kivéve az Apple-platformoknál, ahol ez eltér az operációs rendszer verziójától. |
| Imei |IMEI-szám |
| HardwareInventoryTimeUtc |Az eszköz első leltári jelentésének időpontja. |
| InventoryModifiedTimeUtc |Az utolsó időpont, amikor leltár tárolódott a pillanatkép készítésekor |
| InventoryReportingTimeUtc |Az eszköz utolsó leltárba vételének időpontja. |
| ExchangeActiveSyncId |Exchange ActiveSync eszközazonosító |
| ComputerSystemDescription |Rendszerleírás |
| ComputerSystemName |Rendszer neve |
| ComputerSystemManufacturer |Rendszer gyártója |
| ComputerSystemModel |Rendszermodell |
| UserName |Felhasználónév |
| OSType |Operációs rendszer típusa |
| OSCaption |Operációs rendszer felirata |
| OSName |Operációs rendszer neve |
| OSManufacturer |Operációs rendszer gyártója |
| OSProductSuite |Operációs rendszer termékcsomagja |
| OSProductType |Operációs rendszer terméktípusa |
| Területi beállítás |Operációs rendszer területi beállítása |
| PhysicalMemoryCapacity |Fizikai memória-kapacitás (bájt) |
| PhysicalMemoryRemovable |Fizikai cserélhető memória (bájt) |
| SystemEnclosureChassisTypesInnerText |Az eszköz rendszerháztípusát adja meg. A számok a következő értékeket jelölik: 0 vagy üres = ismeretlen  1 = asztali gép  2 = laptop  3 = munkaállomás  4 = Enterprise Server  100 = telefon  101 = tablet  102/103 = más ismeretlen mobileszköz-típus |
| SystemEnclosureModel |Rendszerház típusa |
| SystemEnclosureSerialNumber |Rendszerház sorozatszáma |
| NetworkAdapterConfigurationText |Konfigurációs szöveg a hálózati adapterről |
| MacAddress |MAC-cím |
| SmsID |Intune-eszközazonosító |
| CertExpiry |Az MDM-felügyeleti tanúsítvány lejárati dátuma |
| DeviceClientAgentVersion |Ügyfélügynök verziója |
| DeviceClientID |Eszköz ügyfélazonosító |
| Sorozatszám |Sorozatszám |
| DeviceManufacturer |Eszköz gyártója |
| DMVersion |DM-verzió |
| FirmwareVersion |Belső vezérlőprogram verziója |
| HardwareVersion |Hardver verziója |
| PlatformType |Platform típusa |
| ProcessorLevel |Processzor szint |
| ProcessorRevision |Processzor-változat |
| Termék |Termék |
| ProductVersion |Termékváltozat |
| OEM |Eredeti gyártó |
| DeviceBuildVersion |Eszköz build-verziószáma |
| MEID |Mobilkészülék-azonosító szám. |
| PhoneNumber |Telefonszám |
| SubscriberCarrierNetwork |Telefonszolgáltatás hálózati neve |
| CellularTechnology |Telefonszolgáltató hálózat típusa (CDMA/GSM) |
| IMSI |IMSI-szám |
| JailBroken |Értéke True, ha az eszköz jailbreakelt vagy rootolt. |
| IsActivationLockEnabled |Értéke True, ha az aktiválási zár engedélyezve van |
| DeviceType |Eszköz típusa |
| IsSupervised |Felügyelt |
| DeviceDisplayNumberOfColors |Kijelzőn megjeleníthető színek száma |
| HorizontalResolution |Az eszköz vízszintes képernyőfelbontása |
| VerticalResolution |Az eszköz függőleges képernyőfelbontása |
| StorageFree |Szabad tárterület (bájt) |
| StorageTotal |Összes tárterület (bájt) |
| ProgramFree |Szabad programmemória (bájt) |
| ProgramTotal |Összes programmemória (bájt) |
| RemovableStorageFree |Szabad tárterület cserélhető tárolón (bájt) |
| RemovableStorageTotal |Összes tárterület cserélhető tárolón (bájt) |
| DeviceMemoryDeviceCapacity |Eszköz memóriakapacitása |
| DeviceMemoryAvailableDeviceCapacity |Eszköz rendelkezésre álló memóriakapacitása |
| DeviceOSVersion |Operációs rendszer verziója |
| DeviceOSPlatform |Operációs rendszer platformja |
| DeviceOSLanguage |Operációs rendszer megjelenítési nyelve |
| PasswordMaxAttemptsBeforeWipe |Jelszó-próbálkozások maximálisan engedélyezett száma az eszközön lévő adatok törlése előtt |
| PasswordMinComplexChars |A jelszóban használandó speciális karakterek minimális száma |
| PasswordMinLength |Jelszó minimális megkövetelt hossza |
| PasswordHistory |Jelszó – legalább ennyi korábbi jelszó nem használható |
| PasswordEnabled |Jelszó – Engedélyezett? |
| PasswordExpiration |Jelszó – Lejárat dátuma |
| AllowRecoveryPassword |Jelszó-visszaállítás engedélyezése |
| PasswordAutoLockTimeout |Jelszó – Automatikus lezárás időkorlátja |
| PasswordType |Jelszótípus |
| BacklightACTimeout |Háttérvilágítás időkorlátja áramforrásról üzemeltetve |
| BacklightBatTimeout |Háttérvilágítás időkorlátja akkumulátorról üzemeltetve |
| PowerBackupPercent |Energiatartalék százalékban |
| BatteryPercent |Akkumulátortöltés százalékban. |
| PlatformID |Platformazonosító |
| ExchangeDeviceID |Exchange-eszközazonosító |
| SmsProcessorDescription |Processzor leírása |
| OwnerEmailAddress |Tulajdonos e-mail-címe |
| DeviceOSName |Operációs rendszer neve |
| WifiMac |WiFi MAC-címe |
| EthernetMac |Ethernet MAC-cím |
| RequireEncryption |Jelzi, hogy az eszköz titkosítva van-e. |
| ActivationLockBypassCode |Kód az aktiválási zár megkerüléséhez |

## <a name="applicationinventory"></a>ApplicationInventory

Az **ApplicationInventory** entitás a leltárkészítés pillanatában az eszközön talált alkalmazásokat sorolja fel.

| Tulajdonság  | Leírás |
|---------|------------|
| DeviceKey |Hivatkozás az Eszközök táblára |
| ApplicationKey |? (ExchangeDeviceService\DeviceApplication helyről másolva) |
| ApplicationName |? (ExchangeDeviceService\DeviceApplication helyről másolva) |
| ApplicationVersion |? (ExchangeDeviceService\DeviceApplication helyről másolva) |
| BundleSize |? (ExchangeDeviceService\DeviceApplication helyről másolva) |