---
title: "Eszközkorlátozásokra vonatkozó beállítások az Intune-ban macOS esetén"
titleSuffix: Intune Azure preview
description: "Intune az Azure-on – előzetes: Az Intune azon beállításainak ismertetése, melyekkel szabályozhatók az eszközbeállítások és a funkciók a macOS rendszerű eszközökön."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: e6b308547331e20a8373aca56f9a0781dcd210a2
ms.lasthandoff: 02/18/2017


---

# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>A macOS eszközkorlátozásokra vonatkozó beállításai a Microsoft Intune-ban

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="password"></a>Jelszó
-     **Jelszó megkövetelése** – Megköveteli a végfelhasználótól, hogy jelszót adjon meg az eszköz eléréséhez.
    -     **Megkövetelt jelszótípus** – Megadja, hogy a jelszó csak numerikus lehet-e, vagy alfanumerikusnak kell lennie (azaz betűket és számokat is tartalmaznia kell). Ezt a beállítást csak a Mac OS X 10.10.3-as és újabb verziói támogatják.
    -     **Nem alfanumerikus karakterek száma a jelszóban** – Megadja, hogy hány speciális karakternek (**0** - **4**) kell szerepelnie a jelszóban.<br>A speciális karakterek szimbólumok, mint például a kérdőjel (**?**).
    -     **Jelszó minimális hossza** – Megadja a felhasználó által beállítandó jelszó minimális hosszát (**4** és **16** karakter között).
    -     **Egyszerű jelszavak** – Az egyszerű jelszavak (például a **0000** vagy az**1234**) használatának engedélyezése.
    -     **Jelszó kérése legfeljebb ennyi perccel a képernyőzárolás után** – Megadja, hogy a számítógépnek mennyi ideig kell inaktívnak lennie ahhoz, hogy bekapcsoljon a jelszavas zárolás.
    -     **Képernyőzárolás legfeljebb ennyi perc inaktivitás után** – Meghatározza, hogy a számítógépnek mennyi ideig kell tétlennek lennie a képernyő zárolása előtt.
    -     **Jelszó lejárata (napokban)** – Megadja, hogy hány nap elteltével kötelező a felhasználónak módosítania a jelszót (**1** **255** nap).
    -     **Korábbi jelszavak újbóli használatának tiltása** – Meghatározza, hogy hány korábbi jelszó ne legyen újra felhasználható (**1** - **24**).

## <a name="restricted-apps"></a>Korlátozott alkalmazások

A korlátozott alkalmazások listájában a következő listák valamelyikét konfigurálhatja:

A **Letiltott alkalmazások** listája – Azokat a nem az Intune által kezelt alkalmazásokat tartalmazza, amelyeknek a telepítése és futtatása nincs engedélyezve a felhasználók számára.
A **Jóváhagyott alkalmazások** listája – Azokat az alkalmazásokat tartalmazza, amelyeknek a telepítése engedélyezve van a felhasználók számára. A megfelelőség biztosítása érdekében a felhasználók nem telepíthetnek olyan alkalmazásokat, amelyek nem szerepelnek a listán. Az Intune által kezelt alkalmazások automatikusan engedélyezettek.

A lista konfigurálásához kattintson a **Hozzáadás** gombra, adja meg a kívánt nevet, igény szerint az alkalmazás kiadóját, valamint az alkalmazás csomagazonosítóját (például *com.apple.calculator*).


