---
title: "Alkalmazásvédelmi Windows információvédelmi (WIP-) szabályzat létrehozása és telepítése az Intune használatával | Microsoft Docs"
description: "Alkalmazásvédelmi WIP-szabályzatok létrehozása és telepítése az Intune használatával"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51e53e28-5c34-4d0f-a4b1-6390a337514c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 5f172290d493717308446c4f9e2313a03ba8f3aa
ms.openlocfilehash: 8221f8ccc9aa07c67cd08b3ceb5f10d192cb6aa7
ms.lasthandoff: 04/27/2017


---

# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Alkalmazásvédelmi Windows információvédelmi (WIP-) szabályzat létrehozása és telepítése az Intune használatával

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Az Intune 1704-es kiadásától kezdve regisztráció nélkül használhatja az alkalmazásvédelmi szabályzatokat a mobilalkalmazás-kezelés (MAM) segítségével Windows 10-es rendszerű eszközök esetén.

## <a name="before-you-begin"></a>Előkészületek

Ismerkedjen meg néhány olyan fogalommal, amelyek a WIP-szabályzatok hozzáadásakor merülnek fel.

### <a name="list-of-allowed-and-exempt-apps"></a>Az Engedélyezett és Mentesített alkalmazások listája

-   **Engedélyezett alkalmazások:** ezeknek meg kell felelniük az adott szabályzatnak.

-   **Mentesített alkalmazások:** ezek mentesülnek az adott szabályzat alól, és korlátozás nélkül hozzáférnek a vállalati adatokhoz.

### <a name="types-of-apps"></a>Alkalmazások típusai

-   **Ajánlott alkalmazások:** a szabályzatba egyszerűen importálható (leginkább Office-) alkalmazásokból előre összeállított lista.

-   **Áruházbeli alkalmazások:** a rendszergazda a Windows Áruházból bármilyen alkalmazást felvehet a szabályzatba.

-   **Asztali Windows-alkalmazások:** a rendszergazda bármilyen hagyományos asztali Windows-alkalmazást (exe, dll stb.) felvehet a szabályzatba.

## <a name="pre-requisites"></a>Előfeltételek

Mielőtt WIP-alkalmazásvédelmi szabályzatot hozhatna létre, be kell állítania a MAM-szolgáltatót.

