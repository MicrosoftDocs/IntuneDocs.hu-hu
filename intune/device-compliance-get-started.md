---
title: "Bevezetés az eszközmegfelelőségbe"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune – előzetes: Ebben a témakörben ismertetjük a Microsoft Intune megfelelőségi szabályzatok létrehozásához szükséges előfeltételeit"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8103df7f-1700-47b4-9a72-c196d2a02f22
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: f59801abf29d15581fcdc577c5320942208595b1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="get-started-with-device-compliance-in-intune-azure-preview"></a>Bevezetés az eszközmegfelelőségbe az Azure-beli Intune előzetesében


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Ebben a témakörben a következőket tekintheti át: 

- Mire lesz szüksége, mielőtt hozzákezdhet az eszközmegfelelőségi szabályzat létrehozásához.
- Vázlatos összefoglaló arról, hogy mit talál és mit intézhet az Azure-beli Intune előzetes verziójában. 

Ha még nem ismeri az eszközmegfelelőség témakörét, célszerű lesz elolvasnia [ezt a fejezetet](device-compliance.md), amely elmagyarázza a fogalmat, és azt is, hogy miképpen használható a szervezetnél.

##  <a name="pre-requisites"></a>Előfeltételek

-   Intune-előfizetés

-   Azure Active Directory-előfizetés

##  <a name="supported-platforms"></a>Támogatott platformok:

-   Android

-   iOS

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

##  <a name="azure-portal-workflow"></a>Az Azure Portal munkafolyamata

Áttekintés arról, hogy miképpen hozhatja létre és kezelheti az eszközmegfelelőséget az Azure-beli Intune előzetes verziójában.

<!---### Overview

When you choose the **Set device compliance** workload, the blade opens with an  **Overview** section that displays a summary view of your compliance policies that you have created and the status of the devices they have been applied to. If you
don’t have any policies configured yet, the overview will just include the various reports but with no data.--->

### <a name="manage"></a>A számítógépeken futó

Létrehozhatja, szerkesztheti és törölheti az eszközmegfelelőségi szabályzatokat. Ugyanitt van lehetősége felhasználókhoz rendelni őket.

<!---### Monitor

This section is a detailed view of what you see in the **Overview**. A list of all the reports are displayed in this section and you can interactively drill down through each of these reports.--->

### <a name="setup"></a>Beállítás

Megfelelőségi állapot érvényességi időtartama

##  <a name="next-steps"></a>További lépések
[Megfelelőségi szabályzat létrehozása Android rendszerhez](compliance-policy-create-android.md)

[Megfelelőségi szabályzat létrehozása Android for Work rendszerhez](compliance-policy-create-android-for-work.md)

[Megfelelőségi szabályzat létrehozása iOS rendszerhez](compliance-policy-create-ios.md)

[Megfelelőségi szabályzat létrehozása Windows rendszerhez](compliance-policy-create-windows.md)
