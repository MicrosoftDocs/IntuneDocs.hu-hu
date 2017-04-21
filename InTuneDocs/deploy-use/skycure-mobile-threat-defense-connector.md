---
title: "Skycure Mobile Threat Defense-összekötő | Microsoft Docs"
description: "A vállalati erőforrásokhoz való hozzáférés védelme az eszköz-, a hálózati és az alkalmazáskockázat alapján a Skycure Mobile Threat Defense-összekötővel."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 86fd9d7212277f9524eb4d7f225df2c7beda1313
ms.openlocfilehash: 219369dfdf9d7a82159563d3fe16bb287bc414d7
ms.lasthandoff: 03/21/2017


---

# <a name="skycure-mobile-threat-defense-connector"></a>Skycure Mobile Threat Defense-összekötő

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A Microsoft Intune-nal integrálható, Skycure nevű, veszélyforrások elleni mobileszköz-védelmi megoldás kockázatfelmérése alapján feltételes hozzáféréssel korlátozható a vállalati erőforrások mobil elérése. A kockázatfelmérés a Skycure által az eszközökről gyűjtött telemetriai adatokon alapul, például:

-   Fizikai védelem

-   Hálózatvédelem

-   Alkalmazásvédelem

-   Biztonsági rések elleni védelem

Feltételes hozzáférési szabályzatokat konfigurálhat az Intune eszközmegfelelőségi szabályzataira épülő Skycure-kockázatfelmérés alapján, és ezek révén az észlelt fenyegetések alapján engedélyezheti vagy tilthatja le a nem megfelelő eszközök hozzáférését a vállalati erőforrásokhoz.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Hogyan segíti az Intune és a Skycure a vállalati erőforrások védelmét?

Az Androidra és iOS-re készült Skycure mobilalkalmazás rögzíti a fájlrendszer, a hálózati protokollkészlet, valamint az eszközök és az alkalmazások telemetriai adatait, ha elérhetők, és továbbítja őket a Skycure felhőszolgáltatásnak, amely felméri az eszköz kockázatát a mobil veszélyforrások tekintetében.

Az Intune eszközmegfelelőségi szabályzata tartalmaz egy szabályt a Skycure mobil fenyegetések elleni védelemhez, amely a Skycure kockázatfelmérésén alapul. Ha ez a szabály engedélyezve van, az Intune az engedélyezett szabályzat alapján értékeli az eszköz megfelelőségét.

Amennyiben az eszköz nem megfelelőnek minősül, akkor megszűnik a hozzáférése az olyan erőforrásokhoz, mint az Exchange Online és a SharePoint Online. A Skycure mobilalkalmazás segítséget nyújt a letiltott eszközök felhasználóinak a probléma elhárításához és a vállalati erőforrásokhoz való hozzáférés visszaszerzéséhez.

Az Intune kétféleképpen integrálható a Skycure-ral:

-   Az **alapszintű beállítás** írásvédett mód, amely révén a Skycure vizsgálhatja az Intune-beli eszközöket.

-   A **teljes integráció** lehetővé teszi, hogy a Skycure jelentse az eszközökkel kapcsolatos kockázatokat és a biztonsági incidensek részleteit az Intune-nak.

## <a name="sample-scenarios"></a>Mintaforgatókönyvek

Néhány gyakori helyzet:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Hozzáférés vezérlése rosszindulatú alkalmazások jelentette fenyegetés alapján

Ha az eszközön kártékony alkalmazásokat, például kártevőket észlel a rendszer, a probléma megoldásáig az eszközön letilthatók az alábbiak:

-   Hozzáférés a vállalati e-mailekhez

-   A vállalati fájlok szinkronizálása a OneDrive for Work alkalmazással

-   Hozzáférés vállalati alkalmazásokhoz

**Letiltás kártékony alkalmazás észlelése esetén:**

![A program kártevőt észlelt](../media/mtp/skycure-arch-1.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![A program kártevőt észlelt, hozzáférés megadva](../media/mtp/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Hozzáférés vezérlése hálózati fenyegetés alapján

Észleli a hálózaton a fenyegetéseket, például a **közbeékelődéses (man-in-the-middle)** támadást, és az eszköz jelentette kockázat alapján biztosítja a Wi-Fi-hálózatok elérésének védelmét.

**Wi-Fi-s hálózati elérés letiltása:**

![Wi-Fi-s hálózati elérés letiltása](../media/mtp/skycure-arch-3.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított](../media/mtp/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Hozzáférés vezérlése a SharePoint Online-hoz hálózati fenyegetés alapján

Észleli a hálózaton a fenyegetéseket, például a **közbeékelődéses (man-in-the-middle)** támadást, és az eszköz jelentette kockázat alapján megakadályozza a vállalati fájlok szinkronizálását.

**A SharePoint Online letiltása hálózati fenyegetések észlelése esetén:**

![A SharePoint Online letiltása hálózati fenyegetések észlelése esetén](../media/mtp/skycure-arch-5.png)

**A fenyegetés kiküszöbölését követően a hozzáférés ismét biztosított:**

![A fenyegetés kiküszöbölését követően a SharePoint-hozzáférés ismét biztosított – példa](../media/mtp/skycure-arch-6.png)

## <a name="supported-platforms"></a>Támogatott platformok

-   **Android 4.1 és újabb verziók**

-   **iOS 8 és újabb verziók**

## <a name="pre-requisites"></a>Előfeltételek

-   Prémium szintű Azure Active Directory

-   Microsoft Intune-előfizetés

-   Skycure Mobile Threat Defense-előfizetés

További tájékoztatást a [Skycure webhelyén](https://www.skycure.com/skycure-microsoft-integration/) talál.

## <a name="next-steps"></a>További lépések

Az Intune és a Skycure integrálásához szükséges lépések:

1.  [A Skycure konfigurálása Azure Active Directory-alapú egyszeri bejelentkezés (SSO) használatára](https://docs.microsoft.com/intune/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [Az iOS-es Skycure alkalmazáshoz tartozó alkalmazáskonfigurációs szabályzat letöltése](https://docs.microsoft.com/intune/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [Skycure-alkalmazások, a Microsoft Authenticator és az iOS-es alkalmazáskonfigurációs szabályzat felvétele](https://docs.microsoft.com/intune/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [Skycure-alkalmazások, a Microsoft Authenticator és az iOS-es alkalmazáskonfigurációs szabályzat üzembe helyezése](https://docs.microsoft.com/intune/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [A Skycure és az Intune közötti integráció beállítása](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [A Skycure Mobile Threat Defense engedélyezése az Intune-ban](https://docs.microsoft.com/intune/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [A Skycure Mobile Threat Defense megfelelőségi szabályzatának létrehozása az Intune-ban](https://docs.microsoft.com/intune/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
