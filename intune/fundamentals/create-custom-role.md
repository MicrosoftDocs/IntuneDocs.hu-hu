---
title: Egyéni szerepkör létrehozása az Intune-ban
description: Ismerje meg, hogyan hozhat létre egyéni szerepkört a Microsoft Intuneban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: b60e4d801d09a834e11119260d3054cf43251bbd
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502955"
---
# <a name="create-a-custom-role-in-intune"></a>Egyéni szerepkör létrehozása az Intune-ban

Létrehozhat egy egyéni Intune-szerepkört, amely tartalmazza az adott feladat függvényéhez szükséges engedélyeket is. Például ha egy IT-részleg alkalmazásokat, szabályzatokat, és konfigurációs profilokat kezel, mindezeket az engedélyeket együtt adhatja meg egy egyéni szerepkör segítségével. Egyéni szerepkör létrehozása után [hozzárendelheti](assign-role.md) azt bármely olyan felhasználóhoz, akinek szüksége van rájuk.

A szerepkörök létrehozásához, szerkesztéséhez vagy hozzárendeléséhez a fióknak rendelkeznie kell a következő jogosultságok egyikével az Azure AD-ben:
- **Globális rendszergazda**
- **Intune-beli szolgáltatás-rendszergazda**

## <a name="to-create-a-custom-role"></a>Egyéni szerepkör létrehozása

1. Jelentkezzen be az [Azure Portalon](https://portal.azure.com) az Intune-os hitelesítő adataival.

2. Válassza a bal oldali menü **Minden szolgáltatás** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. Válassza az **Intune** > **szerepkört** > **minden szerepkör** > **Hozzáadás**elemet.

4. Az **Egyéni szerepkör hozzáadása** panelen adja meg az új szerepkör nevét és leírását, majd kattintson az **Engedélyek** elemre.

5. Az **Engedélyek** panelen válassza ki az ehhez a szerepkörhöz használni kívánt engedélyeket.

6. A **hatókör (címkék)** panelen válassza ki a szerepkörhöz tartozó címkéket. Ez a szerepkör hozzáférhet a címkével ellátható erőforrásokhoz is.

7. Ha elkészült, válassza az **OK** gombot.

8. Az **Egyéni szerepkör hozzáadása** panelen kattintson a **Létrehozás** elemre. Az új szerepkör megjelenik az **Intune-szerepkörök – minden szerepkör** panel listájában.

## <a name="next-steps"></a>További lépések
- [Szerepkör társítása felhasználóhoz](assign-role.md)
- [További információ az Intune-beli szerepköralapú hozzáférés-vezérlésről](role-based-access-control.md)