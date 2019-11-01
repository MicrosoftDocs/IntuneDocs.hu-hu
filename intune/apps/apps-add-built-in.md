---
title: Beépített alkalmazások hozzáadása mobileszközökhöz a Microsoft Intune-nal
titleSuffix: ''
description: Annak ismertetése, hogyan egyszerűsíthető a beépített alkalmazások mobileszközökre való telepítése az Intune használatával.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e494f154c34a4e4866b9eb6980c713da8a7e23b6
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507335"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Beépített alkalmazások hozzáadása a Microsoft Intune-hoz

A *beépített* alkalmazástípus megkönnyíti, hogy válogatott felügyelt alkalmazásokat, például Office 365-alkalmazásokat rendeljen iOS és Android-eszközökhöz. Az alkalmazástípushoz hozzárendelhet adott alkalmazásokat, például az Excel, a OneDrive, az Outlook, a Skype és egyéb alkalmazásokat. Alkalmazás hozzáadása után a megjelenített alkalmazástípus *Beépített iOS-alkalmazás* vagy *Beépített Android-alkalmazás* lesz. A beépített alkalmazástípus használatával kiválaszthatja, hogy mely alkalmazásokat teszi közzé az eszköz felhasználóinak.

Az Intune-konzol korábbi verzióiban az Intune több alapértelmezett felügyelt Office 365-alkalmazást is rendelkezésre bocsátott, például az Outlookot és a OneDrive-ot. Ezen felügyelt alkalmazások alkalmazástípusát a *Felügyelt iOS Store-alkalmazás* vagy *Felügyelt Android-alkalmazás* címke jelölte. Ajánlott ezek helyett a beépített alkalmazástípust használni. A beépített alkalmazástípus használatával rugalmasabban szerkeszthetők és törölhetők az Office 365-alkalmazások.

>[!NOTE]
>A *Felügyelt iOS Store* és *Felügyelt Android-alkalmazás* címkével rendelkező alapértelmezett Office 365-alkalmazásokat az összes hozzárendelés törlése esetén a rendszer eltávolítja az alkalmazáslistából.

## <a name="add-a-built-in-app"></a>Beépített alkalmazás hozzáadása

Beépített alkalmazást a következő módon adhat hozzá az elérhető alkalmazásokhoz a Microsoft Intune-ban:
1. Jelentkezzen be az Azure Portalra.
2. A Microsoft Intune panel megjelenítéséhez válassza a **További szolgáltatások** > **Figyelés és felügyelet** > **Intune** lehetőséget.
3. Az **Intune** ablaktáblán válassza az **Ügyfélalkalmazások** lehetőséget.
4. Az **Ügyfélalkalmazások** panelen a **Kezelés** szakaszban válassza az **Alkalmazások** lehetőséget.
5. Válassza a **Hozzáadás** elemet.
6. Az **Alkalmazás hozzáadása** panelen az **Alkalmazástípus**-listából válassza a **Beépített alkalmazás** lehetőséget.
7. Válassza az **Alkalmazás kiválasztása** lehetőséget.
8. A **Beépített alkalmazás** panelen jelölje ki a belefoglalni kívánt alkalmazásokat.
9. Az **Alkalmazás hozzáadása** panelen válassza a **Hozzáadás** lehetőséget.


## <a name="configure-app-information"></a>Az alkalmazásadatok konfigurálása

Módosíthatja a beépített alkalmazással kapcsolatos információkat. Ezek révén azonosíthatja az alkalmazást az Intune-ban, és segítségükkel a felhasználók is könnyebben megtalálhatják azt a Céges portál alkalmazásban.
1. Az **ügyfélalkalmazások – alkalmazások** panelen válassza ki a módosítani kívánt beépített alkalmazást.  
    Megjelenik a beépített alkalmazás panelje.
2. A **Kezelés** alatt válassza a **Tulajdonságok** lehetőséget.
3. A beépített alkalmazás adatainak módosításához válassza a **Konfigurálás** lehetőséget.
4. Az **Alkalmazásadatok** panelen adja meg az alábbi információkat:
    - **Név**: Itt adhatja meg a beépített alkalmazásnak a céges portálon megjelenő nevét. Ügyeljen arra, hogy csak egyedi neveket használjon. Ha ugyanazt az alkalmazásnevet kétszer adja meg, csak az egyik alkalmazás fog megjelenni a felhasználók számára a céges portálon.
    - **Leírás**: Itt adhatja meg az alkalmazás leírását. 
    - **Kiadó:** Adja meg az alkalmazás kiadójának nevét.
    - **Kategória**: Szükség esetén választhat egyet vagy többet a beépített alkalmazáskategóriák közül. A beállítás megadásával megkönnyítheti a felhasználók számára az alkalmazás megkeresését a céges portálon való böngészés során.
    - **Megjelenítés kiemelt alkalmazásként a Céges portálon**: Ezzel a beállítással hangsúlyosan jelenítheti meg az alkalmazást a Céges portál főoldalán alkalmazásokat kereső felhasználók számára.
    - **Információs URL-cím:** Igény szerint megadhatja az alkalmazással kapcsolatos információkat tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Adatvédelmi nyilatkozat URL-címe:** Igény esetén itt adhatja meg az alkalmazás adatvédelmi nyilatkozatát tartalmazó webhely URL-címét. Ez az URL-cím jelenik meg a felhasználók számára a céges portálon.
    - **Fejlesztő**: Igény esetén megadhatja az alkalmazás fejlesztőjének nevét.
    - **Tulajdonos**: Igény esetén megadhatja az alkalmazás tulajdonosának nevét (például *HR-osztály*).
    - **Megjegyzések**: Ide írhatja be az alkalmazáshoz társítani kívánt megjegyzéseket.
    - **Ikon feltöltése**: Feltölthet egy ikont, mely megjelenik az alkalmazással a céges portálon böngésző felhasználók számára.
4. Válassza az **OK** gombot.
5. A **Tulajdonságok** panelen válassza a **Mentés** lehetőséget.

## <a name="next-steps"></a>További lépések

- Mostantól hozzárendelheti az alkalmazásokat a kiválasztott csoportokhoz. További információ: [Alkalmazások hozzárendelése csoportokhoz](apps-deploy.md).