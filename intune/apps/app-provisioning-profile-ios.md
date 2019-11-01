---
title: iOS-alkalmazáskiépítési profilok a Microsoft Intune-ban
titleSuffix: ''
description: Az Intune biztosítja az eszközöket, amelyek segítségével proaktív módon rendelhet hozzá új kiépítési profilt azokhoz az eszközökhöz, amelyeken hamarosan lejárnak az alkalmazások.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/14/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c0b5f087494e8033cb9645d0a08edd4e1c481a2c
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72584931"
---
# <a name="use-ios-app-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Az iOS-alkalmazáskiépítési profilok segítségével megakadályozhatja, hogy az alkalmazásai lejárjanak

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

## <a name="introduction"></a>Bevezetés

Az iPhone-okhoz és iPadekhez rendelt Apple iOS üzletági alkalmazások beépített kiépítési profillal és a tanúsítvánnyal aláírt kóddal rendelkeznek. Az alkalmazás futtatásakor az iOS ellenőrzi az iOS-alkalmazás integritását, és érvényesíti a kiépítési profil által meghatározott szabályzatokat. A következő érvényesítések zajlanak le:

- **Telepítési fájl integritása** – Az iOS összehasonlítja az alkalmazás részleteit a vállalat aláírási tanúsítványának nyilvános kulcsával. Ha ezek eltérnek, akkor előfordulhat, hogy az alkalmazás tartalma módosult. Ebben az esetben a rendszer nem engedélyezi az alkalmazás futását.
- **Képességek érvényesítése** – Az iOS megkísérli kikényszeríteni az alkalmazásképességeket az alkalmazás telepítési (.ipa) fájljában tárolt vállalati kiépítési profilból (és nem az egyéni fejlesztői kiépítési profilokból).


Az alkalmazások aláírásához használt vállalati aláíró tanúsítvány általában három évig érvényes. A kiépítési profil viszont egy év után lejár. Amíg a tanúsítvány még érvényes, az Intune biztosítja az eszközöket egy új kiépítési profil proaktív hozzárendelésére olyan eszközökhöz, amelyeken már majdnem lejáró alkalmazások vannak.
A tanúsítvány lejárata után újra regisztrálnia kell az alkalmazást egy új tanúsítvánnyal, és be kell ágyaznia egy új kiépítési profilt az új tanúsítvány kulcsával.

Rendszergazdaként belefoglaló vagy kizáró biztonsági csoportokat hozhat létre iOS-alkalmazáskiépítési konfigurációk hozzárendeléséhez. Egy iOS-alkalmazáskiépítési konfigurációt hozzárendelhet például Minden felhasználóhoz, de kizárhatja a vezetői csoportot.

## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>iOS-beli mobilalkalmazás-kiépítési profilok létrehozása

1. Jelentkezzen be az [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)-ba.
2. Az **Intune** panelen válassza az **ügyfélalkalmazások**  >  iOS-**alkalmazás létesítési profiljai**  >  a**profil létrehozása**lehetőséget.
3. Az **alapvető beállítások** lapon adja hozzá a következő értékeket:
    - **Név** – Adjon egy nevet a mobil kiépítési profilnak.
    - **Leírás** – Lehetősége van a házirend ismertetésének megadására.
    - **Profil feltöltése** – válassza a **Megnyitás** ikon lehetőséget, majd válassza ki az Apple [Developer webhelyéről](https://developer.apple.com/)letöltött, `.mobileprovision` kiterjesztésű Apple Mobile-konfigurációs profilt tartalmazó fájlt.

   A **lejárati dátum** a fent hozzáadott Apple Mobile konfigurációs profilban szereplő értékből lesz kitöltve.<br>

   <img alt="Create profile - Basics" src="~/apps/media/app-provisioning-profile-ios/app-provisioning-profile-ios-01.png">

4. Kattintson a **Tovább gombra: hatókör címkék**.<br>
   A **hatókör címkék** lapon opcionálisan konfigurálhatja a hatókör címkéit annak meghatározásához, hogy ki láthatja az iOS-alkalmazások létesítési profilját az Intune-ban. A hatókör-címkékkel kapcsolatos további információkért lásd: [a szerepköralapú hozzáférés-vezérlés és a hatókör-címkék használata a terjesztéshez](../fundamentals/scope-tags.md).
5. Kattintson a **Tovább: hozzárendelések**elemre.<br>
   A **hozzárendelések** lapon a profilt hozzárendelheti a felhasználókhoz és az eszközökhöz. Fontos megjegyezni, hogy a profilokat hozzárendelheti egy eszközhöz, függetlenül attól, hogy az eszközt az Intune felügyeli-e.
6. Kattintson a **Tovább gombra: felülvizsgálat + létrehozás** elemre, és tekintse át a profilhoz megadott értékeket.
7. Ha elkészült, kattintson a **Létrehozás** gombra az iOS-alkalmazás létesítési profiljának létrehozásához az Intune-ban. 

## <a name="next-steps"></a>További lépések

A profilt rendelje hozzá a szükséges iOS-eszközökhöz. További információt az [Eszközprofilok hozzárendelése](../device-profile-assign.md) című útmutató lépéseit használva talál.