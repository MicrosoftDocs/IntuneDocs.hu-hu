---
title: "Az Intune AirPlay-beállításai iOS-eszközökhöz"
titleSuffix: Intune Azure preview
description: "Ismerje meg, hogyan segítheti az Intune az iOS-es eszközök automatikus csatlakoztatását AirPlay-kompatibilis eszközökhöz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: f1f7aa6a0b441b51f20d104c4353a1542a9e01ad
ms.lasthandoff: 04/19/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>Az Intune AirPlay-beállításai iOS-eszközökhöz

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ezekkel a beállításokkal segítheti a felügyelt iOS-es eszközök AirPlay-kompatibilis eszközökhöz (például AppleTV-khez) való csatlakoztatását.
A képesség a következőket teszi lehetővé:

- **Eszköz- és jelszólista konfigurálása** – az eszközöket elláthatja az AirPlay-eszközök nevével és jelszavával, így automatikusan csatlakozhatnak hozzájuk a vételkörzetben. Ha a jelszót is megadja, a felhasználóknak nem kell beírniuk a csatlakozáskor.
- **Engedélyezett célhelyek konfigurálása** – Összeállíthatja az engedélyezett AirPlay-eszközök listáját (az eszközazonosítók alapján). A végfelhasználók (a felügyelt eszközökön) csak a felsorolt eszközöket látják és érik el.

## <a name="get-started"></a>Első lépések

1. Az **Eszközfunkciók** panelen válassza az **AirPlay** elemet.
2. Az **AirPlay** panelen tegye a következők egyikét vagy mindkettőt:

## <a name="configure-a-device-and-password-list"></a>Eszköz- és jelszólista konfigurálása

1. A **Jelszavak** panelen töltse ki az AirPlay-eszközhöz (pl. **Contoso Apple TV**) tartozó **Eszköznév** és **Jelszó** mezőt.
2. Az összes eszközadat megadása után kattintson a **Hozzáadás** elemre. Az eszköz megjelenik az **Eszköznév** listában.
3. Folytassa az eszközök hozzáadását. Ha elkészült, válassza az **OK** elemet.


## <a name="configure-allowed-destinations"></a>Engedélyezett célhelyek konfigurálása

1. Az **Allowed destinations (supervised only)* (Engedélyezett célhelyek (csak felügyelt eszközökhöz)) panelen adja meg az AirPlay-eszköz **Device ID** (Eszközazonosító) értékét, például: 52:46:CD:51:83:4C.
2. Az eszközazonosító megadása után kattintson a **Hozzáadás** elemre. Az azonosító megjelenik az **Eszközazonosító** listában.
3. Folytassa az eszközök hozzáadását. Ha elkészült, válassza az **OK** elemet.

Az eszközöket és jelszavakat, illetve az engedélyezett célhelyeket vesszővel tagolt szövegfájlból (csv-ből) is importálhatja.


