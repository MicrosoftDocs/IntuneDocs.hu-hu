---
title: "A Windows Team konfigurációs házirendjének beállításai | Microsoft Docs"
description: "Regisztrált Windows 10 Team eszközök, például a Microsoft Surface Hub beállításainak konfigurálására használhatja a **Windows 10 Team eszközökhöz készült általános konfigurációs házirendjét**."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 24a64db3a3cf97b679ab0fa739eb6f452499ca63
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>A Windows Team konfigurációs házirendjének beállításai a Microsoft Intune-ban

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Regisztrált Windows 10 Team eszközök, például a Microsoft Surface Hub beállításainak konfigurálására használhatja a **Windows 10 Team eszközökhöz készült általános konfigurációs házirendjét**.

|Beállítás neve|Részletek|
|----------------|-----------|
|**Képernyő felébresztésének engedélyezése, ha valaki van a helyiségben**|Lehetővé teszi az eszköz automatikus felébresztését, ha az érzékelők valakit észlelnek a helyiségben.|
|**PIN-kód kérése vezeték nélküli vetítéshez**|Meghatározza, hogy meg kell-e adni a PIN-kódot az eszköz vezeték nélküli vetítési funkcióinak használata előtt.|
|**Karbantartási időszak megadása az eszközfrissítésekhez**|Meghatározza, hogy mely időszakban kerül sor az eszköz frissítéseire. Beállíthatja a kezdési időt és az időtartamot (1-5 óra) is.|
|**Az Azure-os Operational Insights engedélyezése**|A Microsoft Operations Manager csomag részét képező Azure-os Operational Insights naplófájladatokat gyűjt, tárol és elemez a from Windows 10 Team-eszközökről.<br /><br />Az Azure-os Operational Insights szolgáltatáshoz végzett csatlakozáshoz meg kell adnia egy **munkaterület-azonosítót** és egy **munkaterületkulcsot**.|
|**Miracast vezeték nélküli vetítés engedélyezése**|Engedélyezze ezt a lehetőséget, hogy a Windows 10 Team-eszköz Miracast technológiát használó eszközökkel vetíthessen.<br /><br />Ha engedélyezi ezt a lehetőséget, a **Válasszon Miracast-csatornát** területen válassza ki a tartalom vetítéséhez használni kívánt Miracast-csatornát.|
|**Az üdvözlőképernyőn megjelenő értekezletadatok kiválasztása**|Ha engedélyezi ezt a lehetőséget, kiválaszthatja az **Üdvözöljük** képernyő **Értekezletek** csempéjén megjelenő adatokat. A következőket teheti:<br /><br />-   **Csak szervező és időpont megjelenítése**<br />-   **Szervező, időpont és tárgy megjelenítése (zártkörű értekezletek esetén a tárgy rejtett)**|
|**Zárolási képernyő háttérképének URL-címe**|Engedélyezze ezt a beállítást, ha az Ön által megadott URL-címről egy egyéni hátteret szeretne megjeleníteni a Windows 10 Team-eszközök **Üdvözöljük** képernyőjén.<br /><br />A képnek PNG formátumban kell lennie, és az URL-címnek a **https://** karakterlánccal kell kezdődnie.|


### <a name="see-also"></a>További információ
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-szabályzatok használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

