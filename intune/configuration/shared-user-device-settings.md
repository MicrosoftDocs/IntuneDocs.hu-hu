---
title: Megosztott vagy többfelhasználós eszközbeállítások a Microsoft Intuneban – Azure | Microsoft Docs
description: Windows 10 és Windows holografikus for Business rendszerű eszközök hozzáadása és használata, amelyeket megosztanak vagy több felhasználó használ Microsoft Intuneban. Tekintse meg az összes beállítás listáját, valamint azt, hogy mit csinálnak az eszközökön, beleértve a Microsoft HoloLens is. A vendég fiókjainak vezérlése, a fiókok kezelése és az inaktív fiókok törlése, a helyi tárterületre való mentés engedélyezése vagy letiltása, energiaellátási és alvó üzemmódok beállítása, a frissítések telepítésének engedélyezése és az eszközök használata az oktatási környezetekben az eszköz konfigurációs profiljában.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b8dfab31d770c012acf88eb3775313634c3c14cc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72492299"
---
# <a name="control-access-accounts-and-power-features-on-shared-pc-or-multi-user-devices-using-intune"></a>A megosztott SZÁMÍTÓGÉPeken és a többfelhasználós eszközökön lévő hozzáférés, fiókok és energiaellátási funkciók vezérlése az Intune-nal

A több felhasználóval rendelkező eszközöket megosztott eszközöknek nevezzük, és a mobileszköz-felügyeleti (MDM) megoldások közös részét képezik. A Microsoft Intune használatával testreszabhatja a következő platformokat futtató megosztott eszközöket:

- Windows 10 Professional és újabb
- Windows 10 Enterprise és újabb verziók
- Windows holografikus vállalatoknak, például a HoloLens

Például az iskolák olyan eszközökkel rendelkeznek, amelyeket általában sok diák használ. Ezzel a beállítással a School Intune-rendszergazda bekapcsolhatja a megosztott számítógép szolgáltatást, hogy egyszerre egy felhasználó számára is lehetővé váljon. A tanulók nem válthatnak az eszközön lévő különböző bejelentkezett fiókok között. Ha a tanuló kijelentkezik, az összes felhasználóra vonatkozó beállítást is eltávolítja.

A végfelhasználók a vendég fiókkal is bejelentkezhetnek ezekre a megosztott eszközökre. A felhasználók bejelentkezését követően a rendszer gyorsítótárazza a hitelesítő adatokat. Az eszköz használatakor a végfelhasználók csak az Ön által engedélyezett funkciókhoz férhetnek hozzá. Ha például az eszköz alvó módba lép, ha a felhasználók helyileg láthatják és menthetik a fájlokat, engedélyezheti vagy letilthatja az energiagazdálkodási beállításokat, és így tovább. Azt is szabályozhatja, hogy a vendég fiók törli-e a felhasználót, amikor a felhasználó kijelentkezik vagy törli az inaktív fiókokat a küszöbérték elérésekor.

Ebből a cikkből megtudhatja, hogyan hozhat létre konfigurációs profilt, és az elérhető beállításokra mutató hivatkozásokat is tartalmaz a leírásuk alapján.

Ha a profilt az Intune-ban hozza létre, a profilját üzembe helyezheti vagy hozzárendelheti a szervezetben lévő eszközökhöz. Ezt a profilt vegyes típusú és operációsrendszer-verziókkal rendelkező eszközök csoportjaihoz is hozzárendelheti.

## <a name="create-the-profile"></a>A profil létrehozása

1. Jelentkezzen be az [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)-ba.
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg a következő tulajdonságokat:

   - **Név**: Adja meg az új profil leíró nevét.
   - **Leírás:** Itt adhatja meg a profil leírását. A beállítás használata nem kötelező, de ajánlott.
   - **Platform**: válassza **a Windows 10 és újabb**lehetőséget.
   - **Profil típusa**: válassza a **megosztott többfelhasználós eszköz**lehetőséget.

4. Konfigurálja a [Windows 10 és újabb](shared-user-device-settings-windows.md) vagy a [Windows holografikus for Business](shared-user-device-settings-windows-holographic.md)beállításait.

5. A módosítások mentéséhez válassza az **OK** > **Létrehozás** lehetőséget.

A profil létre lett hozva és megjelenik a listában, de még nem csinál semmit. Ügyeljen arra, hogy a profilt a szervezetében lévő eszközök csoportjaihoz [rendelje](device-profile-assign.md) .

## <a name="next-steps"></a>További lépések

- Tekintse meg a [Windows 10 és újabb](shared-user-device-settings-windows.md) és a [Windows holografikus for Business](shared-user-device-settings-windows-holographic.md)összes beállítását.
- [Rendelje hozzá a profilt](device-profile-assign.md), és [kövesse nyomon az állapotát](device-profile-monitor.md).