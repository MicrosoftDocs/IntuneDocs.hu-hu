---
title: "Az adatok védelme távoli törléssel | Microsoft Intune"
description: "Az Intune a szelektív és a teljes törlési funkcióval is eltávolíthatja a bizalmas vállalati adatokat, valamint a vállalati erőforrásokhoz való hozzáférést."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dcfa3af374a7e64e931508e1a8022bf8a50c71a7
ms.openlocfilehash: a09c9b55d7906ab792bda90b172a36b3656ed6dd


---

# Adatok védelme teljes vagy szelektív törléssel a Microsoft Intune használatával
Az Intune által felügyelt eszközökről törölni tudja az alkalmazásokat és az adatokat, például ha az eszközre már nincs szükség, azt egy megváltozott célra használják, vagy ha elveszett. Az Intune ehhez szelektív törlési és teljes törlési funkciókat kínál. A felhasználók az Intune Vállalati portálon is kiadhatnak egy távoli törlési parancsot az Intune-ban regisztrált saját tulajdonú eszközökre.

  > [!NOTE]
  > Ez a témakör kizárólag az Intune mobileszköz-kezelő által felügyelt eszközök tartalmának törlését ismerteti. Lehetősége van az [Azure Betekintő portál](https://portal.azure.com) használatával is [törölni a vállalati adatokat az alkalmazásokból](wipe-managed-company-app-data-with-microsoft-intune.md). Ezenkívül [kivonhatja az Intune ügyfélszoftver által felügyelt számítógépeket.](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## Teljes törlés

A **Teljes törlés** visszaállítja az eszközt a gyári beállításokra, és eltávolít minden vállalati is felhasználói adatot és beállítást. Az eszközt a rendszer eltávolítja az Intune-ból. A teljes törlés akkor hasznos, ha szeretne alaphelyzetbe állítani egy adott eszközt, mielőtt új felhasználónak adná, illetve abban az esetben, ha az eszközt elveszítették vagy ellopták.  **A teljes törlést óvatosan használja – az eszközről eltávolított adatok nem állíthatók vissza**.


> [!Warning]
> A 4 GB-nál kevesebb RAM-mal rendelkező, Windows 10 RTM rendszerű eszközök (azaz a Windows 10 rendszer 1511-es verziójánál korábbi eszközök) a törlés után használhatatlanná válhatnak. Ha egy Windows 10 rendszerű eszköz nem válaszol, az eszközt egy USB-meghajtóval vagy valamilyen hasonló megoldással lehet elindítani.

### Eszköz tartalmának távoli törlése az Intune felügyeleti konzoljáról

1.  Válassza ki a törlendő eszközöket. Az eszközök felhasználónként vagy eszközönként választhatók ki.

    -   **Felhasználó szerint:**

        1.  Az [Intune felügyeleti konzolján](https://manage.microsoft.com/) kattintson a **Csoportok** &gt; **Minden felhasználó** elemre.

        2.  Kattintson annak a felhasználónak a nevére, akinek a mobileszközét törölni szeretné. Kattintson a **Tulajdonságok megtekintése** elemre.

        3.  A felhasználó **Tulajdonságok** lapján kattintson az **Eszközök** elemre, majd a törölni kívánt mobileszköz nevére. Ha a kattintás közben a Ctrl billentyűt lenyomva tartja, több eszközt is kijelölhet.

    -   **Eszköz szerint:**

        1.  Az [Intune felügyeleti konzolján](https://manage.microsoft.com/) válassza a **Csoportok** &gt; **Minden mobileszköz** lehetőséget.

      ![Kivonási vagy törlési művelet indítása](../media/dev-sa-wipe.png)

        2.  Kattintson az **Eszközök** elemre, majd a törölni kívánt mobileszköz nevére. Ha a kattintás közben a Ctrl billentyűt lenyomva tartja, több eszközt is kijelölhet.

2.  Válassza a **Kivonás/Összes adat törlése** lehetőséget.

3.  Ekkor a rendszer kérni fogja az eszköz kivonásának megerősítését.

    -   Ha **szelektív törlést** szeretne végrehajtani, amely csak a vállalati alkalmazásokat és adatokat távolítja el, kattintson az **Igen** gombra.

    -   Minden alkalmazást és adatot törlő és az eszközt a gyári alapértelmezett beállításokra visszaállító **Teljes törlés** végrehajtásához válassza az **Adatok törlése az eszközről annak kivonása előtt** lehetőséget. Ez a művelet minden platformra érvényes, kivéve a Windows 8.1-et. **A teljes törlési funkcióval törölt adatok nem állíthatók vissza**.

Ha az eszköz be van kapcsolva és csatlakoztatva van, a törlés összes eszköztípusra való terjesztése kevesebb, mint 15 percet vesz igénybe.

## Szelektív törlés

A **szelektív törlés** a vállalati adatokat, többek között a mobilalkalmazás-felügyeleti (MAM-) adatokat (adott esetben), a beállításokat és az e-mail profilokat távolítja el az eszközről. Szelektív törlés esetén a felhasználó személyes adatai az eszközön maradnak. Az eszközt a rendszer eltávolítja az Intune-ból. Az alábbi táblázatok ismertetik, hogy az egyes platformokon milyen adatokat töröl a rendszer, és hogy az eszközön maradó adatokra milyen hatással van a szelektív törlés.

**iOS**

|Adattípus|iOS|
|-------------|-------|
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok.|Törlődnek az alkalmazások. Törlődnek a vállalati alkalmazásadatok.<br /><br />Törlődnek a mobilalkalmazás-felügyeletet használó Microsoft-alkalmazások adatai. Az alkalmazások nem törlődnek.|
|Beállítások|Az Intune-házirend által beállított konfigurációk érvényüket vesztik, és a felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonódnak.|
|Felügyeleti ügynök|Törlődik a felügyeleti profil.|
|E-mail|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek.|
|Azure Active Directory (AAD) elhagyása|Törlődik az AAD-rekord|
|Névjegyek | Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja.  A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.

**Android**

|Adattípus|Android|Androidra fejlesztett Samsung KNOX|
|-------------|-----------|------------------------|
|Webhivatkozások|Eltávolítva.|Eltávolítva|
|Nem felügyelt Google Play-alkalmazások|Az alkalmazások és az adatok telepítve maradnak.|Az alkalmazások és az adatok telepítve maradnak.|
|Nem felügyelt üzletági alkalmazások|Az alkalmazások és az adatok telepítve maradnak.|Az alkalmazások el lesznek távolítva, és emiatt az alkalmazás helyi adatai is törlődnek. Az alkalmazáson kívüli (SD-kártyán tárolt stb.) adatokat a rendszer nem távolítja el.|
|Felügyelt Google Play-alkalmazások|Az alkalmazásadatok törlődnek. Az alkalmazás nem lesz eltávolítva. Az alkalmazáson kívül (pl. SD-kártyán stb.) a MAM-titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de a rendszer nem távolítja el azokat.|Az alkalmazásadatok törlődnek. Az alkalmazás nem lesz eltávolítva. Az alkalmazáson kívül (pl. SD-kártyán stb.) a MAM titkosítás által védett adatok titkosítva maradnak, de a rendszer nem távolítja el azokat.|
|Felügyelt üzletági alkalmazások|Az alkalmazásadatok törlődnek. Az alkalmazás nem lesz eltávolítva. Az alkalmazáson kívül (pl. SD-kártyán stb.) a MAM-titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de a rendszer nem távolítja el azokat.|Az alkalmazásadatok törlődnek. Az alkalmazás nem lesz eltávolítva. Az alkalmazáson kívül (pl. SD-kártyán stb.) a MAM-titkosítás által védett adatok titkosítva és használhatatlan állapotban maradnak, de a rendszer nem távolítja el azokat.|
|Beállítások|Az Intune-házirend által beállított konfigurációk érvényüket vesztik, és a felhasználók megváltoztathatják a beállításokat.|Az Intune-házirend által beállított konfigurációk érvényüket vesztik, és a felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva|Eltávolítva|
|Tanúsítvány profilbeállításai|A tanúsítványok visszavonódnak, de nem törlődnek.|A tanúsítványok törlődnek és visszavonódnak.|
|Felügyeleti ügynök|Visszavonódik az eszköz-rendszergazdai jogosultság.|Visszavonódik az eszköz-rendszergazdai jogosultság.|
|E-mail|Törlődnek az androidos Microsoft Outlook alkalmazás által fogadott e-mailek.|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek.|
|Azure Active Directory (AAD) elhagyása|Törlődik az AAD-rekord|Törlődik az AAD-rekord|
|Névjegyek | Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja.  A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.|Az alkalmazásból a natív címjegyzékbe közvetlenül szinkronizált névjegyeket a rendszer eltávolítja.  A natív címjegyzékből egy másik külső forrásba szinkronizált névjegyek nem törölhetők. <br /> <br />Jelenleg csak az Outlook alkalmazás használata támogatott.

**Windows**

|Adattípus|Windows 8.1 (MDM) és Windows RT 8.1|Windows RT|Windows Phone 8 és Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Vállalati alkalmazások és az Intune által telepített egyéb vonatkozó adatok.|A titkosított fájlrendszerrel (EFS) védett fájlok kulcsát a rendszer visszavonja, és a felhasználó nem fogja tudni megnyitni őket.|Nem törlődnek a vállalati alkalmazások.|Törlődnek az eredetileg a vállalati portálon keresztül telepített alkalmazások. Törlődnek a vállalati alkalmazásadatok.|Az alkalmazások és a közvetlen telepítési kulcsok el lesznek távolítva.|
|Beállítások|Az Intune-házirend által beállított konfigurációk érvényüket vesztik, és a felhasználók megváltoztathatják a beállításokat.|Az Intune-házirend által beállított konfigurációk érvényüket vesztik, és a felhasználók megváltoztathatják a beállításokat.|Az Intune-házirend által beállított konfigurációk érvényüket vesztik, és a felhasználók megváltoztathatják a beállításokat.|Az Intune-házirend által beállított konfigurációk érvényüket vesztik, és a felhasználók megváltoztathatják a beállításokat.|
|Wi-Fi és VPN profilbeállításai|Eltávolítva|Eltávolítva|Nem támogatott|Eltávolítva|
|Tanúsítvány profilbeállításai|A tanúsítványok törlődnek és visszavonódnak.|A tanúsítványok törlődnek és visszavonódnak.|Nem támogatott|A tanúsítványok törlődnek és visszavonódnak.|
|E-mail|Törlődnek az EFS által védett e-mailek, ideértve a Windows Posta alkalmazásban tárolt leveleket és mellékleteket.|Nem támogatott|Törlődnek az Intune által telepített levelezési profilok és az eszközön gyorsítótárazott e-mailek.|Törlődnek az EFS által védett e-mailek, ideértve a Windows Posta alkalmazásban tárolt leveleket és mellékleteket. A rendszer eltávolítja az Intune által telepített e-mail-fiókokat.|
|Azure Active Directory (AAD) elhagyása|Nem|Nem|Törlődik az AAD-rekord|Nem alkalmazható. A Windows 10 nem támogatja az Azure Active Directoryhoz csatlakoztatott eszközök szelektív törlését.|

## Titkosítási fájlrendszer (EFS) által védett tartalom törlése
A Windows 8.1 és a Windows RT 8.1 rendszer támogatja az EFS által védett tartalom szelektív törlését. Az EFS által védett tartalom szelektív törlése az alábbiak szerint működik:

-   A szelektív törlés során csak azok az EFS által védett alkalmazások és adatok törlődnek, amelyek az Intune-fiókkal megegyező internetes tartományba tartoznak. További információ: [Eszközadatok törlése a Windows szelektív törlési funkciójával](http://technet.microsoft.com/library/dn486874.aspx).

-   Ha az EFS-hez társított tartomány bármilyen módon megváltozik, akár 48 órára is szükség lehet ahhoz, hogy az új tartományt használó alkalmazások és adatok szelektív törlése lehetséges legyen.

-   A rendszer az Intune-ban regisztrált valamennyi tartományt törli.

Szelektív törléssel jelenleg a következő EFS által védett adatok és alkalmazások törölhetők:

-   A Posta alkalmazás a Windowsban

-   Munkahelyi mappák

-   Az EFS által titkosított fájlok és mappák. További információ: [Gyakorlati tanácsok a titkosított fájlrendszerhez](http://support.microsoft.com/kb/223316).

-   Ha a szervezet Active Directoryt használ identitáskezelőként, akkor ahhoz, hogy az EFS által védett adatok szelektív törlése megfelelően működjön, szinkronizálnia kell az adatokat az AAD-be a Címtár-szinkronizálás (DirSync) eszközzel.  A DirSyncrőlaz Azure Active Directory dokumentációjának következő cikkében találhat további információt: [Címtár-szinkronizálási forgatókönyv](http://technet.microsoft.com/library/dn441212.aspx).

## A kivonási és törlési műveletek figyelése
A kivont és törölt eszközök, valamint a műveletet végző felhasználók listáját tartalmazó jelentés megtekintése:

1.  Az [Intune felügyeleti konzoljában](https://manage.microsoft.com/) kattintson a **Jelentések** &gt; **Korábbi eszközökről készült jelentések** elemre.

2.  Adja meg a jelentés kezdő- és záródátumát, majd kattintson a **Jelentés megtekintése** elemre.


### További információ
[Eszközök kivonása](retire-devices-from-microsoft-intune-management.md)

[Windows szelektív törlés az eszközadatok felügyeletéhez](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Aug16_HO1-->

