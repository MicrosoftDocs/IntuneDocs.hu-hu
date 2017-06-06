---
title: "Mit jelent az eszközök regisztrálása a Microsoft Intune-ban"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Útmutató iOS-, Android- és Windows-eszközök regisztrálásához"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 57bad4be991b61fe5212d340ab8d89cb6af3b0f7
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-device-enrollment"></a>Mi az eszközregisztrálás?
[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Ez a témakör az eszközregisztrálást írja le, és felsorolja azokat a különféle módszereket, amelyekkel a mobileszközök regisztrálhatók az Intune-nal való felügyeletre.

Az eszközök Intune-ban való regisztrálásának az a célja, hogy azok felügyelhetők legyenek. Ezt a funkciót mobileszköz-kezelésnek (MDM) nevezzük az Intune dokumentációjában. Az Intune-ban regisztrált eszközök részére a rendszer MDM-tanúsítványt állít ki, amelyet az eszközök az Intune szolgáltatással való kommunikációban használnak.

Az eszköz regisztrálásának módja függ az eszköz típusától, tulajdonosától és az elvárt felügyeleti szinttől. A saját eszközök használatával (BYOD) történő regisztráció lehetővé teszi a felhasználóknak saját, személyes telefonjaik, táblagépeik vagy számítógépeik regisztrálását. Vállalat által birtokolt eszközök (COD) használatával történő regisztráció lehetővé tesz olyan felügyeleti lehetőségeket, mint például az automatikus regisztráció, a megosztott eszközök vagy az előre engedélyezett regisztrációs követelmények.

Ha az Exchange ActiveSyncet használja helyben vagy a felhőben, akkor regisztrálás nélkül is engedélyezheti az egyszerű Intune-felügyeletet (hamarosan további információ válik elérhetővé). A Windows rendszerű számítógépek is kezelhetők mobileszközként. Ez az ajánlott módszer, az alábbiakban leírtak szerint.


## <a name="overview-of-device-enrollment-methods"></a>Az eszközök regisztrálási módszereinek áttekintése

Az alábbi táblázat bemutatja az Intune regisztrációs módszereit, és az egyes módszerekhez kapcsolódó lehetőségeket és követelményeket. A lehetőségeket és a követelményeket alább ismertetjük. A táblázatban az alábbi fogalmak szerepelnek:

- **Törlés** – Azt jelzi, hogy törölni kell-e mindent az eszközről ahhoz, hogy a felhasználók regisztrálni tudják. A „törlés” itt az eszköz gyári alaphelyzetének visszaállítását, vagyis az összes adat törlését jelenti. További információ: [Teljes vagy szelektív törlés használata az eszközökön](devices-wipe.md).
- **Affinitás** - Az eszközök felhasználókkal való társítása. Erre a mobilalkalmazás-kezeléshez (MAM) és a vállalati adatokhoz való feltételes hozzáféréshez van szükség. További információk: [Felhasználói affinitás](device-enrollment-program-enroll-ios.md).
- **Zárolás** – Jelzi, hogy a rendszer megakadályozza a felhasználókat abban, hogy töröljék eszközeik regisztrációját, és ezzel kivonják azokat a felügyelet alól. A felhasználók a Céges portál alkalmazás használatával bármelyik platformon törölhetik eszközeik regisztrációját. A natív operációs rendszer menüit nem használhatják a regisztráció törlésére.


**iOS-eszközök regisztrálási módszerei**

| **Módszer** |    **Törölni kell?** |    **Affinitás**    |    **Zárolás** | **Részletek** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem|    Igen |    Nem | Hamarosan további információ válik elérhetővé|
|**[DEM](#dem)**|    Nem |Nem |Nem    | [További információ](device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|    Igen |    Nem kötelező megadni |    Nem kötelező megadni|[További információ](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**|    Igen |    Nem kötelező megadni |    Nem| [További információ](apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**|    Nem |    Nem    | Nem|[További információ](apple-configurator-direct-enroll-ios.md)|

**Windows-eszközök regisztrálási módszerei**

| **Módszer** |    **Törölni kell?** |    **Affinitás**    |    **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem |    Igen |    Nem | [További információ](windows-enroll.md)|
|**[DEM](#dem)**|    Nem |Nem |Nem    |[További információ](device-enrollment-manager-enroll.md)|

**Android-eszközök regisztrálási módszerei**

| **Módszer** |    **Törölni kell?** |    **Affinitás**    |    **Zárolás** | **Részletek**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nem|    Igen |    Nem | [További információ](android-enroll.md)|
|**[DEM](#dem)**|    Nem |Nem |Nem    |[További információ](device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Nem | Igen | Nem| [További információ](android-enroll.md) |


## <a name="byod"></a>BYOD
A saját eszközeiket használó („BYOD”) felhasználók telepítik a Vállalati portál alkalmazást, és ők regisztrálják az eszközt. Ez lehetővé teszi a felhasználók számára a vállalati hálózathoz való kapcsolódást, így csatlakozhatnak a tartományhoz vagy az Azure Active Directoryhoz. A legtöbb platformon és COD-forgatókönyv esetében engedélyeznie kell a BYOD-regisztrálást. Letilthatja a személyes tulajdonban lévő iOS-es és androidos eszközök regisztrálását. Útmutatót a [Típus szerinti korlátozás beállítása](enrollment-restrictions-set.md#set-device-type-restrictions) című cikkben talál.

## <a name="corporate-owned-devices"></a>Vállalati tulajdonú eszközök
A vállalati tulajdonú eszközök (COD) az Azure Portal segítségével kezelhetők. Az iOS-eszközök az Apple által biztosított megoldások segítségével közvetlenül is regisztrálhatók. A rendszergazdák vagy menedzserek bármilyen típusú eszközt regisztrálhatnak az eszközregisztráció-kezelő segítségével. Az IMEI-számmal rendelkező eszközöket azonosítani lehet, és meg lehet jelölni vállalati tulajdonúként, ami lehetőséget nyújt a vállalati tulajdonú eszközök kezelésére.

### <a name="dem"></a>DEM
Az eszközregisztráció-kezelő (DEM) egy speciális felhasználói fiók, amely több vállalati tulajdonú eszköz regisztrációjára és felügyeletére szolgál. A kezelők tudják telepíteni a Vállalati portált és regisztrálni számos, felhasználó nélküli eszközt. További információ a [DEM](device-enrollment-manager-enroll.md) módszerről. ([Vissza a táblázathoz](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Az Apple készülékregisztrációs program (DEP) lehetővé teszi szabályzatok létrehozását és vezeték nélküli központi telepítését a DEP keretében vásárolt és felügyelt eszközökre. Az eszköz regisztrálása akkor történik, amikor a felhasználók első alkalommal bekapcsolják az eszközt, és futtatják rajta az iOS beállítási asszisztens alkalmazást. Ez a módszer támogatja az **iOS Supervised** (Felügyelt) üzemmódot, amely lehetővé teszi a következő funkciókat:

  -    Zárolt regisztráció
  -    Teljes képernyős mód és más speciális konfigurációk és korlátozások

További információ az iOS-eszközök regisztrációjáról:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](enrollment-method-choose-ios.md)
- [iOS-eszközök regisztrálása a Készülékregisztrációs program segítségével](device-enrollment-program-enroll-ios.md)
- [Vissza a fenti táblázathoz](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB-SA
Az Apple Configurator segítségével a rendszergazdák a beállítási asszisztens használatával USB-kapcsolaton keresztül manuálisan előkészíthetnek minden vállalat által birtokolt eszközt. A rendszergazda létrehoz egy regisztrációs profilt, és exportálja azt az Apple Configuratorba. Amikor a felhasználók megkapják az eszközeiket, választhatják a beállítási asszisztens futtatását az eszköz regisztrálásához. Ez a módszer támogatja az **iOS Supervised** (Felügyelt) üzemmódot, amely lehetővé teszi a következő funkciókat:
  -    Zárolt regisztráció
  -    Teljes képernyős mód és más speciális konfigurációk és korlátozások

További információ az iOS-eszközök regisztrációjáról:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](enrollment-method-choose-ios.md)
- [iOS-eszközök regisztrálása az Apple Configurator és a Beállítási asszisztens használatával](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
A közvetlen regisztrációhoz a rendszergazdának a regisztrációs házirend létrehozásához és az Apple Configuratorba való exportálásához manuálisan kell regisztrálnia minden eszközt. Az USB-csatlakozású, vállalati tulajdonú eszközök regisztrálása közvetlenül történik, a gyári beállítások visszaállítása nem szükséges. Az eszközök kezelése felhasználó nélküli eszközökként történik. Nincsenek zárolva, sem felügyelve, és nem támogathatják a feltételes hozzáférést, a függetlenítés észlelését, illetve a mobilalkalmazás-felügyeletet.

További információ az iOS-eszközök regisztrációjáról:

- [Az iOS-eszközök regisztrálási módjának kiválasztása](enrollment-method-choose-ios.md)
- [iOS-eszközök regisztrálása a Configurator és közvetlen regisztráció használatával](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Mobileszköz-kezelés az Exchange ActiveSync és az Intune használatával
Azok a mobileszközök, amelyek nincsenek regisztrálva, de kapcsolódnak az Exchange ActiveSync (EAS) rendszerhez, EAS MDM-szabályzat segítségével kezelhetők az Intune-ban. Az Intune helyszíni vagy felhőalapú Exchange Connector összekötő segítségével kommunikál az EAS-szel. Hamarosan további információ válik elérhetővé.

## <a name="supported-device-platforms-and-browsers"></a>Támogatott eszközplatformok és böngészők

Lásd: [Az Intune által támogatott eszközök és böngészők](https://docs.microsoft.com/intune-classic/get-started/supported-mobile-devices-and-computers)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobileszköz karbantartása az MDM-tanúsítvány lejárta után

Az MDM-tanúsítvány automatikusan megújul, amikor a mobileszköz kommunikál az Intune szolgáltatással. Ha egy mobileszköznek törlik a tartalmát, vagy az eszköz egy bizonyos időn át nem kommunikál az Intune szolgáltatással, akkor az MDM-tanúsítvány nem újul meg. Az eszköz az MDM-tanúsítvány lejárta után 180 nappal törlődik az Azure Portalról.
