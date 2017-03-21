---
title: "IMEI azonosítók hozzáadása az Intune-hoz"
titleSuffix: Intune Azure preview
description: "Azure-beli Intune –előzetes: Ez a témakör azt ismerteti, hogyan lehet céges azonosítókat (IMEI-számokat) felvenni a Microsoft Intune-ba. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: d8cb15d1b8c1c100f15084e43d2c3c4633fd64b5
ms.openlocfilehash: f12d538b1f4cd327b893d234f2b558185cdd9d85
ms.lasthandoff: 03/09/2017

---

# <a name="add-corporate-identifiers"></a>Vállalati azonosítók felvétele

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A céges eszközök azonosítására listát készíthet az IMEI-számokról. Az eszközök lehetnek regisztráltak vagy sem, és ennek megfelelően állapotuk lehet „Regisztrálva” vagy „Nem történt kapcsolatfelvétel”. Utóbbi állapot azt jelenti, hogy az eszköz nem egyeztet adatokat az Intune szolgáltatással.

Hozzon létre egy kétoszlopos, fejléc nélküli listát .csv formátumban. A baloldali oszlopban tüntesse fel az IMEI-azonosítót, a jobb oldaliban pedig a további adatokat. A lista jelenlegi maximális mérete 500 sor.

Szövegszerkesztőben a .csv-fájl az alábbihoz hasonlóan jelenik meg:

01 234567 890123,eszközadatok</br>
02 234567 890123,eszközadatok

**Céges azonosítók .csv-listájának felvétele**

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Céges készülékazonosítók** elemet.

3. Ha olyan fájlt importál, amely a régieket felülíró új adatokat tartalmaz, válassza a **Meglévő azonosítók adatainak felülírása** lehetőséget, így az új adatok felülírják a jelenlegieket.

4. Keresse meg az IMEI-számok CSV-fájlját, és válassza a **Hozzáadás** elemet.

> [!IMPORTANT]
> Bizonyos androidos eszközök több IMEI-számmal rendelkeznek. Az Intune eszközönként egy IMEI-számot vesz leltárba. Ha olyan IMEI-számot importál, amely nem egyezik meg az eszköz az Intune által leltározott IMEI-számával, az eszköz nem vállalati, hanem személyes eszközként lesz besorolva. Ha egy eszközhöz több IMEI-számot importál, a nem leltározott számok **Ismeretlen** regisztrációs állapottal jelennek meg.

**Céges azonosítók .csv-listájának törlése**

1. Az Azure Portalon válassza a **További szolgáltatások** > **Figyelés + felügyelet** > **Intune** lehetőséget.

2. Válassza az Intune panel **Eszközök regisztrálása** elemét, majd a **Céges készülékazonosítók** elemet.

3. Válassza a **Törlés** elemet.