-   További információk a [MAM-szolgáltató konfigurálása az Intune segítségével](https://docs.microsoft.com/intune/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10) témakörben talál.

Emellett rendelkeznie kell a következőkkel:

-   [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) licenc.
-   [Windows Alkotói frissítés](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> A WIP nem támogatja a többszörös identitás használatát, egyidejűleg csak egyetlen felügyelt identitás létezhet.

## <a name="to-add-a-wip-policy"></a>WIP-szabályzat hozzáadása

Miután a vállalatnál beállította az Intune-t, az [Azure Portal](https://docs.microsoft.com/intune/deploy-use/azure-portal-for-microsoft-intune-mam-policies) használatával hozhat létre WIP-szabályzatokat.

1.  Nyissa meg az **Intune mobilalkalmazás-kezelési irányítópultját**, válassza a **Minden beállítás** lehetőséget, majd válassza ki az **Alkalmazásszabályzat** lehetőséget.

2.  Az **Alkalmazásszabályzat** panelen válassza a **Szabályzat hozzáadása** lehetőséget, majd adja meg a következő értékeket:

    a.  **Név:** Adja meg az új szabályzat nevét (kötelező).

    b.  **Leírás:** Adjon meg hozzá leírást (nem kötelező).

    c.  **Platform:** Válassza a **Windows 10** lehetőséget az alkalmazásvédelmi szabályzat támogatott platformjaként.

    d.  **Regisztráció állapota:** Válassza a **Regisztráció nélkül** lehetőséget a szabályzat regisztrációs állapotának.

3.  Válassza a **Létrehozás** lehetőséget. A szabályzat létrejön, és megjelenik az **Alkalmazásszabályzat** panelen található táblázatban.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>Javasolt alkalmazások hozzáadása az engedélyezett alkalmazások listájához

1.  Az **Alkalmazásszabályzat** panelen válassza ki a kívánt szabályzat nevét, majd a **Szabályzat hozzáadása** panelen válassza ki az **Engedélyezett alkalmazások** lehetőséget. Megnyílik az **Engedélyezett alkalmazások** panel, ahol megjelenik azoknak az alkalmazásoknak a listája, amelyekre ez a szabályzat vonatkozik.

2.  Az **Engedélyezett alkalmazások** panelen válassza az **Alkalmazások hozzáadása** lehetőséget. Megnyílik az **Alkalmazások hozzáadása** panel, amelyen láthatja a listában található összes alkalmazást.

3.  Válassza ki azokat az alkalmazásokat, amelyeknek hozzáférést kíván adni a vállalati adatokhoz, majd kattintson az **OK** gombra. Az **Engedélyezett alkalmazások** panel frissül, és kibővül a kiválasztott alkalmazásokkal.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Áruházi alkalmazások hozzáadása az Engedélyezett alkalmazások listájához

**Áruházi alkalmazás hozzáadása**

1.  Az **Alkalmazásszabályzat** panelen válassza ki a kívánt szabályzat nevét, majd válassza az **Engedélyezett alkalmazások** lehetőséget a megjelenő menüben, amely az alkalmazásszabályzathoz már korábban hozzáadott alkalmazások listáját jeleníti meg.

2.  Az **Engedélyezett alkalmazások** panelen válassza az **Alkalmazások hozzáadása** lehetőséget.

3.  Az **Alkalmazások hozzáadása** panelen válassza ki az **Áruházbeli alkalmazások** lehetőséget a legördülő listából. A panelen szövegbeviteli mezők jelennek meg, amelyekkel megadhatja az alkalmazás **közzétevőjét** és az alkalmazás **nevét**.

4.  Írja be az alkalmazás és a közzétevő nevét, majd kattintson az **OK** gombra.

    > [!TIP]
    > Az alábbi példában a **Közzétevő** a *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US*, a termék **neve** pedig *Microsoft.MicrosoftAppForWindows*.

5.  Miután megadta a szükséges adatokat, az **OK** gombra kattintva hozzáadhatja az alkalmazást az **Engedélyezett alkalmazások** listájához.

> [!NOTE]
> Egyszerre több Áruházi alkalmazást is hozzáadhat, ha az alkalmazások sor végén található **(...)** elemre kattint, és további alkalmazásokat választ ki. Ha elkészült, kattintson az **OK** gombra.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>Asztali alkalmazás hozzáadása az Engedélyezett alkalmazások listájához

**Asztali alkalmazás hozzáadása**

1.  Az **Alkalmazásszabályzat** panelen válassza ki a kívánt szabályzat nevét, majd válassza ki az **Engedélyezett alkalmazások** lehetőséget. Megnyílik az **Engedélyezett alkalmazások** panel, ahol azoknak az alkalmazásoknak a listáját láthatja, amelyekre ez a szabályzat vonatkozik.

2.  Az **Engedélyezett alkalmazások** panelen válassza az **Alkalmazások hozzáadása** lehetőséget.

3.  Az **Alkalmazások hozzáadása** panelen a legördülő listából válassza ki az **Asztali alkalmazások** lehetőséget.

4.  Miután megadta a szükséges adatokat, az **OK** gombra kattintva hozzáadhatja az alkalmazást az **Engedélyezett alkalmazások** listájához.

> [!NOTE]
> Egyszerre több **asztali alkalmazást** is hozzáadhat, ha az alkalmazások sor végén található **(...)** elemre kattint, és további alkalmazásokat választ ki. Ha elkészült, kattintson az **OK** gombra.

## <a name="windows-information-protection-wip-learning"></a>A Windows Információvédelmi (WIP-) tanulási mód

A WIP által védendő alkalmazások hozzáadása után alkalmazni kell valamely védelmi szabályzatot a **WIP tanulási mód** használatával.

### <a name="before-you-begin"></a>Előkészületek

A Windows információvédelmi (WIP-) tanulás egy olyan jelentés, amellyel a rendszergazdák figyelhetik a WIP számára ismeretlen alkalmazásokat. Ismeretlen az olyan alkalmazás, amelyet nem a szervezeti IT-részleg helyezett üzembe. A rendszergazda a jelentésből exportálhatja ezeket az alkalmazásokat, és a működési zavarok megelőzése céljából hozzáadhatja őket a WIP-szabályzatokhoz, mielőtt a WIP-et „Felülbírálások elrejtése” módban alkalmazná.

Javasoljuk, hogy először a **Csendes** vagy a **Felülbírálások engedélyezése** módot válassza, és egy kisebb csoporton ellenőrizze, hogy az engedélyezett alkalmazások listáján a megfelelő alkalmazások szerepelnek-e. Ha ezzel végzett, a végleges szabályzatban használhatja a **Felülbírálások elrejtése** módot.

#### <a name="what-the-protection-modes-are"></a>Milyen védelmi módok lehetségesek?

- **Felülbírálások elrejtése:**
    - A WIP figyeli a nem megfelelő adatmegosztási gyakorlatot, és megakadályozza, hogy a felhasználó elvégezze a műveletet.
    - Ilyen gyakorlat lehet, ha információt nem vállalati védelem alatt álló alkalmazásokkal osztanak meg, vagy ha vállalati adatokat a vállalaton kívüli személyekkel és eszközökkel osztanak meg.
<br></br>

- **Felülbírálások engedélyezése:**
    - A WIP figyeli a nem megfelelő adatmegosztásokat, és figyelmezteti a felhasználót az esetlegesen nem biztonságos tevékenységre.
    - Ebben a módban azonban a felhasználónak lehetősége van a szabályzat felülbírálásával megosztani az adatokat, a tevékenység pedig megjelenik a műveleti naplóban.
<br></br>
- **Csendes:**
    - A WIP csendes módban üzemel, és úgy naplózza az adatmegosztásokat, hogy nem akadályozza meg azokat a tevékenységeket, amelyek esetében a Felülbírálások engedélyezése módban figyelmeztetések jelennének meg a felhasználó számára.
    - A nem engedélyezett műveletek azonban, például hálózati erőforrások vagy WIP-védelem alatt álló adatok nem megfelelő elérése továbbra is tiltva vannak.
<br></br>
- **Kikapcsolva (nem ajánlott):**
    - A WIP ki van kapcsolva, és nem védi és nem naplózza az adatokat.
    - A WIP kikapcsolása után a rendszer megkísérli visszafejteni a WIP-címkével ellátott fájlokat a csatlakoztatott helyszíni meghajtókon. Vegye figyelembe, hogy a WIP-védelem újbóli bekapcsolásakor a titkosítási és szabályzatinformációk nem lesznek automatikusan újra alkalmazva.

### <a name="to-add-a-protection-mode"></a>Védelmi mód hozzáadása

1.  A **Alkalmazásszabályzat** panelen válassza ki a szabályzat nevét, majd a **Szabályzat hozzáadása** panelen kattintson a **Kötelező beállítások** elemre.

    ![A tanulási mód képernyőképe](../media/AppManagement/learning-mode-sc1.png)

1.  Válassza a **Mentés** elemet.

### <a name="to-use-wip-learning"></a>A WIP-tanulás használata

1. Nyissa meg az Azure irányítópultját.

2. Válassza a bal oldali menü **További szolgáltatások** pontját, majd írja be a szűrő szövegmezőbe az **Intune** nevet.

3. Az **Intune** kiválasztásával megnyílik az **Intune irányítópult**. Itt válassza a **Mobilalkalmazások** elemet.

4. A **Figyelés** szakaszban válassza a **WIP-tanulás** lehetőséget. Ekkor megjelenik a WIP-tanulás által naplózott ismeretlen alkalmazások listája.

> [!IMPORTANT]
> Ha az alkalmazások megjelennek a WIP-tanulási jelentésben, azokat exportálhatja az alkalmazásvédelmi szabályzatokba.

## <a name="to-deploy-your-wip-app-protection-policy"></a>WIP alkalmazásvédelmi szabályzat telepítése

> [!IMPORTANT]
> Az alábbi információk a WIP mobilalkalmazás-kezeléssel (MAM) való használatára vonatkoznak regisztrációs forgatókönyv használata nélkül.

A WIP alkalmazásvédelmi szabályzat létrehozása után a szabályzatot MAM használatával telepíteni kell a szervezetben.

1.  Az **Alkalmazásszabályzat** panelen válassza ki a újonnan létrehozott alkalmazásvédelmi szabályzatot, és válassza a **Felhasználói csoportok**, majd a **Felhasználói csoport hozzáadása** elemet.

    A **Felhasználói csoport hozzáadása** panelen megjelenik az Azure Active Directoryban elérhető összes felhasználói csoport listája.

1.  Válassza ki azt a csoportot, amelyre alkalmazni szeretné a szabályzatot, majd kattintson a **Kiválaszt** lehetőségre.
