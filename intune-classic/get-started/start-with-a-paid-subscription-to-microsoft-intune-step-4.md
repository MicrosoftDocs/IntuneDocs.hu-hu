---
title: "Intune-licencek hozzárendelése | Microsoft Docs"
description: "Licencek és eszközök hozzárendelése az Intune-előfizetéshez"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 03/28/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 793df9f3734b84c74ecac9b8192d0b06306607e8
ms.contentlocale: hu-hu
ms.lasthandoff: 05/23/2017


---

# <a name="assign-intune-licenses-to-your-user-accounts"></a>Intune-licencek hozzárendelése a felhasználói fiókokhoz

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Akár manuálisan adja hozzá a felhasználókat, akár a helyszíni Active Directoryból szinkronizál, először Intune-licencet kell hozzárendelnie minden felhasználóhoz, hogy a felhasználók regisztrálhassák eszközeiket az Intune-ban.

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Intune-licenc hozzárendelése az Office 365 Felügyeleti központban

Az [Office 365 portál](http://go.microsoft.com/fwlink/p/?LinkId=698854) használatával a felhőalapú felhasználók és licencek manuálisan hozzáadhatók, illetve hozzárendelhetők a felhőalapú felhasználói fiókokhoz és a helyszíni Active Directoryból az Azure AD-be szinkronizált fiókokhoz is.

1.  Jelentkezzen be az [Office 365 portálon](http://go.microsoft.com/fwlink/p/?LinkId=698854) bérlői rendszergazdai hitelesítő adataival, majd válassza a **Felhasználók** > **Aktív felhasználók** lehetőséget.

2.  Válassza ki a felhasználói fiókot az Intune felhasználói licencek hozzárendelésére, és válassza a **Terméklicencek** > **Szerkesztés** lehetőséget.

3.  Kapcsolja az **Intune** vagy az **Enterprise Mobility + Security** beállítást **Be**, és válassza a **Mentés** lehetőséget.

4. A felhasználói fiókot most már rendelkezik a szolgáltatás használatához és az eszközöknek a felügyelet alá való regisztrálásához szükséges engedélyekkel.

> [!NOTE]
> Miután regisztrálnak egy eszközt, a felhasználók már megjelennek a felügyeleti konzolon. Emellett kiválaszthat egy felhasználói csoportot az egyszerre való szerkesztéshez, vagy hozzáadva, vagy lecserélve az összes kijelölt felhasználó licencét.

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>A School Data Sync használata licencek kiosztására a felhasználók számára az Intune for Educationben
Az oktatási szervezetek a School Data Sync (SDS) segítségével Intune for Education-licenceket oszthatnak ki a szinkronizált felhasználóknak. Az SDS-profil beállítása esetén jelölje be az Intune for Education jelölőnégyzetet.  

![Az SDS-profil beállításának képe](./media/i4e-sds-profile-setup-setting.png)

Az Intune for Education-licencek kiosztásakor ellenőrizze, hogy az Intune A Direct-licenc is ki van-e osztva.

![Terméklicenc beállításának képe](./media/i4e-set-licenses.png)

További tudnivalók az SDS-ről: [A School Data Sync áttekintése](https://support.office.com/en-us/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US).

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Az EMS felhasználói licencek szelektív kezelése a PowerShell segítségével
Előfordulhat, hogy a Microsoft Enterprise Mobility + Security (korábban: Nagyvállalati mobilitási csomag) megoldást használó szervezeteknek vannak olyan felhasználói, akiknek csak az EMS csomagban foglalt Azure Active Directory Premium vagy Intune szolgáltatásra van szükségük. Az [Azure Active Directory PowerShell-parancsmagok](https://msdn.microsoft.com/library/jj151815.aspx) használatával egy-egy szolgáltatás vagy a szolgáltatások egy részhalmaza is hozzárendelhető.

A felhasználói licencek EMS-szolgáltatásokhoz való szelektív hozzárendeléséhez nyissa meg a PowerShellt rendszergazdaként egy olyan számítógépen, amelyre telepítve van a [Windows PowerShellhez készült Microsoft Azure Active Directory-modul ](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) megoldással rendelkező számítógépen. A PowerShell helyi számítógépre vagy ADFS-kiszolgálóra telepíthető.

Létre kell hoznia egy új licenctermékváltozat-definíciót, amely csak a szükséges szolgáltatáscsomagokra vonatkozik. Ehhez tiltsa le az alkalmazni nem kívánt csomagokat. Például létrehozhat olyan licenctermékváltozat-definíciót, amely nem rendel hozzá Intune-licencet. Az elérhető szolgáltatások listájának megtekintéséhez írja be:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Az Intune szolgáltatáscsomag kizárásához a következő parancsot futtathatja. Ugyanezzel a módszerrel kibonthat egy teljes biztonsági csoportot, vagy még részletesebb szűrőket is használhat.

**1. példa**<br>
Új felhasználó létrehozása a parancssorból, és EMS-licenc hozzárendelése a licenc Intune-részének engedélyezése nélkül:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Ellenőrizze a következővel:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**2. példa**<br>
A hozzárendelt licenccel már rendelkező felhasználó EMS-licencéből az Intune-rész letiltása:

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Ellenőrizze a következővel:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

>[!div class="step-by-step"]

>[&larr; **Felhasználók szinkronizálása az Intune-nal**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Felhasználók és eszközök rendszerezése** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  
