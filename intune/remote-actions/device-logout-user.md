---
title: iOS-eszköz felhasználójának kijelentkeztetése
titleSuffix: Microsoft Intune
description: Ez a cikk ismerteti, hogy hogyan lehet kijelentkeztetni egy Intune által felügyelt iOS-eszköz aktuális felhasználóját.”
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8336f5b29cd21bb6875285177071542080eb95f3
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509455"
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Intune által felügyelt iOS-eszköz aktuális felhasználójának kijelentkeztetése


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Az **Aktuális felhasználó kijelentkeztetése** művelet kijelentkezteti egy megosztott iPad aktuális felhasználóját. 

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – nem támogatott
- Windows Phone – nem támogatott
- iOS – az iOS 9.3-as és újabb verzióiban támogatott (csak megosztott iPad eszközökön)
- macOS – nem támogatott
- Android – nem támogatott

## <a name="how-to-log-out-the-current-user"></a>Aktuális felhasználó kijelentkeztetése

1. Jelentkezzen be az Azure Portalra.
2. Válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.
3. Az **Intune** panelen válassza az **Eszközök** lehetőséget.
4. Az **Eszközök és csoportok** panelen válassza a **Minden eszköz** lehetőséget.
5. A felügyelt eszközök listájából válasszon ki egy iOS-eszközt, majd kattintson az **Aktuális felhasználó kijelentkeztetése** távoli eszközműveletre.

## <a name="next-steps"></a>További lépések

A kezdeményezett művelet állapotát az **Eszközök és csoportok** panel **Eszközműveletek** szakaszában tekintheti meg.