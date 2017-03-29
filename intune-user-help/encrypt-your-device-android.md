---
title: "Androidos eszközök védelme titkosítással | Microsoft Docs"
description: "Androidos eszköz védelme"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: 8ba85e15fb55a4de1b2f1db53bc5b9962de84394
ms.lasthandoff: 03/13/2017


---


# <a name="how-to-protect-your-android-device-using-encryption"></a>Androidos eszközök védelme titkosítással

Egy eszköz titkosításakor a rajta lévő információt egy védelmi kódréteg veszi körül, amely megakadályozza, hogy illetéktelenek férjenek hozzá. Az információbiztonság érdekében a munkahelye az androidos eszközök titkosítását követeli meg Öntől, mielőtt hozzáférhetne a vállalati fájlokhoz, e-mailekhez és adatokhoz.

> [!Note]
> Ha a rendszergazda ezt kéri, előfordulhat, hogy egy PIN-kódot vagy jelszót kell beállítania a titkosítás megkezdése előtt.

Ha megszünteti a telefonja regisztrációját, a titkosítás megmarad.

1.  Győződjön meg arról, hogy a képernyő-zárolási PIN-kód vagy jelszó be van állítva az eszközön.

2.  A **Beállítások** menüben válassza ki a **Biztonság** &gt; **Eszköz titkosítása** lehetőséget.
    (Egyes telefonokon a **Tárolás** &gt; **Tárolás titkosítása** vagy a **Tárolás** &gt; **Zárolási képernyő és biztonság** &gt; **További biztonsági beállítások** menüben található a „Titkosítás” opció).

3.  Kövesse a képernyőn megjelenő utasításokat. Előfordulhat, hogy a titkosítás során az eszköz többször újraindul.

> [!Note]
> Bizonyos Android-eszközöket nem lehet titkosítani. További információért [kattintson ide](your-device-appears-encrypted-but-cp-says-otherwise-android.md).

### <a name="what-to-do-if-you-have-issues"></a>Mi a teendő ha problémába ütközik?
**Probléma:** Már titkosította az eszközt, és a következők egyikét látja:

- A titkosítási gomb le van tiltva.
- Egy üzenet azt jelzi, hogy titkosítania kell az eszközt.
- Hibaüzenet jelenik meg a Vállalati portál alkalmazás használatakor.

**Az alábbiakkal próbálkozhat**

- Ellenőrizze, hogy az eszköz fel van-e töltve és csatlakoztatva van-e.
- Ellenőrizze, hogy beállított-e PIN-kódot vagy jelszót az eszközön.
- Ha már beállította a PIN-kódot vagy jelszót, próbálkozzon az alábbi lépésekkel, amelyeket a rendszergazda megkövetelhet az eszköz biztonságosabbá tételéhez. A lépésekben szereplő menünevek kissé eltérhetnek az eszközön láthatóaktól, attól függően, hogy milyen Android-eszközt használ.

    1. Válassza a **Settings** (Beállítások) > **Security** (Biztonság) > **Screen lock** (Képernyőzár) lehetőséget. Erősítse meg jelenlegi PIN-kódját vagy jelszavát.

    2. A **Choose screen lock** (Képernyőzár kiválasztása) képernyőn válassza ki a használni kívánt képernyőzárat.

    3. A **Secure start-up** (Biztonságos indítás) képernyőn koppintson a **Require PIN to start device** (PIN-kód kérése az eszköz indításához), majd a **Continue** (Folytatás) elemre.

    4. Adjon meg egy PIN-kódot (a korábban megadott PIN-kódot is beírhatja), és koppintson a **Confirm your PIN** (PIN-kód megerősítése) elemre.

    5. Nyissa meg a Vállalati portál alkalmazást, jelölje ki az eszközét, és koppintson a **Megfelelőség ellenőrzése** elemre.

További segítségre van szüksége? Forduljon a rendszergazdához (a kapcsolattartási adatokat a [Munkahelyi portál webhelyén](http://portal.manage.microsoft.com) találja), vagy írjon a <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-csapatának</a>.
