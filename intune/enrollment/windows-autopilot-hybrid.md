---
title: Regisztráció hibrid Azure AD-hez csatlakoztatott eszközökhöz – Windows Autopilot
titleSuffix: ''
description: A Windows Autopilot használatával regisztrálhat hibrid Azure AD-hez csatlakoztatott eszközöket Microsoft Intuneban.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ab90dc9a95e461ad8c5913131a23a0355e9d072c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509218"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-by-using-intune-and-windows-autopilot"></a>Hibrid Azure AD-hez csatlakoztatott eszközök üzembe helyezése az Intune és a Windows Autopilot használatával
Az Intune és a Windows Autopilot használatával hibrid Azure Active Directory (Azure AD) csatlakoztatott eszközöket állíthat be. Ehhez kövesse a cikk lépéseit.

## <a name="prerequisites"></a>Előfeltételek

A [hibrid Azure ad-hez csatlakoztatott eszközök](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan)konfigurálása sikerült. Ügyeljen arra, hogy az [eszköz regisztrációját](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration) a Get-MsolDevice parancsmag használatával ellenőrizze.

A regisztrálni kívánt eszközöknek a következő feltételeknek kell megfelelniük:
- Windows 10 v1809 vagy újabb rendszert kell futtatnia.
- A [dokumentált Windows Autopilot hálózati követelményeket követve](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)hozzáférhet az internethez.
- Hozzáféréssel kell rendelkeznie egy Active Directory tartományvezérlőhöz, ezért csatlakoznia kell a szervezet hálózatához (ahol fel tudja oldani az AD-tartomány és az AD-tartományvezérlő DNS-rekordjait, és kommunikálni a tartományvezérlővel a felhasználó hitelesítéséhez. A VPN-kapcsolat jelenleg nem támogatott).
- Pingelje a csatlakoztatni kívánt tartomány tartományvezérlőjét.
- Ha proxyt használ, a WPAD-proxybeállítások beállítást engedélyezni és konfigurálni kell.
- Az out-of-box (OOBE) felületén keresztül végezhető el.

## <a name="set-up-windows-10-automatic-enrollment"></a>Windows 10-es eszközök automatikus regisztrációjának beállítása

