---
title: "Eszközök védelme | Microsoft Intune"
description: "Megismerhet néhány módot, amelyek segítségével az Intune segít megvédeni az eszközét a jogosulatlan hozzáféréstől és más fenyegetésektől."
keywords: 
author: Robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 5c82e905afeab2d7da8a2e9cebf651ed3c8ce21c


---

# Eszközök védelme a Microsoft Intune-nal

A Microsoft Intune teljes körű funkcionalitást biztosít a kezelt eszközök és az azokon tárolt adatok védelméhez. A jelen témakör áttekinti az e funkciókkal kapcsolatos alapismereteket és tájékoztat az azokkal kapcsolatos további információkról.

## Általános módszerek az összes eszköz védelmére

### Eszközök konfigurálása
Az Intune [konfigurációs szabályzatai](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) egy sor beállítás és funkció ellenőrzésével járulnak hozzá az eszközök védelméhez. Példa:
- Korlátozhatja az eszköz hardveres funkcióit, például a kamera vagy a Bluetooth használatát.
- Megfelelő és nem megfelelő alkalmazásokat konfigurálhat. Nem megfelelő alkalmazás telepítése esetén riasztást kap (és egyes platformok képesek ténylegesen megakadályozni a telepítést).

### PIN-kódok alaphelyzetbe állítása a felhasználók eszközökről való kizárása esetén
Mivel a mobileszközökön lévő vállalati adatok védelmének legfontosabb eleme a hitelesítő kódok használatának megkövetelése, időnként [alaphelyzetbe kell állítania a hitelesítő kódot](use-remote-lock-and-passcode-reset-in-microsoft-intune.md), vagy ehhez segítséget kell nyújtania az alkalmazottnak a hitelesítő kód eltávolításával vagy ideiglenes jelszó távolról történő beállításával. Elvesztés vagy lopás esetén [távolról is zárolhatja az eszközöket](use-remote-lock-and-passcode-reset-in-microsoft-intune.md).

### Eszközök kivonása és adatok eltávolítása
Ha egy eszközt [ki kell vonni az Intune-felügyelet alól](retire-devices-from-microsoft-intune-management) (például azért, mert a felhasználó távozik a vállalattól, vagy mert az eszköz elvész vagy ellopják), valószínű, hogy szükség van az adatok eltávolítására az eszközről. Az Intune egy sor módszert kínál a vállalati adatok biztonságának megőrzésére.

### Megfelelőség előírása az eszközök számára
Az Intune olyan [eszközmegfelelőségi szabályzatokat](introduction-to-device-compliance-policies-in-microsoft-intune) biztosít, amelyek segítségével értékelheti (és bizonyos esetekben kijavíthatja) azokat az eszközöket, amelyek nem felelnek meg a meghatározott szabályoknak. Így például jelentést készíthet a függetlenített iOS-eszközökről, arról, hogy az eszközök titkosítottak-e, vagy hogy az Állapotigazolási szolgáltatás a Windows 10-eszközöket kifogástalan állapotúként jelenti-e.

### Az alkalmazások és az általuk használt adatok védelme
Az Intune egy sor funkciót biztosít az alkalmazások és adataik védelmére. Így például a mobilalkalmazás-kezelési (MAM) szabályzatok képesek megakadályozni az adatok biztonsági mentését védett alkalmazásokból, korlátozni a másolást és beillesztést más alkalmazásokba vagy PIN-kód megadását előírni az alkalmazásokhoz való hozzáféréshez. Az alkalmazások védelméről bővebben lásd: [Alkalmazások és adatok védelme a Microsoft Intune-nal](protect-apps-and-data-with-microsoft-intune)

## További lehetőségek Windows-eszközök esetében

### Kiegészítő védelmi réteg hozzáadása Windows rendszerű eszközökhöz
A[többtényezős hitelesítés (MFA)](protect-windows-devices-with-multi-factor-authentication.md) biztonságosabb módszer a hálózatban lévő Windows és Windows Phone rendszerű eszközök felhasználóinak hitelesítésére.  A többtényezős hitelesítés (MFA) szolgáltatás használatakor a felhasználóknak a felhasználónév-jelszó pároson túlmenően egy telefonhívással vagy szöveges üzenettel is igazolniuk kell személyazonosságukat.

### A Vállalati Windows Hello beállításainak szabályozása Windows-eszközökön
Az Intune lehetővé teszi az integrációt a [Vállalati Windows Hello](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (korábban Microsoft Passport) nevű, a Windows 10-ben és későbbi verziókban használható alternatív bejelentkezési módszerrel, amely az Active Directoryt vagy az Azure Active Directory egy fiókját használja jelszó, intelligens kártya vagy virtuális intelligens kártya helyett.

## További lehetőségek iOS-eszközök esetében

### Az aktiválási zár megkerülése iOS-eszközökön
Az aktiválási zár funkció úgy biztosítja a felhasználók eszközeinek védelmét, hogy senki nem törölheti vagy aktiválhatja újra az eszközt addig, amíg meg nem adta a felhasználó Apple ID azonosítóját és jelszavát. Azonban ez problémákkal is járhat, például akkor, ha a felhasználó a zár feloldása nélkül elhagyja a céget. Az [iOS aktiválási zár megkerülésével](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) feloldhatja a felügyelt iOS-eszközök zárolását, így azokat új feladatokhoz használhatja, vagy törölheti a tartalmát.



## Intune ügyfélprogram által felügyelt Windows rendszerű számítógépek védelme
Az Intune továbbra is támogatja az olyan Windows rendszerű számítógépek védelmét, amelyek nincsenek regisztrálva, de felügyeletüket az Intune ügyfélszoftvere biztosítja. Ha szeretné tudni, hogyan segítik ezek a szabályzatok a Windows rendszerű számítógépek védelmét, a [Szabályzatok használata az Intune ügyfélszoftvert futtató Windows rendszerű számítógépek védelméhez](policies-to-protect-windows-pcs-in-microsoft-intune.md) című témakörből tájékozódhat.



<!--HONumber=Oct16_HO4-->

