---
title: Eszközök újraindítása az Azure-beli Microsoft Intune-ban | Microsoft Docs
description: Újraindíthatja a Windows- és iOS-eszközöket a Microsoft Intune használatával az Azure Portalon az Újraindítás távoli művelettel.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 42908f09dd47a22f1c545b60a97ca5e6b7fa068f
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508640"
---
# <a name="remotely-restart-devices-with-intune"></a>Az eszközök távoli újraindítása az Intune-nal


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Az **újraindítási** eszközművelettel a kiválasztott eszköz újraindítható. Az eszköz tulajdonosa nem kap automatikus értesítést az újraindításról, ezért a munkája elveszhet.

## <a name="supported-platforms"></a>Támogatott platformok

- Windows – A Windows 8.1-es és újabb verziói esetén támogatott
- Windows Phone – A Windows Phone 8.1-es és újabb verziói esetén támogatott
- Androidos kioszk-eszközök – az Android 7,0-es és újabb verzióiban támogatott
- iOS – támogatott

    > [!Note]  
    > Ehhez a parancshoz felügyelt eszközökre és az **Eszközzárolás** hozzáférési jogosultságra van szükség. Az eszköz azonnal újraindul. Újraindítás után a PIN-kóddal zárolt iOS-eszközök nem csatlakoznak újra a Wi-Fi-hálózathoz. Újraindítás után az eszköz lehet, hogy nem fog tudni kommunikálni a kiszolgálóval.
- macOS – nem támogatott
- Androidos és androidos munkahelyi profillal rendelkező eszközök – nem támogatottak

## <a name="restart-a-device"></a>Eszköz újraindítása

1. Jelentkezzen be az [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)-ba.
3. Válassza az **Eszközök** > **Minden eszköz** lehetőséget.
4. A kezelt eszközök listájában válasszon ki egy eszközt, válassza a **További** lehetőséget, majd az **Újraindítás** távoli eszközműveletet.

## <a name="next-steps"></a>További lépések

- Az **Újraindítás** eszközművelet állapotának megtekintéséhez válassza az **Eszközök** > **Eszközműveletek** lehetőséget.