1. Jelentkezzen be a [Azure Portalba](https://portal.azure.com) , és a bal oldali ablaktáblán válassza a **Azure Active Directory**lehetőséget.

   ![A Azure Portal](./media/windows-autopilot-hybrid/auto-enroll-azure-main.png)

1. Válassza a **Mobilitás (MDM és MAM)** elemet.

   ![A Azure Active Directory panel](./media/windows-autopilot-hybrid/auto-enroll-mdm.png)

1. Válassza a **Microsoft Intune** elemet.

   ![A mobilitás (MDM és MAM) panel](./media/windows-autopilot-hybrid/auto-enroll-intune.png)

1. Győződjön meg arról, hogy az Intune és a Windows használatával az Azure AD-hez csatlakoztatott eszközöket telepítő felhasználók a **Mdm felhasználói hatókörében**szereplő csoport tagjai.

   ![A mobilitás (MDM és MAM) konfigurálása panel](./media/windows-autopilot-hybrid/auto-enroll-scope.png)

1. Használja az alapértelmezett értékeket a **MDM használati feltételek URL-cím**, a **Mdm-felderítési URL**-cím és a **Mdm megfelelőségi URL-címe** mezőbe, majd válassza a **Mentés**lehetőséget.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>A számítógépfiókok maximális számának növelése a Szervezeti egység területen

A Active Directory Intune-összekötője robotpilóta-beléptetett számítógépeket hoz létre a helyszíni Active Directory tartományban. Az Intune-összekötőt futtató számítógépnek rendelkeznie kell a számítógép-objektumok tartományon belüli létrehozásához szükséges jogokkal. 

Bizonyos tartományokban a számítógépek nem kapnak jogosultságot a számítógépek létrehozásához. Emellett a tartományok beépített korláttal rendelkeznek (alapértelmezett érték 10), amely minden olyan felhasználóra és számítógépre vonatkozik, amely nem delegált számítógép-objektumok létrehozásához szükséges jogosultságokat. Ezért a jogosultságokat az Intune-összekötőt futtató számítógépekre kell delegálni azon a szervezeti egységen, ahol a hibrid Azure AD-hez csatlakoztatott eszközök jönnek létre.

A számítógépek létrehozásához szükséges jogokat biztosító szervezeti egységnek meg kell egyeznie:
- A tartományhoz való csatlakozás profiljában megadott szervezeti egység.
- Ha nincs kiválasztva profil, a számítógép tartományneve a tartományhoz.

1. Nyissa meg **Active Directory felhasználókat és számítógépeket (DSA. msc)** .

1. Kattintson a jobb gombbal arra a szervezeti egységre, amelyet hibrid Azure AD-hez csatlakoztatott számítógépek létrehozásához fog használni, majd válassza a **vezérlés delegálása**lehetőséget.

    ![A delegált vezérlő parancs](./media/windows-autopilot-hybrid/delegate-control.png)

1. A Control Wizard ( **vezérlés delegálása** ) varázslóban válassza a **következő** >   > **típusú objektumok** **hozzáadása**lehetőséget.

1. Az **Objektumtípusok** ablaktáblán jelölje be a **számítógépek** jelölőnégyzetet, majd kattintson az **OK gombra**.

    ![Az Objektumtípusok panel](./media/windows-autopilot-hybrid/object-types-computers.png)

1. A **felhasználók, számítógépek vagy csoportok kiválasztása** panelen az **adja meg a kijelölendő objektumok nevét** mezőbe írja be annak a számítógépnek a nevét, amelyen az összekötő telepítve van.

    ![A felhasználók, számítógépek vagy csoportok kiválasztása panel](./media/windows-autopilot-hybrid/enter-object-names.png)

1. Jelölje be a Névellenőrzés **jelölőnégyzetet** a bejegyzés ellenőrzéséhez, majd kattintson **az OK gombra**, majd válassza a **tovább**lehetőséget.

1. Válassza az **Egyéni feladat létrehozása**lehetőséget  > **következő**delegálásához.

1. Jelölje be a **csak a következő objektumokat a mappában** jelölőnégyzetből, majd jelölje ki a **számítógép-objektumokat**, **hozzon létre a kijelölt objektumokat**ebben a mappában, és **törölje a kijelölt objektumokat a mappában** jelölőnégyzetből.

    ![Az Active Directory objektumtípus panel](./media/windows-autopilot-hybrid/only-following-objects.png)
    
1. Válassza a **Tovább** elemet.

1. Az **engedélyek**területen jelölje be a **teljes hozzáférés** jelölőnégyzetet.  
    Ez a művelet kijelöli az összes többi beállítást.

    ![Az engedélyek panel](./media/windows-autopilot-hybrid/full-control.png)

1. Válassza a **tovább**, majd a **Befejezés**lehetőséget.

## <a name="install-the-intune-connector"></a>Az Intune-összekötő telepítése

A Active Directory Intune-összekötőjét a Windows Server 2016-es vagy újabb verzióját futtató számítógépre kell telepíteni. A számítógépnek hozzáféréssel kell rendelkeznie az internethez és a Active Directoryhoz is. A méret és a rendelkezésre állás növelése érdekében, valamint egyszerre több Active Directory-tartomány támogatásához egyszerre több összekötőt is telepíthet környezetében. Javasoljuk, hogy az összekötőt olyan kiszolgálóra telepítse, amely nem futtat más Intune-összekötőket.

1. Az [Intune](https://aka.ms/intuneportal)-ban válassza az **eszközök beléptetése** > **Windows-regisztráció** > **Intune-összekötő a Active Directory** > **hozzáadáshoz**lehetőséget. 
2. Az összekötő letöltéséhez kövesse az utasításokat.
3. Az összekötő telepítéséhez nyissa meg a letöltött összekötő telepítési fájlját ( *ODJConnectorBootstrapper. exe)* .
4. A beállítás végén válassza a **Konfigurálás**lehetőséget.
5. Válassza **a bejelentkezés**lehetőséget.
6. Adja meg a felhasználó globális rendszergazdai vagy Intune-rendszergazdai szerepkörének hitelesítő adatait.  
   A felhasználói fióknak rendelkeznie kell egy hozzárendelt Intune-licenccel.
7. Lépjen az **eszközök beléptetése**@no__t – 1**Windows-regisztráció** > **Intune-összekötő a Active Directoryhoz**, majd ellenőrizze, hogy a kapcsolódási állapot **aktív**-e.

> [!NOTE]
> Az Összekötőbe való bejelentkezés után néhány percet is igénybe vehet, hogy megjelenjen az [Intune](https://aka.ms/intuneportal)-ban. A rendszer csak akkor jelenik meg, ha sikeresen tud kommunikálni az Intune szolgáltatással.

### <a name="turn-off-ie-enhanced-security-configuration"></a>Az Internet Explorer fokozott biztonsági beállításainak kikapcsolása
Alapértelmezés szerint a Windows Serveren be van kapcsolva az Internet Explorer fokozott biztonsági beállításai. Ha nem tud bejelentkezni az Intune-Összekötőbe Active Directory, akkor kapcsolja ki az Internet Explorer fokozott biztonsági beállításait a rendszergazda számára. [Az Internet Explorer fokozott biztonsági beállításainak kikapcsolása](https://blogs.technet.microsoft.com/chenley/2011/03/10/how-to-turn-off-internet-explorer-enhanced-security-configuration)

### <a name="configure-web-proxy-settings"></a>Webproxy-beállítások konfigurálása

Ha a hálózati környezetben van egy webproxyja, győződjön meg arról, hogy az Intune-összekötő a Active Directory megfelelően működik-e, ha a [meglévő helyszíni proxykiszolgálók](autopilot-hybrid-connector-proxy.md)használatára hivatkozik.


## <a name="create-a-device-group"></a>Eszközcsoport létrehozása
1. Az [Intune](https://aka.ms/intuneportal)-ban válassza a **csoportok** > **új csoport**lehetőséget.

1. A **csoport** ablaktáblán tegye a következőket:

    a. A **csoport típusa**beállításnál válassza a **Biztonság**elemet.

    b. Adja meg a **csoport nevét** és a **csoport leírását**.

    c. Válasszon **tagsági típust**.

1. Ha a **dinamikus eszközök** lehetőséget választotta a tagság típusa beállításnál, **a csoport** ablaktáblán válassza ki a **dinamikus eszközök tagjai** elemet, majd a **speciális szabály** mezőben tegye a következők egyikét:
    - Az összes Autopilot-eszközt tartalmazó csoport létrehozásához írja be a következőt: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
    - Az Intune csoport címkéje mezője az Azure AD-eszközök Rendeléskód attribútumára mutat. Ha olyan csoportot szeretne létrehozni, amely tartalmazza az összes Autopilot-eszközt egy adott csoport címkével (Rendeléskód), akkor a következőt kell beírnia: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Ha olyan csoportot szeretne létrehozni, amely tartalmazza az összes Autopilot-eszközt egy adott megrendelés-AZONOSÍTÓval, írja be a `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")` értéket.
    
1. Válassza a **Mentés** lehetőséget.

1. Válassza a **Létrehozás** lehetőséget.  

## <a name="register-your-autopilot-devices"></a>Az Autopilot-eszközök regisztrálása

Válassza ki az alábbi módszerek egyikét az Autopilot-eszközök regisztrálásához.

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>A már beléptetett Autopilot-eszközök regisztrálása

1. Autopilot-üzembehelyezési profil létrehozása a **Minden megcélzott eszköz AutoPilot-eszközzé alakítása** beállítás **Igen** értékre állításával. 
2. Rendelje hozzá a profilt egy olyan csoporthoz, amely tartalmazza azokat a tagokat, amelyeket automatikusan szeretne regisztrálni az Autopilot-ben.

További információért lásd: [AutoPilot-üzembehelyezési profil létrehozása](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>A nem beléptetett Autopilot-eszközök regisztrálása

Ha az eszközök még nincsenek beléptetve, regisztrációjukat saját kezűleg elvégezheti. További információkért lásd: [Eszközök hozzáadása](enrollment-autopilot.md#add-devices)

### <a name="register-devices-from-an-oem"></a>OEM-eszközök regisztrálása

Új eszközök vásárlásakor egyes számítógépgyártók (OEM) regisztrálhatják az eszközöket az Ön számára. További információkat a [Windows Autopilot oldala](https://aka.ms/WindowsAutopilot) tartalmaz.

Az Autopilot-eszközök *regisztrálása*előtt az Intune-ba való regisztrálás előtt három helyen jelennek meg (a nevük a sorozatszámokra van állítva):
- Az Azure Portal az Intune-ban található **robotpilóta-eszközök** panel. Válassza az eszközök **beléptetése** > **Windows-regisztráció** > **eszköz**lehetőséget.
- Az **Azure ad-eszközök** panel a Azure Portal Intune-ban. Válassza az **eszközök**@no__t – 1**Azure ad-eszközök**elemet.
- Az **Azure ad minden eszköz** paneljének Azure Active Directory a Azure Portal az **eszközök**@no__t – 2**minden eszköz**kiválasztásával.

Az Autopilot-eszközök *regisztrálását*követően négy helyen jelennek meg:
- Az Azure Portal az Intune-ban található **robotpilóta-eszközök** panel. Válassza az eszközök **beléptetése** > **Windows-regisztráció** > **eszköz**lehetőséget.
- Az **Azure ad-eszközök** panel a Azure Portal Intune-ban. Válassza az **eszközök**@no__t – 1**Azure ad-eszközök**elemet.
- Az **Azure ad minden eszköz** paneljének Azure Active Directory a Azure Portal. Válassza az **eszközök** > **minden eszköz**lehetőséget.
- A Azure Portalban található Intune **minden eszköz** panelje. Válassza az **eszközök** > **minden eszköz**lehetőséget.

Az Autopilot-eszközök regisztrálását követően a nevük az eszköz állomásneve lesz. Alapértelmezés szerint az állomásnév a *desktoptal*kezdődik.


## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Autopilot-üzembehelyezési profil létrehozása és hozzárendelése
Az Autopilot-üzembehelyezési profilokkal Autopilot-eszközeit konfigurálhatja.

1. Az [Intune](https://aka.ms/intuneportal)-ban válassza az **eszközök beléptetése** > **Windows-regisztráció** > **üzembe helyezési profilok** > **Létrehozás profilt**.
2. Az **alapvető beállítások** lapon adja meg a **nevet** és a **leírást**(nem kötelező).
3. Ha azt szeretné, hogy a hozzárendelt csoportokban lévő minden eszköz automatikusan átálljon az AutoPilotra, állítsa a **Minden megcélzott eszköz AutoPilot-eszközzé alakítása** beállítást **Igen** értékre. A hozzárendelt csoportokban a vállalat tulajdonában lévő, nem Autopilot-eszközök regisztrálva lesznek az Autopilot Deployment szolgáltatásban. A személyes tulajdonban lévő eszközök nem lesznek átalakítva az Autopilot szolgáltatásba. A regisztráció feldolgozása 48 órát is igénybe vehet. Az eszköz regisztrációjának törlése és alaphelyzetbe állítása után az Autopilot regisztrálja az eszközt. Miután ilyen módon regisztrál egy eszközt, a beállítás letiltása vagy a profil-hozzárendelés eltávolítása nem távolítja el az eszközt az Autopilot üzembehelyezési szolgáltatásból. Ehhez [közvetlenül kell törölnie az eszközt](enrollment-autopilot.md#delete-autopilot-devices).
4. Válassza a **Tovább** elemet.
5. A beépített felhasználói **élmény (OOBE)** lapon a **telepítési mód**beállításnál válassza a **felhasználó által vezérelt**lehetőséget.
6. Az **illesztés az Azure ad** -ba mezőben válassza a **hibrid Azure ad-hez csatlakoztatott**lehetőséget.
7. Szükség szerint konfigurálja a további beállításokat a beépített **élmény (OOBE)** lapon.
8. Válassza a **Tovább** elemet.
9. A **hatókör címkék** lapon válassza ki a profil [hatókör-címkéi](../fundamentals/scope-tags.md) elemet.
10. Válassza a **Tovább** elemet.
11. A **hozzárendelések** lapon válassza a **csoportok kiválasztása** lehetőséget > kereséséhez, majd válassza ki az eszközcsoport > **válassza ki**azt.
12. Válassza a **következő** > **Létrehozás**elemet.

Körülbelül 15 percet vesz igénybe, hogy az eszköz profiljának állapota *ne* legyen hozzárendelve *hozzárendeléshez* , és végül hozzá legyen *rendelve*.

## <a name="optional-turn-on-the-enrollment-status-page"></a>Választható A regisztráció állapotának bekapcsolása lap

1. Az [Intune](https://aka.ms/intuneportal)-ban válassza az **eszközök beléptetése**@no__t – 2**Windows-regisztráció**@no__t – 4**regisztráció állapota lapot**.
1. A **regisztráció állapota lap** ablaktáblán válassza az **alapértelmezett** > **Beállítások**lehetőséget.
1. Az **alkalmazás és profil telepítési folyamatának megjelenítése** területen válassza az **Igen**lehetőséget.
1. Igény szerint konfigurálja a többi beállítást.
1. Válassza a **Mentés** lehetőséget.

## <a name="create-and-assign-a-domain-join-profile"></a>Tartomány-csatlakoztatási profil létrehozása és hozzárendelése

1. Az [Intune](https://aka.ms/intuneportal)-ban válassza az **eszköz konfigurációja** > **profilok** > **profil létrehozása**lehetőséget.
1. Adja meg a következő tulajdonságokat:
   - **Név**: Adja meg az új profil leíró nevét.
   - **Leírás:** Itt adhatja meg a profil leírását.
   - **Platform**: válassza **a Windows 10 és újabb**lehetőséget.
   - **Profil típusa**: válassza a **tartományhoz való csatlakozás (előzetes verzió)** lehetőséget.
1. Válassza a **Beállítások**lehetőséget, majd adja meg a **számítógép nevének előtagját**, a **tartománynevet**és a (választható) **szervezeti egységet** [DN formátumban](https://docs.microsoft.com/windows/desktop/ad/object-names-and-identities#distinguished-name). 
   > [!NOTE]
   > Ne használjon idézőjeleket a **szervezeti egységben**lévő érték körül.
1. Válassza **az OK** > **Létrehozás**elemet.  
    Ekkor létrejön a profil, és megjelenik a listában.
1. A profil hozzárendeléséhez kövesse az [eszköz profiljának](../configuration/device-profile-assign.md#assign-a-device-profile) kiosztása és a profil társítása ugyanahhoz [a lépésben használt](windows-autopilot-hybrid.md#create-a-device-group) csoporthoz című témakör lépéseit.
   - Több tartományhoz való csatlakozás profilok üzembe helyezése
   
     a. Hozzon létre egy dinamikus csoportot, amely tartalmazza az összes Autopilot-eszközt egy adott Autopilot Deployment-profillal, írja be a következőt: (Device. enrollmentProfileName-EQ "Autopilot-profil neve"). 
     
     b. Cserélje le az "Autopilot-profil neve" nevet az [Autopilot Deployment-profil létrehozása és kiosztása](windows-autopilot-hybrid.md#create-and-assign-an-autopilot-deployment-profile)alatt létrehozott profil megjelenített nevére. 
     
     c. Hozzon létre több Autopilot Deployment-profilt, és rendelje hozzá az eszközt a dinamikus csoportban megadott profilhoz.

> [!NOTE]
> A hibrid Azure AD Joinhez készült Windows Autopilot elnevezési képességei nem támogatják a (z)% SERIAL% változót, és csak a számítógépnév előtagjait támogatják.

## <a name="next-steps"></a>További lépések

Miután konfigurálta a Windows Autopilotot, ideje elsajátítani, hogyan felügyelheti az eszközöket. További információ: [Mi a Microsoft Intune eszközkezelés?](../remote-actions/device-management.md).