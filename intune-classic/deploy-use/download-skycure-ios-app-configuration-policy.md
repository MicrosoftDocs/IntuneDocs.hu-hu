---
title: "Az iOS-es Skycure alkalmazáshoz tartozó alkalmazáskonfigurációs szabályzat letöltése | Microsoft Docs"
description: "Letölthet egy, a végfelhasználókhoz telepített iOS-es Skycure alkalmazásban használható alkalmazáskonfigurációs szabályzatot."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a8e46960a5d469093052148eb457140b3c235d3a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="download-skycure-ios-app-configuration-policy"></a>Az iOS-es Skycure alkalmazáshoz tartozó alkalmazáskonfigurációs szabályzat letöltése

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

##<a name="before-you-begin"></a>Előkészületek

A következő lépések előtt be kell jelentkezni a Skycure Management konzolon.

> [!TIP] 
> Ha Microsoft Internet Explorer 11-et vagy Edge-et használ, akkor lehet, hogy a Skycure Management konzolt InPrivate módban kell megnyitnia.

## <a name="to-download-the-ios-app-configuration-policy"></a>Az iOS-es alkalmazáskonfigurációs szabályzat letöltése

1.  Nyissa meg a [Skycure Management konzolt](https://aad.skycure.com).

2.  Írja be **Skycure-adminisztrátori hitelesítő adatait**, majd kattintson a **Tovább** gombra.

    ![Bejelentkezés a Skycure Management konzolra](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > A Skycure-adminisztrátor felhasználóneve egy olyan e-mail-fiók, amely egyúttal érvényes felhasználói fiókot is jelöl az Azure Active Directoryban. Ellenkező esetben nem fog tudni bejelentkezni. A Skycure az Azure Active Directoryval hitelesíti egyszeri bejelentkezéshez (SSO) az adminisztrátor felhasználónevét.

3.  Kattintson a **Settings** (Beállítások) &gt; **Device Management Integrations** (Eszközfelügyelet-integráció) &gt; **EMM Integration Selection** (EMM-integráció kiválasztása) elemre, válassza a **Microsoft Intune** lehetőséget, és mentse a választást.

2.  Kattintson az **Integration setup files** (Integráció-telepítőfájlok) hivatkozásra, és mentse a létrejövő \*.zip fájlt. A .zip-fájlban található a **skycure\_configuration.plist** fájl, amellyel létrehozható az iOS-es alkalmazáskonfigurációs szabályzat a klasszikus Intune-konzolon.

![A Skycure-integráció telepítőfájljai](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>További lépések

[Skycure-alkalmazások, Microsoft Authenticator alkalmazás és az iOS-es konfigurációs szabályzat felvétele](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)
