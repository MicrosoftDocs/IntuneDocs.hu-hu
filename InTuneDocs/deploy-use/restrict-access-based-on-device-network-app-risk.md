---
title: "A hozzáférés korlátozása mobil veszélyforrások elleni eszközvédelemmel | Microsoft Intune"
description: "A vállalati erőforrásokhoz való hozzáférés korlátozása az eszköz-, a hálózati és az alkalmazáskockázat alapján."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d4cd3d28a9e4c80fb6a2e17856f6dc9230429e70
ms.openlocfilehash: cbd223560810ee1b97966b8bf8da7206cc2a7955


---

# <a name="restrict-access-to-company-resource-based-on-device-network-and-application-risk"></a>A vállalati erőforrásokhoz való hozzáférés korlátozása az eszköz-, a hálózati és az alkalmazáskockázat alapján
A Microsoft Intune tartalmazza a Lookout nevű, beépített veszélyforrások elleni eszközvédelmi megoldást. Az ez által elvégzett kockázatfelmérés alapján korlátozható a vállalati erőforrások mobileszközökről történő elérése. A kockázatfelmérés a Lookout szolgáltatás által gyűjtött, az operációs rendszer biztonsági réseivel, a telepített kártékony alkalmazásokkal és a kártékony hálózati profilokkal kapcsolatos telemetriai adatokon alapul. Az Intune megfelelőségi szabályzatai által engedélyezett, a Lookout által jelentett kockázatértékelés alapján feltételes hozzáférési szabályzatok konfigurálhatók az Intune-ban, és engedélyezhetők vagy letilthatók azok az eszközök, amelyek az észlelt veszélyforrások alapján nem megfelelőnek minősülnek.  

## <a name="what-problem-does-this-solve"></a>Milyen problémára nyújt ez megoldást?
A vállalatoknak és a szervezeteknek meg kell védeniük érzékeny adataikat a folyamatosan keletkező különböző veszélyforrásoktól, így a fizikai, az alkalmazás- és a hálózat alapú fenyegetésektől, valamint az operációs rendszer biztonsági réseitől.

A vállalatok hagyományosan a számítógépeiket védték a rosszindulatú támadásoktól. A mobileszközök olyan új, feltörekvő területet jelentenek, ahol gyakran elégtelen a védelem. Jóllehet a mobilplatformok operációs rendszerei rendelkeznek olyan beépített védelmi technikákkal, mint az alkalmazások elkülönítése és az ellenőrzött alkalmazásáruházak, e platformok továbbra is sebezhetők az egyre kifinomultabb támadásokkal szemben. Ahogy az alkalmazottak egyre nagyobb mértékben használják mobileszközeiket munkára, és érzékeny és értékes információkhoz férnek hozzá ezekkel az eszközökkel, az eszközöket meg kell védeni a kifinomult támadások sokaságától.

Az Intune lehetővé teszi a vállalati erőforrásokhoz és adatokhoz való hozzáférésnek a Lookouthoz hasonló, veszélyforrások elleni védelmi megoldások által biztosított kockázatfelmérés alapján történő korlátozását.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Hogyan segít az Intune és a Lookout veszélyforrások elleni eszközvédelme a vállalati erőforrások védelmében?
A Lookout mobileszközökön futó alkalmazása (Lookout for Work) rögzíti a fájlrendszer, a hálózati protokollkészlet és az eszközök és az alkalmazások telemetriai adatait (ha elérhetők), és továbbítja őket a Lookout veszélyforrások elleni eszközvédelmi felhőszolgáltatásnak, az pedig kiszámítja az eszköz összesített kockázatát a mobil veszélyforrások tekintetében. A Lookout konzolon igény szerint módosítható a fenyegetések kockázatiszint-besorolása.  

Az Intune megfelelőségi szabályzata már tartalmaz egy új szabályt a Lookout fenyegetések elleni eszközvédelemhez, amely a Lookout kockázatfelmérésén alapul. Ha ez a szabály engedélyezve van, akkor a Microsoft Intune az engedélyezett szabályzat alapján értékeli az eszköz megfelelőségét.

Amennyiben az eszköz az értékelés alapján nem felel meg a megfelelőségi szabályzatnak, akkor feltételes hozzáférési szabályzatok segítségével letiltható a hozzáférése az olyan erőforrásokhoz, mint az Exchange Online és a SharePoint Online. A hozzáférés letiltása esetén a rendszer biztosít egy forgatókönyvet a végfelhasználók részére, amelynek segítségével megoldhatják a problémát, és helyreállíthatják hozzáférésüket a vállalati erőforrásokhoz. Ez a forgatókönyv a Lookout for Work alkalmazásból indítható.
## <a name="supported-platforms"></a>Támogatott platformok:
* **Android 4.1 és újabb verziók**, és legyen regisztrálva a Microsoft Intune-ban.
* **iOS 8 és újabb verziók**, és legyen regisztrálva a Microsoft Intune-ban.
A Lookout által támogatott platformokról és nyelvekről [ez a cikk](https://personal.support.lookout.com/hc/en-us/articles/114094140253) nyújt tájékoztatást.

## <a name="prerequisites"></a>Előfeltételek:
* Microsoft Intune- és Azure Active Directory-előfizetés.
* Vállalati előfizetés a Lookout Mobile EndPoint Securityhez.  További információ: [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="example-scenarios"></a>Példaforgatókönyvek
Néhány gyakori helyzet:
### <a name="control-access-based-on-threat-from-malicious-apps"></a>Hozzáférés vezérlése rosszindulatú alkalmazások jelentette fenyegetés alapján:
Rosszindulatú alkalmazások, például kártevők észlelése esetén az eszközön, letiltható:
* Az eszköz hozzáférése a vállalati e-mailekhez a veszélyforrás megszüntetése előtt.
* A vállalati fájlok szinkronizálása a OneDrive for Work alkalmazás segítségével.
* Az eszköz hozzáférése az üzleti szempontból kritikus fontosságú alkalmazásokhoz.

**Hozzáférés letiltása rosszindulatú alkalmazások észlelése esetén:**
![ábra, amely azt mutatja, ahogy a feltételes hozzáférési szabályzat letiltja a hozzáférést, ha az eszköz a rajta észlelt rosszindulatú alkalmazások alapján nem megfelelőnek minősül](../media/mtp/malicious-apps-blocked.png)

**A rendszer feloldja az eszköz letiltását és az eszköz újra hozzáférhet a vállalati erőforrásokhoz a fenyegetés kiküszöbölését követően:**

![ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést, amikor a fenyegetés kiküszöbölését követően az eszköz ismét megfelelőnek minősül](../media/mtp/malicious-apps-unblocked.png)
### <a name="control-access-based-on-threat-to-network"></a>Hozzáférés vezérlése hálózati fenyegetés alapján:
Észleli a hálózat elleni támadásokat, például a közbeékelődéses (man-in-the-middle) támadást, és az eszköz jelentette kockázat alapján korlátozza a Wi-Fi-hálózatok elérését.

**Wi-Fi-hálózaton keresztüli hozzáférés letiltva:**
![ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat a hálózati fenyegetések alapján letiltja a Wi-Fi-hálózat elérését](../media/mtp/network-wifi-blocked.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![ábra, amely azt mutatja, hogy a fenyegetés kiküszöbölését követően a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Hozzáférés vezérlése a SharePoint Online-hoz hálózati fenyegetés alapján:

Észleli a hálózat elleni támadásokat, például a közbeékelődéses (man-in-the-middle) támadást és az eszköz jelentette kockázat alapján megakadályozza a vállalati fájlok szinkronizálását.

**Hozzáférés letiltva a SharePoint Online-hoz az eszközön észlelt fenyegetés alapján:**

![Ábra, amely azt mutatja, hogy a feltételes hozzáférési szabályzat letiltotta az eszköz hozzáférését a SharePoint Online-hoz az észlelt fenyegetés alapján](../media/mtp/network-spo-blocked.png)


**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![Ábra, amely azt mutatja, hogy a hálózati fenyegetés kiküszöbölését követően a feltételes hozzáférési szabályzat ismét engedélyezi a hozzáférést](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>További lépések
A legfontosabb lépések a megoldás megvalósítása érdekében:
1.  [Az előfizetés beállítása a Lookout mobilfenyegetések elleni védelemhez](set-up-your-subscription-with-lookout-mtp.md)
2.  [A Lookout MTP-kapcsolat engedélyezése az Intune-ban](enable-lookout-mtp-connection-in-intune.md)
3.  [A Lookout for Work alkalmazások konfigurálása és központi telepítése](configure-and-deploy-lookout-for-work-apps.md)
4.  [Megfelelőségi szabályzat konfigurálása](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [A Lookout-integráció hibaelhárítása](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Nov16_HO1-->

