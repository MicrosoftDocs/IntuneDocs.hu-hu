---
title: Újdonságok a Microsoft Intune-ban – Azure | Microsoft Docs
titleSuffix: ''
description: Az Azure-beli Intune-portál újdonságai
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 591a9af597fc64509a4a7dd19d83d25948a6118e
ms.sourcegitcommit: d1b36501186e867355843ddd67c795ade800b76a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73182949"
---
# <a name="whats-new-in-microsoft-intune"></a>Újdonságok a Microsoft Intune-ban

Heti összesítésben olvashat a Microsoft Intune újdonságairól. Megtalálhatja a [fontos megjegyzéseket](#notices), a [korábbi kiadásokat](whats-new-archive.md)és az [Intune szolgáltatás frissítéseinek kiadásával](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728)kapcsolatos információkat is.

> [!Note]
> A [havi frissítés](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) akár három napot is igénybe vehet, és a következő sorrendben fog megjelenni:
>
> - 1\. nap: Ázsia és a Csendes-óceáni térség (APAC)
> - 2\. nap: Európa, Közel-Kelet, Afrika (EMEA)
> - 3\. nap: Észak-Amerika
>
> Egyes funkciók bevezetése több hetet igénybe vehet, így előfordulhat, hogy nem elérhetők a felhasználók számára az első héten.
>
> A kiadásban a közelgő funkciók listáját a [fejlesztés lapon](in-development.md) találja.

**RSS-hírcsatorna**: értesítést kap az oldal frissítésekor, ha a következő URL-címet másolja, és beillesztette a hírcsatorna-olvasóba: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Device security
### Intune apps
### Monitor and troubleshoot
### Role-based access control
-->  


## <a name="week-of-october-28-2019"></a>2019. október 28-i hét

### <a name="app-management"></a>Alkalmazáskezelés 

#### <a name="win32-apps-on-windows-10-s-mode-devices----3747604---"></a>Win32-alkalmazások Windows 10 S üzemmódú eszközökön <!-- 3747604 --> 
Win32-alkalmazásokat telepíthet és futtathat Windows 10 S üzemmódú felügyelt eszközökön. Ehhez a Windows Defender Application Control (WDAC) PowerShell-eszközeivel létrehozhat egy vagy több kiegészítő szabályzatot az S üzemmódhoz. Írja alá a kiegészítő szabályzatokat az Eszközkezelő-aláírási portálon, majd töltse fel és terjessze a szabályzatokat az Intune-on keresztül. Az Intune-ban ezt a képességet az **ügyfélalkalmazások** > **Windows 10 S kiegészítő házirendek**lehetőség kiválasztásával találja meg. További információ: Win32- [alkalmazások engedélyezése az S Mode-eszközökön](~/apps/apps-win32-s-mode.md).

#### <a name="set-win32-app-availability-based-on-a-date-and-time----3510685---"></a>Win32-alkalmazás rendelkezésre állásának beállítása dátum és idő alapján <!-- 3510685 -->
Rendszergazdaként beállíthatja a szükséges Win32-alkalmazások kezdési és határidő-idejét. A kezdési időpontban az Intune felügyeleti bővítmény elindítja az alkalmazás tartalmának letöltését és gyorsítótárazását. Az alkalmazás a határidő lejártakor lesz telepítve. Az elérhető alkalmazások esetében a kezdési idő akkor fog megjelenni, amikor az alkalmazás látható Céges portálban. További információ: az [Intune win32 app Management](~/apps/apps-win32-app-management.md#set-win32-app-availability-and-notifications).

#### <a name="require-device-restart-based-on-grace-period-after-win32-app-install----3136567---"></a>Eszköz újraindításának megkövetelése türelmi időszak alapján a Win32-alkalmazás telepítése után <!-- 3136567 -->
Megkövetelheti, hogy az eszköznek újra kell indítania a Win32-alkalmazások sikeres telepítése után. További információ: [win32 app Management – alkalmazás telepítésének részletei](~/apps/apps-win32-app-management.md#step-4-configure-app-installation-details).

#### <a name="dark-mode-for-ios-company-portal----4911422---"></a>Sötét mód iOS-Céges portál <!-- 4911422 -->
A sötét mód elérhető az iOS-Céges portál számára. A felhasználók letölthetik a vállalati alkalmazásokat, kezelhetik az eszközeiket, és az eszköz beállításai alapján választhatják ki a kívánt színsémát. Az iOS-Céges portál automatikusan meg fogja egyezni a végfelhasználói eszközbeállítások sötét vagy világos módban. További információ: [sötét mód bevezetése Microsoft Intune céges portál iOS rendszerhez](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Introducing-dark-mode-on-Microsoft-Intune-Company-Portal-for-iOS/ba-p/918453). További információ az iOS Céges portálről: [a Microsoft Intune céges portál alkalmazás konfigurálása](~/apps/company-portal-app.md).

#### <a name="android-company-portal-enforced-minimum-app-version----2378776---"></a>Android Céges portál kényszerített alkalmazás minimális verziója <!-- 2378776 -->
Az alkalmazás-védelmi házirend **minimális céges portál verziójának** beállításával megadhatja a végfelhasználói eszközön kényszerített céges portál adott minimálisan meghatározott verzióját. Ez a feltételes indítási beállítás lehetővé teszi a **hozzáférés letiltását**, az **adatok törlését**vagy a **Figyelmeztetés** lehetséges műveleteit, ha az érték nem teljesül. Az érték lehetséges formátuma a *[Major] mintázatot követi. [ Minor]* , *[főverzió]. [ Alverzió]. [Build]* vagy *[főverzió]. [ Alverzió]. [Build]. [Változat]* . 

Ha be van állítva a **minimális céges portál verziószáma** , az hatással lesz minden olyan végfelhasználóra, aki a céges portál 5.0.4560.0 és a céges portál jövőbeli verzióit lekéri. Ez a beállítás nem lesz hatással a felhasználók olyan Céges portál verzióját használó felhasználóra, amely régebbi, mint a szolgáltatás által kiadott verzió. Az alkalmazás automatikus frissítéseit az eszközön használó végfelhasználók valószínűleg nem fogják látni a szolgáltatásból származó párbeszédpaneleket, mivel azok valószínűleg a legújabb Céges portál-verziót fogják használni. Ez a beállítás csak a regisztrált és a nem regisztrált eszközökön futó alkalmazás-védelemmel rendelkező Android. További információ: [Android-alkalmazás védelmi szabályzatának beállításai – feltételes indítás](~/apps/app-protection-policy-settings-android.md#conditional-launch).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->

### <a name="microsoft-365-device-management"></a>Eszközkezelés Microsoft 365

#### <a name="introducing-endpoint-security-node-in-microsoft-365-device-management-------5630102---"></a>A végpont biztonsági csomópontjának bemutatása Microsoft 365-eszközkezelés    <!-- 5630102 -->

A **végponti biztonsági** csomópont mostantól általánosan elérhető Microsoft 365 Eszközkezelő Specialist munkaterületen a https://devicemanagement.microsoft.com , amely a végpontok biztonságossá tételeit csoportosítja, például:

- Biztonsági alapkonfigurációk: előre konfigurált beállítások csoportja, amely segítséget nyújt a Microsoft által javasolt, ismert beállítások és alapértelmezett értékek alkalmazásához.

- Biztonsági feladatok: kihasználhatja a Microsoft Defender ATPs Threat and sebezhetőségi felügyeletét (TVM), és az Intune-nal javíthatja a végpontok gyengeségeit.

- Microsoft Defender ATP: integrált Microsoft Defender komplex veszélyforrások elleni védelem (ATP) a biztonsági rések megelőzése érdekében.

Ezek a beállítások továbbra is elérhetők lesznek a többi érintett csomóponttól, például az eszközöktől, és az aktuálisan konfigurált állapot ugyanaz lesz, függetlenül attól, hogy hol férhet hozzá és engedélyezheti ezeket a funkciókat.

További információ ezekről a fejlesztésekről: [Intune-ügyfél sikerének blogbejegyzése](https://aka.ms/Endpoint_security_node) a Microsoft Tech Community webhelyén.

### <a name="device-management"></a>Eszközkezelés

#### <a name="intune-supports-ios-11-and-later----4665324----"></a>Az Intune támogatja az iOS 11 és újabb verziókat <!-- 4665324  -->

Az Intune-regisztráció és a Céges portál mostantól támogatja az iOS 11-es és újabb verzióit. A régebbi verziók nem támogatottak.

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="updated-support-experience------5012398---"></a>Frissített támogatási élmény   <!-- 5012398 -->

Az Intune-nal kapcsolatos [Súgó és támogatás megszerzésének](get-support.md) konzolon belüli élményét a rendszer frissíti és egyszerűsíti.  Továbbfejlesztettük a konzolon belüli keresést és visszajelzést a gyakori problémákkal kapcsolatban, valamint az ügyfélszolgálattal való kapcsolatfelvételhez használt munkafolyamatot. A támogatási problémák megnyitásakor a rendszer valós idejű becsléseket fog kapni a visszahívási vagy e-mail-válaszhoz, és a Premier és az egységes támogatással rendelkező ügyfelek egyszerűen meghatározhatják a probléma súlyosságát, így gyorsabban kaphatnak támogatást.

<!-- ########################## -->
## <a name="week-of-october-21-2019"></a>2019. október 21-i hét

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="microsoft-365-device-management"></a>Eszközkezelés Microsoft 365

#### <a name="improved-administration-experience-in-microsoft-365-device-management"></a>Továbbfejlesztett adminisztrációs élmény az Microsoft 365-eszközök felügyeletében

Mostantól általánosan elérhető a frissített és áramvonalas felügyeleti felület a Microsoft 365 Eszközkezelő Specialist munkaterületen a [https://devicemanagement.microsoft.com on ](https://devicemanagement.microsoft.com), beleértve a következőket:

- **Frissített navigáció**: egy egyszerűsített, első szintű navigációt talál, amely logikailag csoportosítja a szolgáltatásokat.
- **Új platform szűrők**: egyetlen platformot választhat ki, amely csak a kiválasztott platformhoz tartozó szabályzatokat és alkalmazásokat jeleníti meg az eszközök és alkalmazások oldalain.
- **Új Kezdőlap**: gyorsan megtekintheti a szolgáltatás állapotát, a bérlőt, a híreket stb. az új kezdőlapon.

További információ ezekről a fejlesztésekről: [Enterprise Mobility + Security blogbejegyzés](https://go.microsoft.com/fwlink/?linkid=2109094) a Microsoft technikai Közösség webhelyén.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="add-mobile-threat-defense-apps-to-unenrolled-devices----3005337---"></a>Mobile Threat Defense-alkalmazások hozzáadása a nem regisztrált eszközökhöz <!-- 3005337 -->
Létrehozhat egy Intune app Protection-szabályzatot, amely letilthatja vagy szelektíven törölheti a felhasználók vállalati adatait az eszköz állapota alapján. Az eszköz állapota a kiválasztott Mobile Threat Defense-(MTD-) megoldás használatával van meghatározva. Ez a funkció ma már az Intune-ban regisztrált eszközökön van, eszköz-megfelelőségi beállításként. Ezzel az új funkcióval kiterjesztjük a fenyegetések észlelését egy Mobile Threat Defense-gyártótól a nem regisztrált eszközökön való működéshez. Android rendszeren a szolgáltatáshoz a legújabb Céges portál van szükség az eszközön. IOS rendszeren ez a funkció akkor használható, ha az alkalmazások integrálják a legújabb Intune SDK-t (v 12.0.15 +). Frissítjük az Újdonságok témakört, amikor az első alkalmazás elfogadja a legújabb Intune SDK-t. A fennmaradó alkalmazások folyamatosan elérhetővé válnak. További információ: [a Mobile Threat Defense-alkalmazás védelmi szabályzatának létrehozása az Intune](~/protect/mtd-app-protection-policy.md)-nal.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices----2266073----"></a>Új eszköz belső vezérlőprogram-konfigurációs felületének profilja a Windows 10 és újabb rendszerű eszközökhöz <!-- 2266073  -->

Windows 10 és újabb rendszereken létrehozhat egy eszköz-konfigurációs profilt a beállítások és szolgáltatások vezérléséhez (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **Windows 10 és újabb verziók** a platformhoz). Ebben a frissítésben egy új, az eszköz belső vezérlőprogram-konfigurációs felületének profilja van, amely lehetővé teszi az Intune számára az UEFI-(BIOS-) beállítások kezelését. Ennek a funkciónak a bevezetési folyamata minden ügyfelünk számára folyamatban van, és a következő hét végére várhatóan elvégezhető.

A szolgáltatással kapcsolatos további információkért lásd: [DFCI-profilok használata Windows-eszközökön Microsoft Intune](../configuration/device-firmware-configuration-interface-windows.md).

A következőkre vonatkozik:
- Windows 10 RS5 (1809) és újabb támogatott belső vezérlőprogram

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="toggle-to-only-show-enrollment-status-page-on-devices-provisioned-by-out-of-box-experience-oobe---3959566--"></a>Váltás csak a regisztrációs állapot megjelenítése lapra a beépített felhasználói felülettel (OOBE) kiépített eszközökön <!--3959566-->
Most úgy is dönthet, hogy csak az Autopilot OOBE által kiépített eszközök regisztrációs állapot lapját jeleníti meg.

Az új váltógomb megjelenítéséhez válassza az **Intune** > **eszközök beléptetése** > **Windows** -beléptetés > **regisztráció állapota lap** > **profil létrehozása** > **Beállítások** > **csak a kezdőélmény (OOBE) használatával kiépített lapok megjelenítése az eszközökön**.


<!-- ########################## -->
## <a name="week-of-october-14-2019"></a>2019. október 14-i hét

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Alkalmazáskezelés 

#### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956-----"></a>Elérhető Google Play-alkalmazások jelentéskészítése androidos munkahelyi profilokhoz <!-- 3041956   -->
Az Android Enterprise munkahelyi profil, dedikált és teljes körűen felügyelt eszközökön elérhető alkalmazások telepítésének megtekintheti az alkalmazások telepítési állapotát, valamint a felügyelt Google Play-alkalmazások telepített verzióját. További információ: [az alkalmazás-védelmi szabályzatok figyelése](~/apps/app-protection-policies-monitor.md), [androidos munkahelyi profilú eszközök kezelése az Intune](~/enrollment/android-enterprise-overview.md) -nal és a [felügyelt Google Play-alkalmazás típusa](~/apps/apps-add-android-for-work.md#managed-google-play-app-types).

#### <a name="microsoft-edge-version-77-and-later-for-windows-10-and-macos-public-preview----3872025-4678761----"></a>A Microsoft Edge 77-es és újabb verziói a Windows 10 és a macOS rendszerhez (nyilvános előzetes verzió) <!-- 3872025, 4678761  -->
A Microsoft Edge 77-es és újabb verziói elérhetők lesznek a Windows 10 és macOS rendszerű számítógépeken való üzembe helyezéshez. 

A nyilvános előzetes verzió a Windows 10 **fejlesztési** és **bétaverziós** csatornáit, valamint a MacOS-hez készült **bétaverziót** kínálja. A központi telepítés csak angol (EN) nyelven érhető el, de a végfelhasználók a **beállítások**  > **nyelvek**területen módosíthatják a böngésző megjelenítési nyelvét. A Microsoft Edge egy, a rendszerkörnyezetben és hasonló architektúrákban telepített Win32-alkalmazás (x86-OS és x64-es OS-es x64-es alkalmazás). Emellett a böngésző automatikus frissítései alapértelmezés szerint be vannak **kapcsolva** , és a Microsoft Edge nem távolítható el. További információ: a [Microsoft Edge for Windows 10 hozzáadása a Microsoft Intune](~/apps/apps-windows-edge.md) és a [Microsoft Edge dokumentációhoz](https://go.microsoft.com/fwlink/?linkid=2103823).

#### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui----4102027-4102029-----"></a>Az App Protection felhasználói felületének és az iOS-alkalmazások kiépítési felhasználói felületének frissítése <!-- 4102027, 4102029   -->
Az alkalmazás-védelmi szabályzatok létrehozásához és szerkesztéséhez, valamint az iOS-alkalmazások létesítési profiljaihoz az Intune-ban frissült a felhasználói felület. A felhasználói felület változásai a következők:
- Egyszerűsített felhasználói felület, amely egy, egy panelen belül tömörített varázsló-stílusú formátumot használ. 
- A létrehozási folyamatra vonatkozó frissítés, amely tartalmazza a hozzárendeléseket.
- A tulajdonságok megtekintésekor beállított összes dolog összefoglaló lapja új házirend létrehozása vagy egy tulajdonság szerkesztésekor. Emellett a tulajdonságok szerkesztésekor az összefoglalás csak a szerkesztett tulajdonságok kategóriájában lévő elemek listáját jeleníti meg.

További információ: [az alkalmazás-védelmi szabályzatok létrehozása és kiosztása](~/apps/app-protection-policies.md) és [az iOS-alkalmazások létesítési profiljainak használata](~/apps/app-provisioning-profile-ios.md).

#### <a name="intune-guided-scenarios----4850318-4831296-3610611----"></a>Az Intune interaktív forgatókönyvei <!-- 4850318, 4831296, 3610611  -->
Az Intune-nal olyan interaktív forgatókönyvek érhetők el, amelyek segítséget nyújtanak egy adott feladat vagy feladatok elvégzéséhez az Intune-ban. Az interaktív forgatókönyvek egy teljes körű használati esethez igazított lépések (munkafolyamat) testreszabott sorozata. A gyakori forgatókönyvek a rendszergazda, a felhasználó vagy az eszköz által a szervezeten belül játszott szerepkör alapján vannak meghatározva. Ezek a munkafolyamatok általában gondosan előkészített profilok, beállítások, alkalmazások és biztonsági vezérlők gyűjteményét igénylik a legjobb felhasználói élmény és biztonság érdekében. Az új interaktív forgatókönyvek a következők:
- [A Microsoft Edge for Mobile üzembe helyezése](~/fundamentals/guided-scenarios-edge.md)
- [Biztonságos Microsoft Office Mobile apps](~/fundamentals/guided-scenarios-office-mobile.md) 
- [Felhőben felügyelt modern asztal](~/fundamentals/guided-scenarios-cloud-managed-pc.md)

További információ: az [Intune interaktív forgatókönyvek áttekintése](guided-scenarios-overview.md).

#### <a name="additional-app-configuration-variable-available----4969237-----"></a>További elérhető az alkalmazás konfigurációs változója <!-- 4969237   -->
Alkalmazás-konfigurációs házirend létrehozásakor a konfigurációs beállítások részeként felveheti a `AAD Device ID` konfigurációs változót. Az Intune-ban válassza az **ügyfélalkalmazások** > **alkalmazás-konfigurációs szabályzatok** > **Hozzáadás**lehetőséget. Adja meg a konfigurációs szabályzat adatait, és válassza a **konfigurációs beállítások** lehetőséget a **konfigurációs beállítások** panel megtekintéséhez. További információ: [alkalmazás-konfigurációs házirendek a felügyelt Android Enterprise-eszközökhöz – a Configuration Designer használata](~/apps/app-configuration-policies-use-android.md#use-the-configuration-designer).


#### <a name="create-groups-of-management-objects-called-policy-sets----3762880----"></a>Házirend-készletek nevű felügyeleti objektumok csoportjainak létrehozása <!-- 3762880  -->
A házirend-készletek lehetővé teszik, hogy a már meglévő felügyeleti entitásokra mutató hivatkozásokat hozzon létre, amelyeket egyetlen fogalmi egységként kell azonosítani, megcélozni és figyelni. A házirend-készletek nem helyettesítik a meglévő fogalmakat vagy objektumokat. Továbbra is hozzárendelhet egyedi objektumokat az Intune-ban, és egy házirend-készlet részeként egyedi objektumokat is hivatkozhat. Ezért az egyes objektumok módosításai a házirend-készletben is megjelennek.  Az Intune-ban a **házirend-készletek**  > **Létrehozás** gombra kattintva hozhat létre új házirend-készletet. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="ui-update-for-creating-and-editing-windows-10-update-rings-----4099089-----------"></a>Felhasználói felület frissítése a Windows 10-es frissítési gyűrűk létrehozásához és szerkesztéséhez  <!-- 4099089         -->
Frissítettük az Intune [-hoz készült Windows 10-es frissítési körök létrehozására és szerkesztésére](../protect/windows-update-for-business-configure.md#create-and-assign-update-rings) szolgáló felhasználói felületet. A felhasználói felület változásai a következők:  
- A varázsló-stílusú formátum egyetlen konzolos panelre van tömörítve, amely az előzőekben látható, az Update Rings konfigurálásakor korábban látott panelre mutat.   
- A felülvizsgált munkafolyamat hozzárendeléseket tartalmaz, mielőtt befejezi a gyűrű kezdeti konfigurációját.
- Egy összefoglaló lap, amellyel áttekintheti az összes olyan konfigurációt, amelyeket az új frissítési kör mentése és telepítése előtt használhat. Egy frissítési kör szerkesztésekor az összefoglalás csak a szerkesztett tulajdonságok kategóriáján belül beállított elemek listáját jeleníti meg.

#### <a name="ui-update-for-creating-and-editing-ios-software-update-policy-----4099090---------"></a>Felhasználói felület frissítése iOS szoftverfrissítési szabályzat létrehozásához és szerkesztéséhez  <!-- 4099090       --> 
Frissítettük az Intune-hoz készült iOS-szoftverfrissítési szabályzatok [létrehozásához](../protect/software-updates-ios.md#configure-the-policy) és [SZERKESZTÉSÉHEZ](../protect/software-updates-ios.md#edit-a-policy) szükséges felhasználói felületet.  A felhasználói felület változásai a következők:  
- A varázsló-stílusú formátum egyetlen konzolos panelre van tömörítve, amely a korábban a frissítési szabályzatok konfigurálásakor megtekintett panel terjeszkedésével foglalkozik.   
- A módosított munkafolyamat hozzárendeléseket tartalmaz, mielőtt befejezi a szabályzat kezdeti konfigurációját.
- Egy összefoglaló lap, amellyel áttekintheti az összes olyan konfigurációt, amelyeket az új szabályzat mentése és telepítése előtt használhat. A szabályzatok szerkesztésekor az összefoglalás csak a szerkesztett tulajdonságok kategóriáján belül beállított elemek listáját jeleníti meg.

#### <a name="engaged-restart-settings-are-removed-from-windows-update-rings------4464404---wnready-----"></a>Az újraindítási beállítások el lesznek távolítva a Windows Update gyűrűkből  <!--  4464404   WNReady   -->
Amint azt korábban bejelentettük, az Intune Windows 10-es frissítési gyűrűk mostantól [támogatják a határidőkhöz tartozó beállításokat](../protect/windows-update-settings.md) , és a továbbiakban nem támogatják az *újraindítást*. A *felvállalt újraindítási* beállítások már nem érhetők el, ha az Intune-ban konfigurálja vagy kezeli a frissítési köröket.  

Ez a módosítás a legújabb [Windows-karbantartási változásokkal](https://docs.microsoft.com//windows/whats-new/whats-new-windows-10-version-1903#servicing) és a Windows 10 1903 vagy újabb rendszerű eszközökön is igazodik, és a *határidők* felülírják a *felvállalt újraindítási*konfigurációkat.

#### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-work-profile-devices----4760025-----"></a>Az ismeretlen forrásból származó alkalmazások telepítésének megakadályozása az Android Enterprise Work profiling-eszközökön <!-- 4760025   -->
Az Android Enterprise Work Profile eszközein a felhasználók soha nem telepíthetnek ismeretlen forrásból származó alkalmazásokat. Ebben a frissítésben van egy új beállítás – megakadályozza, hogy **az alkalmazások telepítése ismeretlen forrásból történjen a személyes profilban**. Alapértelmezés szerint ez a beállítás megakadályozza, hogy a felhasználók az ismeretlen forrásból származó alkalmazásokat az eszköz személyes profiljába töltsenak be.

A konfigurálható beállítás megjelenítéséhez nyissa meg az [Android Enterprise Device Settings lehetőséget az Intune-nal való funkciók engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-android-for-work.md).

A következőkre vonatkozik:
- Androidos vállalati munkahelyi profil

#### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices----4816339-----"></a>Globális HTTP-proxy létrehozása androidos vállalati eszköz tulajdonosi eszközein <!-- 4816339   -->
Az Android Enterprise rendszerű eszközökön konfigurálhat egy globális HTTP-proxyt, hogy megfeleljen a szervezete webböngészési szabványainak (az**eszköz konfigurációjának**  > **profiljai**  > **profil létrehozása**  > **Android Enterprise** for platform > **eszköz tulajdonosa > eszköz korlátozásai** a profil típusa > a **kapcsolat**). A konfigurálást követően az összes HTTP-forgalom ezt a proxyt fogja használni.

A szolgáltatás konfigurálásához és az összes konfigurált beállítás megjelenítéséhez nyissa meg az [androidos vállalati eszköz beállításait, és engedélyezze vagy korlátozza a szolgáltatásokat az Intune használatával](../configuration/device-restrictions-android-for-work.md).

A következőkre vonatkozik:
- Androidos vállalati eszköz tulajdonosa

#### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-device-administrator-and-android-enterprise----5021055-----"></a>Az Automatikus csatlakozás beállítás el lesz távolítva a Wi-Fi profilokban az Android-eszköz rendszergazdája és az Android Enterprise <!-- 5021055   -->
Az Android-eszköz rendszergazdája és az Android Enterprise rendszerű eszközökön létrehozhat egy Wi-Fi profilt különböző beállítások konfigurálásához (**eszköz konfigurációja**  > **profilok**  > **profil létrehozása**  > **Android-eszköz rendszergazdai** vagy **Android Enterprise** platform > **Wi-Fi** profil típusa). Ebben a frissítésben a **kapcsolat automatikus** beállítása el lesz távolítva, mivel az [Android nem támogatja](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Ha ezt a beállítást egy Wi-Fi profilban használja, előfordulhat, hogy észrevette, hogy a **Csatlakozás automatikusan** nem működik. Semmilyen műveletet nem kell elvégeznie, de vegye figyelembe, hogy ez a beállítás el lesz távolítva az Intune felhasználói felületén.

Az aktuális beállítások megtekintéséhez lépjen az [Android Wi-Fi beállítások](../configuration/wi-fi-settings-android.md) vagy az [Android Enterprise Wi-Fi beállítások](../configuration/wi-fi-settings-android-enterprise.md)elemre.

A következőkre vonatkozik:
- Android-eszköz rendszergazdája 
- Vállalati Android


#### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices----5199328-----"></a>Új eszköz konfigurációs beállításai felügyelt iOS-és iPadOS-eszközökhöz <!-- 5199328   -->
IOS-és iPadOS-eszközökön létrehozhat egy profilt az eszközök funkcióinak és beállításainak korlátozásához (**eszköz konfigurációja**  > **profilok**  > **profil létrehozása**  > **iOS/iPadOS** platform > **eszközhöz** a profil típusának korlátozásai). Ebben a frissítésben új beállítások vezérelhetők: 
- Hozzáférés hálózati meghajtóhoz a Files alkalmazásban  
- Hozzáférés USB-meghajtóhoz a Files alkalmazásban 
- Wi-Fi mindig be van kapcsolva 

A beállítások megtekintéséhez lépjen az iOS- [eszközbeállítások elemre az Intune-t használó funkciók engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-ios.md).

A következőkre vonatkozik:
- iOS 13,0 és újabb verziók
- iPadOS 13,0 és újabb verziók

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment----4350697-----"></a>Itt adhatja meg, hogy az operációs rendszer mely operációsrendszer-verzióit regisztrálja munkahelyi profillal vagy az eszközök rendszergazdai regisztrálásával <!-- 4350697   -->
Az Intune-eszközök típusának korlátozásai segítségével megadhatja, hogy mely felhasználói eszközök fogják használni az Android Enterprise munkahelyi profil regisztrációját vagy az Android-eszközök rendszergazdai regisztrációját.  További információkért lásd a [regisztrációs korlátozások beállítása](../enrollment/enrollment-restrictions-set.md)című témakört.

#### <a name="windows-autopilot-deployment-reports----3856172---"></a>A Windows Autopilot üzembe helyezési jelentései <!-- 3856172 -->
Egy új jelentés a Windows Autopilot szolgáltatáson keresztül üzembe helyezett összes eszközt részletezi. További információ: [Autopilot Deployment Report](../enrollment/enrollment-autopilot.md#autopilot-deployments-report). Ennek a funkciónak a bevezetési folyamata minden ügyfelünk számára folyamatban van, és a következő hét végére várhatóan elvégezhető.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Eszközkezelés

#### <a name="new-restrictions-for-renaming-windows-devices----3478938----"></a>Új korlátozások a Windows-eszközök átnevezéséhez <!-- 3478938  -->
Egy Windows-eszköz átnevezése során új szabályokat kell követnie:
- legfeljebb 15 karakter (63 bájtnál kisebbnek vagy azzal egyenlőnek kell lennie, a záró NULL értékkel nem együtt)
- Nem null vagy üres karakterlánc
- Engedélyezett ASCII: betűk (a-z, A-Z), számok (0-9) és kötőjelek
- Engedélyezett Unicode: karakter > = 0x80, érvényes UTF8-nak kell lennie, az IDN-leképezhető (azaz a RtlIdnToNameprepUnicode sikeresek, lásd: RFC 3492)
- A nevek nem tartalmazhatnak csak számokat
- Nincs szóköz a névben
- Nem engedélyezett karakterek: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *)

 További információ: [eszköz átnevezése az Intune-ban](../remote-actions/device-rename.md).

### <a name="new-android-report-on-devices-overview-page----4924364---"></a>Új Android-jelentés az eszközök áttekintése oldalon <!-- 4924364 -->
Az eszközök áttekintése oldal új jelentése megjeleníti, hogy hány Android-eszköz van regisztrálva az egyes eszközkezelés megoldásokban. Ez a diagram a munkahelyi profilt, a teljes körűen felügyelt, a dedikált és az eszköz-rendszergazda által beléptetett eszközök számát mutatja. A jelentés megtekintéséhez válassza az **Intune**  > **eszközök**  > **Áttekintés**elemet.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Eszköz biztonsága 

#### <a name="pkcs-certificates-for-macos-----1333650---------"></a>PKCS-tanúsítványok macOS rendszerhez  <!-- 1333650       -->
Mostantól [HASZNÁLHAT PKCS-tanúsítványokat MacOS használatával](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile). A PKCS-tanúsítványt a macOS-profil típusaként kiválaszthatja, és olyan felhasználói és eszköz-tanúsítványokat telepíthet, amelyek [testreszabott tulajdonosi és tulajdonosi alternatív név mezőket](../protect/certficates-pfx-configure.md#subject-name-format-for-macos)tartalmazhatnak.  

A macOS-hez készült PKCS-tanúsítvány egy új beállítást is támogat, _lehetővé téve az összes alkalmazás elérését_. Ezzel a beállítással engedélyezheti, hogy az összes társított alkalmazás hozzáférhessen a tanúsítvány titkos kulcsához.  A beállítással kapcsolatos további információkért tekintse meg az Apple dokumentációját https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf címen.

####   <a name="derived-credentials-to-provision-ios-mobile-devices-with-certificates----------1736036-1736037-1772050-2777333-----------"></a>Származtatott hitelesítő adatok a tanúsítványokkal rendelkező iOS-mobileszközök kiépítéséhez      <!--  1736036, 1736037, 1772050, 2777333         -->  
Az Intune támogatja a [származtatott hitelesítő adatok](../protect/derived-credentials.md) hitelesítési módszerként való használatát, valamint az S/MIME-aláírást és az iOS-eszközök titkosítását. A származtatott hitelesítő adatok a *nemzeti szabványügyi és Technológiai Intézet (NIST) 800-157* standard implementációja, amely tanúsítványokat helyez üzembe az eszközökön.  

A származtatott hitelesítő adatok a személyes személyazonosság-ellenőrzés (PIV) vagy a Common Card (CAC) kártya (például intelligens kártya) használatára támaszkodnak. Ahhoz, hogy egy származtatott hitelesítő adatot kapjon a mobileszköz számára, a felhasználók a Céges portál alkalmazásban kezdődnek, és egy, a használt szolgáltatóra jellemző regisztrációs munkafolyamatot követnek.  Az összes szolgáltatóval közösen az intelligens kártyát kell használni a számítógépen a származtatott hitelesítőadat-szolgáltatón való hitelesítéshez. Ez a szolgáltató ezután kibocsátja a tanúsítványt a felhasználó intelligens kártyáján található eszközre.  

Az Intune a következő származtatott hitelesítőadat-szolgáltatókat támogatja:   
- DISA fajtatiszta
- Entrust Datacard
- Közbenjárni

Származtatott hitelesítő adatokat használ a VPN-, Wi-Fi-és e-mail-alapú eszköz-konfigurációs profilok hitelesítési módszere. Ezeket az alkalmazás-hitelesítéshez, valamint az S/MIME-aláíráshoz és a titkosításhoz is használhatja.  

További információ a standardról: [származtatott PIV hitelesítő adatok](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) a www.nccoe.nist.gov címen.

#### <a name="use-graph-api-to-specify-a-on-premises-user-principal-name-as-a-variable-for-scep-certificates--------5437939----------"></a>A Graph API használatával adja meg a helyszíni egyszerű felhasználónevet változóként a SCEP-tanúsítványok számára.    <!--  5437939        -->  
Az [Intune-Graph API](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0)használatakor megadhatja a onPremisesUserPrincipalName változóként a tulajdonos alternatív NEVEKÉNT (San) a SCEP-tanúsítványokhoz.



<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>2019. szeptember 23-i hét

#### <a name="ios-user-enrollment-in-preview----4817900---"></a>iOS-felhasználók regisztrációja az előzetes verzióban <!-- 4817900 -->
Az Apple iOS 13,1 kiadásában a felhasználók beléptetése, valamint az iOS-eszközökhöz készült egyszerűsített felügyelet új formája szerepel. A személyes tulajdonú eszközök esetében az eszközök beléptetése vagy az automatikus eszközök beléptetése (korábban Készülékregisztrációs program) helyett is felhasználható. Az Intune előzetes verziója a következő lépésekkel támogatja a szolgáltatáskészlet támogatását:

- Felhasználói csoportokba való felhasználói regisztráció megcélzása.
- Lehetővé teszi a végfelhasználók számára, hogy az eszközük regisztrálásakor a könnyebb felhasználói regisztráció vagy erősebb eszközök beléptetése között választhatnak.

Az iOS 13,1-es verziójától kezdődően a 9/24/2019-es verziótól kezdve a frissítések minden ügyfelünk számára elérhetők lesznek, és a következő hét végére várhatóan befejeződtek.
A következőkre vonatkozik:

iOS 13,1 és újabb verziók

#### <a name="intune-support-for-ipados-and-ios-131-devices---5439574--"></a>Intune-támogatás a iPadOS és az iOS 13,1-eszközökhöz <!--5439574-->
Az Intune mostantól támogatja a iPadOS és az iOS 13,1-eszközök kezelését is. További információkat [ebben a blogban](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094) talál.

<!-- ########################## -->

## <a name="week-of-september-16-2019"></a>2019. szeptember 16-i hét

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Alkalmazáskezelés 

#### <a name="managed-google-play-private-lob-apps----1464182----"></a>Felügyelt Google Play Private LOB-alkalmazások <!-- 1464182  -->
Az Intune mostantól lehetővé teszi a rendszergazdák számára, hogy privát Android LOB-alkalmazásokat tegyenek közzé a Google Play szolgáltatásban az Intune-konzolon beágyazott iframe használatával.  Korábban a rendszergazdák számára szükséges, hogy a LOB-alkalmazásokat közvetlenül a Google Play közzétételi konzolján tegye közzé, amely több lépést igényelt, és időigényes volt. Ez az új funkció lehetővé teszi a LOB-alkalmazások egyszerű közzétételét a lépések minimális készletével anélkül, hogy az Intune-konzolt el kellene hagynia.  A rendszergazdáknak többé nem kell manuálisan regisztrálniuk a Google-fejlesztőként, és a továbbiakban nem kell fizetniük a Google $25 regisztrációs díját.  A felügyelt Google Play szolgáltatást használó androidos vállalati felügyeleti forgatókönyvek bármelyike kihasználhatja ezt a funkciót (munkahelyi profil, dedikált, teljes körűen felügyelt és nem regisztrált eszközök). Az Intune-ból válassza a **Client apps** > **alkalmazások** > **Hozzáadás**elemet. Ezután válassza a **felügyelt Google Play** lehetőséget az **alkalmazás típusa** listából. A felügyelt Google Play-alkalmazásokkal kapcsolatos további információkért lásd: [felügyelt Google Play-alkalmazások hozzáadása androidos vállalati eszközökhöz az Intune](../apps/apps-add-android-for-work.md)-nal.

#### <a name="windows-company-portal-experience----1473353-3598357---"></a>Windows Céges portál-élmény <!-- 1473353, 3598357 -->
A Windows Céges portál frissítése folyamatban van. Az alkalmazások lapon több szűrőt is használhat a Windows Céges portálon belül. Az eszköz részletes felhasználói felülete is frissül. Ezen frissítések minden ügyfelünk számára folyamatban vagyunk, és a következő hét végére várhatóan elvégezhető.

#### <a name="macos-support-for-web-apps----3174427---"></a>macOS-támogatás webes alkalmazásokhoz <!-- 3174427 -->
Webalkalmazások, amelyek lehetővé teszik a webes URL-címekhez való parancsikonok hozzáadását a Dockon a macOS Céges portál használatával. A végfelhasználók a macOS Céges portál webalkalmazáshoz tartozó alkalmazás részletei lapon érhetik el a **telepítési** műveletet. A **Webhivatkozás** alkalmazás típusával kapcsolatos további információkért lásd: [alkalmazások hozzáadása a Microsoft Intunehez](../apps/apps-add.md) és [webalkalmazások hozzáadása Microsoft Intunehoz](../apps/web-app.md).

#### <a name="macos-support-for-vpp-apps----3173501----"></a>a macOS-alkalmazások macOS-támogatása <!-- 3173501  -->
az Apple Business Managerrel megvásárolt macOS-alkalmazások a konzolon jelennek meg, amikor az Apple VPP-tokenek szinkronizálva vannak az Intune-ban. Az Intune-konzollal rendelhet hozzá, vonhat vissza és rendelhet hozzá eszközöket és felhasználó-alapú licenceket a csoportokhoz. A Microsoft Intune segítségével kezelheti a vállalat által a cégnél való használatra megvásárolt VPP-alkalmazásokat:

- Licencinformációk jelentése az App Store-ból.
- A felhasznált licencek számának nyilvántartása.
- Segít megelőzni az alkalmazás több példányának telepítését, mint amennyit Ön birtokol.

Az Intune-nal és a VPP-vel kapcsolatos további információkért lásd: [mennyiségi programban vásárolt alkalmazások és könyvek kezelése Microsoft Intuneokkal](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support----2871756----"></a>Felügyelt Google Play iframe-támogatás <!-- 2871756  -->
Az Intune mostantól támogatást nyújt a webhivatkozások hozzáadásához és kezeléséhez közvetlenül az Intune-konzolon a felügyelt Google Play iframe használatával.  Ez lehetővé teszi, hogy a rendszergazdák elküldjék az URL-címet és az ikont, majd ezeket a hivatkozásokat a normál Android-alkalmazásokhoz hasonló eszközökre telepítse. A felügyelt Google Play szolgáltatást használó androidos vállalati felügyeleti forgatókönyvek bármelyike kihasználhatja ezt a funkciót (munkahelyi profil, dedikált, teljes körűen felügyelt és nem regisztrált eszközök). Az Intune-ból válassza a **Client apps** > **alkalmazások** > **Hozzáadás**elemet. Ezután válassza a **felügyelt Google Play** lehetőséget az **alkalmazás típusa** listából. A felügyelt Google Play-alkalmazásokkal kapcsolatos további információkért lásd: [felügyelt Google Play-alkalmazások hozzáadása androidos vállalati eszközökhöz az Intune](../apps/apps-add-android-for-work.md)-nal.

#### <a name="silently-install-android-lob-apps-on-zebra-devices----4252734----"></a>Android LOB-alkalmazások csendes telepítése a zebra-eszközökön <!-- 4252734  -->
Ha az androidos üzletági (LOB) alkalmazásokat a [Zebra-eszközökre](../configuration/android-zebra-mx-overview.md)telepíti, és nem kéri a LOB-alkalmazás letöltését és telepítését, akkor az alkalmazást csendesen is telepítheti. Az Intune-ban válassza a **Client apps** > **alkalmazások** > **Hozzáadás**elemet. Az **Alkalmazás hozzáadása** panelen válassza az **Üzletági alkalmazás** lehetőséget. További információ: [androidos üzletági alkalmazás hozzáadása a Microsoft Intunehoz](../apps/lob-apps-android.md).

Jelenleg a LOB-alkalmazás letöltése után a rendszer **letölti a sikerről** szóló értesítést a felhasználó eszközén. Az értesítés csak akkor törölhető, ha az értesítési árnyékban az **összes törlése** elemre koppint. Ez az értesítési probléma egy közelgő kiadásban fog megjelenni, és a telepítés teljesen csendes marad, és nem jelenik meg vizuális mutató.

#### <a name="read-and-write-graph-api-operations-for-intune-apps----5031704----"></a>Az Intune-alkalmazások Graph API műveleteinek olvasása és írása <!-- 5031704  -->
Az alkalmazások az Intune-Graph API az olvasási és írási műveletekkel is meghívhatják az alkalmazás identitása felhasználói hitelesítő adatok nélkül. További információ az Intune-hoz készült Microsoft Graph API eléréséről: az [Intune használata a Microsoft Graphban](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios----3586942----"></a>Az iOS-hez készült Intune app SDK védett adatmegosztása és titkosítása <!-- 3586942  -->
Az iOS-hez készült Intune app SDK 256 bites titkosítási kulcsokat használ, ha az adatvédelmi szabályzatok lehetővé teszik a titkosítást. Minden alkalmazásnak rendelkeznie kell egy SDK-verzió 8.1.1 a védett adatmegosztás engedélyezéséhez.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438-----"></a>Az iOS rendszerhez készült IKEv2 VPN-profilok támogatása <!-- 1943438   -->
Ebben a frissítésben VPN-profilokat hozhat létre az iOS natív VPN-ügyfél számára a IKEv2 protokoll használatával. A IKEv2 új kapcsolattípus az **eszköz konfigurációja** > **profilok** > **profil létrehozása** > **iOS** for platform > **VPN** a profil típusa > **kapcsolattípus**.

Ezek a VPN-profilok a natív VPN-ügyfelet konfigurálja, így a rendszer nem telepíti a VPN-ügyfélszoftvert, és nem küldi azokat a felügyelt eszközökre Ehhez a szolgáltatáshoz regisztrálni kell az eszközöket az Intune-ban (MDM-regisztráció).

Az aktuálisan konfigurálható VPN-beállítások megjelenítéséhez nyissa [meg a VPN-beállítások konfigurálása iOS-eszközökön](../configuration/vpn-settings-ios.md)című témakört.

A következőkre vonatkozik:
- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type----4886161-----"></a>A regisztrációs típus megjeleníti az eszközök funkcióit, az eszközök korlátozásait és a bővítményi profilokat az iOS-és macOS-beállításokhoz. <!-- 4886161   -->

Az Intune-ban létrehozhat profilokat az iOS-és macOS-eszközökhöz (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **iOS** vagy **MacOS** a platform > **eszköz funkciói**, **eszköz** a profil típusának korlátozásai vagy **bővítményei** . 

Ebben a frissítésben az Intune-portálon elérhető beállítások a beléptetési típus szerint vannak kategorizálva:

- iOS
  - Felhasználó beléptetése
  - Eszközök beléptetése
  - Automatikus eszközök beléptetése (felügyelt)
  - Minden regisztrációs típus

- macOS
  - Felhasználó által jóváhagyott
  - Eszközök beléptetése
  - Automatikus eszközök beléptetése
  - Minden regisztrációs típus

A következőkre vonatkozik:
- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode----4892835-----"></a>A teljes képernyős módban futó, felügyelt iOS-eszközök új hang-vezérlési beállításai <!-- 4892835   -->
Az Intune-ban házirendeket hozhat létre a felügyelt iOS-eszközök kioszkként való futtatásához vagy dedikált eszközként (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **iOS** platformra > **eszköz korlátozásai** a profil típusa > **kioszk**). 

Ebben a frissítésben új beállítások vezérelhetők:
- **Hangvezérlés**: lehetővé teszi a hangvezérelt vezérlést az eszközön kioszk módban.
- A **hangvezérlés módosítása**: lehetővé teszi a felhasználók számára, hogy kioszk módban módosítsák az eszköz hangvezérlési beállítását.

Az aktuális beállítások megjelenítéséhez nyissa meg az [iOS kioszk beállításait](../configuration/device-restrictions-ios.md#kiosk).

A következőkre vonatkozik:
- iOS 13,0 és újabb verziók

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices----4893175-----"></a>Egyszeri bejelentkezés használata az iOS-és macOS-eszközökön futó alkalmazásokhoz és webhelyekhez <!-- 4893175   -->
Ebben a frissítésben az iOS-és macOS-eszközökre vonatkozó új egyszeri bejelentkezési beállítások vannak (**Device configuration** > **profilok** > **profil létrehozása** > **iOS** vagy **MacOS** a platform > **eszköz szolgáltatásaihoz** a profil típusa).

Ezekkel a beállításokkal konfigurálhatja az egyszeri bejelentkezési élményt, különösen a Kerberos-hitelesítést használó alkalmazásokhoz és webhelyekhez. Választhat egy általános hitelesítő adatok egyszeri bejelentkezési alkalmazás-bővítménye és az Apple beépített Kerberos-bővítménye közül.

Az eszköz aktuálisan konfigurálható szolgáltatásainak megtekintéséhez nyissa meg az [iOS-eszközök funkcióit](../configuration/ios-device-features-settings.md) és a [MacOS-eszközök funkcióit](../configuration/macos-device-features-settings.md).

A következőkre vonatkozik:
- iOS 13,0 és újabb verziók
- macOS 10,15 és újabb verziók

#### <a name="associate-domains-to-apps-on-macos-1015-devices----4898079-----"></a>Tartományok hozzárendelése macOS-10.15 és-eszközökön futó alkalmazásokhoz <!-- 4898079   -->
MacOS-eszközökön különböző funkciókat konfigurálhat, és leküldheti ezeket a funkciókat az eszközökre egy szabályzat használatával (**eszköz konfigurációja** > **profilok** > **create Profile** > **MacOS** a platform > **eszközhöz** a profil típusának jellemzői). Ebben a frissítésben tartományokat rendelhet az alkalmazásaihoz. Ez a szolgáltatás segít megosztani a hitelesítő adatokat az alkalmazással kapcsolatos webhelyekkel, és használható az Apple egyszeri bejelentkezési bővítménnyel, az univerzális hivatkozásokkal és a jelszavak automatikus kitöltésével. 

Az aktuálisan konfigurálható szolgáltatások megjelenítéséhez nyissa meg a [MacOS-eszköz szolgáltatás beállításait az Intune-ban](../configuration/macos-device-features-settings.md).

A következőkre vonatkozik:
- macOS 10,15 és újabb verziók

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices----4928474-----"></a>Az iOS-es felügyelt eszközökön lévő alkalmazások megjelenítéséhez vagy elrejtéséhez használja az iTunes alkalmazás-áruház URL-címe "iTunes" és "alkalmazások" elemét. <!-- 4928474   --> 
Az Intune-ban szabályzatokat hozhat létre a felügyelt iOS-eszközökön lévő alkalmazások megjelenítéséhez vagy elrejtéséhez (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **iOS** platformra > **eszköz korlátozásai** Profil típusa > **alkalmazások megjelenítése vagy elrejtése**). 

Megadhatja az iTunes alkalmazás-áruház URL-címét, például `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. Ebben a frissítésben a `apps` és a `itunes` is használható az URL-címben, például:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

További információ ezekről a beállításokról: [alkalmazások megjelenítése vagy elrejtése](../configuration/device-restrictions-ios.md#show-or-hide-apps).

A következőkre vonatkozik:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>A Windows 10-es megfelelőségi szabályzat jelszavának típusa világosabb és egyező CSP<!-- 5138985 -->
Windows 10 rendszerű eszközökön létrehozhat olyan megfelelőségi szabályzatot, amely meghatározott jelszó-szolgáltatásokat igényel (**eszköz megfelelőségi** > **szabályzatok** > **házirend létrehozása** > **Windows 10 és újabb verziók** a platform > **rendszer számára Biztonság**). Ebben a frissítésben:
- A **jelszó típusú** értékek világosabbak, és frissülnek, hogy megfeleljenek a [DEVICELOCK/AlphanumericDevicePasswordRequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)-nek.
- A **jelszó lejárati ideje (nap)** beállítás frissült, így az 1-730 napos értékek is megengedettek. 

A Windows 10 megfelelőségi beállításaival kapcsolatos további információkért lásd: [Windows 10 és újabb beállítások az eszközök megfelelő vagy nem megfelelőként való megjelöléséhez](../protect/compliance-policy-create-windows.md). 

A következőkre vonatkozik:
- Windows 10 és újabb

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access-------4092920---"></a>Frissített felhasználói felület a Microsoft Exchange helyszíni hozzáférésének konfigurálásához    <!-- 4092920 -->  
Frissítettük a konzolt, ahol a [Microsoft Exchange helyszíni hozzáférését konfigurálja](../protect/conditional-access-exchange-create.md). A helyszíni Exchange-hozzáférés összes konfigurációja már elérhető a konzol ugyanazon paneljén, ahol *engedélyezheti a helyszíni Exchange-hozzáférés-vezérlést*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices----1109650----"></a>Alkalmazás-widgetek a kezdőképernyőn való hozzáadásának engedélyezése vagy korlátozása Android Enterprise Work profiling-eszközökön <!-- 1109650  --> 
Az Android Enterprise rendszerű eszközökön a munkahelyi profil szolgáltatásai konfigurálhatók (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **Android Enterprise** for platform > **munkahelyi profil > Az eszközre vonatkozó korlátozások** a profil típusa esetén). Ebben a frissítésben engedélyezheti a felhasználóknak, hogy a munkahelyi profil alkalmazásai által közzétett widgeteket adjanak az eszköz kezdőlapjára.

A konfigurálható beállítások megjelenítéséhez nyissa meg az [androidos vállalati eszköz beállításait, hogy engedélyezze vagy korlátozza a szolgáltatásokat az Intune használatával](../configuration/device-restrictions-android-for-work.md).

A következőkre vonatkozik:
- Androidos vállalati munkahelyi profil

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management----4869790-----"></a>Az új bérlők alapértelmezetten az Android-eszközök rendszergazdájának felügyeletével lesznek elérhetők <!-- 4869790   -->
Az Android rendszerű eszközök rendszergazdai képességeit az Android Enterprise váltja fel. Ezért javasoljuk, hogy az Android Enterprise új regisztrációkat használjon. Egy későbbi frissítés során az új bérlőknek a következő előfeltételeket kell végrehajtaniuk az Android-regisztrációban az eszköz rendszergazdai felügyeletének használatához: Nyissa meg az **Intune** > **eszközök beléptetése** > **Android-regisztráció** >  **A személyes és vállalati tulajdonban lévő eszközök, amelyek az eszköz felügyeleti jogosultságait** >  eszközzel**kezelhetik az eszközök rendszergazdáját**.

A meglévő bérlők semmilyen változást nem fognak tapasztalni a környezetében. 

További információ az Android-eszközök rendszergazdájáról az Intune-ban: [Android-eszközök rendszergazdai regisztrációja](https://docs.microsoft.com/intune/android-enroll-device-administrator).

#### <a name="list-of-dep-devices-associated-with-a-profile----5012045-idmiss---"></a>A profilhoz társított DEP-eszközök listája <!-- 5012045 idmiss -->
Most már megtekintheti a profilhoz társított Apple automatizált Készülékregisztrációs program (DEP) eszközök lapozható listáját. A listában bármelyik oldalról kereshet. A lista megjelenítéséhez nyissa meg az **Intune** > **eszközök beléptetése** > **Apple-regisztráció** > **beléptetési program jogkivonatok** elemet > Válassza ki a token > **Profiles** > válasszon egy profilt > **hozzárendelt eszközök** ( a **figyelő**alatt). 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Eszközkezelés

#### <a name="more-android-fully-managed-support----3464667-4631425-4631440-5227935-4062195-----"></a>További Android teljes körűen felügyelt támogatás <!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
Az Android teljes körűen felügyelt eszközeihez a következő támogatást adtuk hozzá:

- A teljes körűen felügyelt Android-tanúsítványok SCEP tanúsítványokat biztosítanak az eszköz tulajdonosként felügyelt eszközökön. A SCEP-tanúsítványok már támogatottak a munkahelyi profil eszközein.  Az SCEP-tanúsítványokkal a következőket teheti: <!-- 5227935 -->
    - SCEP-profil létrehozása az Android Enterprise DO szakaszban
    - SCEP-tanúsítványok csatolása Wi-Fi-profil hitelesítéshez
    - SCEP-tanúsítványok csatolása a VPN-profilokhoz hitelesítéshez
    - SCEP-tanúsítványok csatolása e-mail-profilokhoz a hitelesítéshez (AppConfig keresztül)
- A rendszeralkalmazások az Android Enterprise rendszerű eszközökön támogatottak. Az Intune-ban vegyen fel egy androidos nagyvállalati rendszeralkalmazást az **ügyfélalkalmazások** > **alkalmazások** > **Hozzáadás**elem kiválasztásával. Az **alkalmazás típusa** listában válassza az **Android Enterprise System app**elemet. További információ: [androidos nagyvállalati rendszeralkalmazások hozzáadása a Microsoft Intunehoz](../apps/apps-ae-system.md). <!-- 4062195 -->
- Az **eszköz megfelelősége** > **Android Enterprise** > **eszköz tulajdonosa**, létrehozhat egy megfelelőségi szabályzatot, amely beállítja a Google biztonság igazolási szintjét.   <!-- 4631425 -->
- Az Android Enterprise teljes körűen felügyelt eszközökön a Mobile Threat Defense-szolgáltatók támogatottak. Az **eszköz megfelelősége** > **Android Enterprise** > **eszköz tulajdonosa**, választhat egy elfogadható kockázati szintet. <!-- 4631440 --> Az [Android vállalati beállítások az eszközök megfelelő vagy nem megfelelőként való megjelölésére az Intune](../protect/compliance-policy-create-android-for-work.md#device-owner) -ban az aktuális beállítások szerepelnek.
- Az Android Enterprise teljes körűen felügyelt eszközökön a Microsoft Launcher alkalmazás mostantól az alkalmazás-konfigurációs szabályzatok segítségével konfigurálható, hogy lehetővé váljon a teljes körűen felügyelt eszközön a szabványosított végfelhasználói élmény. Az Android-eszköz személyre szabásához használhatja a Microsoft Launcher alkalmazást. Az alkalmazással Microsoft-fiók vagy munkahelyi/iskolai fiókkal is elérheti a naptárt, a dokumentumokat és a legutóbbi tevékenységeket a személyre szabott hírcsatornában. <!-- 5334044 -->

Ezzel a frissítéssel örömmel jelentjük be, hogy az Android Enterprise teljes körűen felügyelt Intune-támogatás már általánosan elérhető.

A következőkre vonatkozik:

- Android Enterprise teljes körűen felügyelt eszközök

#### <a name="send-custom-notifications-to-a-single-device-----4928910---"></a>Egyéni értesítések küldése egyetlen eszközre  <!-- 4928910 -->
Most már kijelölhet egyetlen eszközt, majd egy távoli eszköz művelettel [Egyéni értesítéseket küldhet csak erre az eszközre](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment----4950491---"></a>A törlés és a PIN-kód átállítása művelet nem érhető el a felhasználói regisztráció használatával beléptetett iOS-eszközökön <!-- 4950491 -->
A felhasználó beléptetése új típusú Apple-eszközök beléptetése. Ha felhasználói beléptetést használó eszközöket regisztrál, a törlés és a jelszó-visszaállítás távoli műveletei nem lesznek elérhetők az ilyen eszközökön.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices----4665317---"></a>Intune-támogatás iOS 13-és macOS-eszközökhöz <!-- 4665317 -->
Az Intune mostantól támogatja az iOS 13 és macOS Catalina eszközök felügyeletét. További információkért lásd az [iOS 13 és a iPadOS Microsoft Intune támogatását ismertető blogbejegyzést](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Eszköz biztonsága

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation-------3444125---"></a>BitLocker-támogatás az ügyfél által vezérelt helyreállítási jelszó elforgatásához   <!--  3444125 -->
Az Intune-Endpoint Protection beállítások segítségével konfigurálhatja az [ügyfél által vezérelt helyreállítási jelszavakat](../protect/endpoint-protection-windows-10.md#windows-encryption) a Bitlockerhez a Windows 1909-es vagy újabb verzióját futtató eszközökön.

Ez a beállítás egy, az operációsrendszer-meghajtó helyreállítása után (a Csizmadia vagy a WinRE használatával) és a helyreállítási jelszó zárolásának feloldása után kezdeményezi az ügyfél által vezérelt helyreállítási jelszó frissítését egy rögzített adatmeghajtón. Ez a beállítás frissíti a használt helyreállítási jelszót, és a köteten található egyéb nem használt jelszavak változatlanok maradnak. További információ: a BitLocker CSP dokumentációja a [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

#### <a name="tamper-protection-for-windows-defender-antivirus-----4705448----------"></a>Illetéktelen védelem a Windows Defender Víruskeresőben  <!-- 4705448        -->
Az Intune használatával kezelheti a Windows Defender víruskereső *illetéktelen hozzáférést biztosító védelmét* . Az [illetéktelen hozzáférést biztosító védelem beállítását](../protect/endpoint-protection-windows-10.md#windows-defender-security-center) a Microsoft Defender Security Center csoportjában találja, ha a Windows 10-es végpontok védelméhez eszköz-konfigurációs profilokat használ. Beállíthatja, hogy az illetéktelen hozzáférést *engedélyező* védelem bekapcsolja a Temper Protection-korlátozásokat, *Letiltva* a kikapcsolását, vagy beállíthatja, hogy a rendszer*ne* állítsa be az eszközök aktuális konfigurációját.  

További információ az illetéktelen hozzáférést biztosító védelemről: a [biztonsági beállítások módosításának megakadályozása](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) a Windows dokumentációjában. 

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available-----5317392---------"></a>Mostantól általánosan elérhető a Windows Defender-tűzfal speciális beállításai <!--  5317392       -->  
A [Windows Defender egyéni tűzfalszabályok az Endpoint Protection számára](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices), amelyet az eszköz konfigurációs profiljának részeként konfigurál, a szolgáltatás nem nyilvános előzetes verzióban érhető el, és általánosan elérhető (GA).  Ezekkel a szabályokkal megadhatja a bejövő és kimenő viselkedést az alkalmazásokhoz, a hálózati címekhez és a portokhoz. Ezek a szabályok júliusban lettek közzétéve nyilvános előzetes verzióként. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="scope-tags-now-support-terms-of-use-policies----2358863-idmiss---"></a>A hatókör-címkék mostantól támogatják a Használati szabályzatok használati feltételeit <!-- 2358863 idmiss -->
Mostantól hozzárendelheti a [hatókörhöz tartozó címkéket](scope-tags.md) a használati szabályzatokhoz. Ehhez nyissa meg az **Intune** > **eszközök beléptetése** > **használati** feltételeket > válasszon ki egy elemet a listában > **Tulajdonságok** > **hatókör címkék** > válasszon hatóköri címkét.

## <a name="week-of-september-9-2019"></a>2019. szeptember 9. hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="updates-to-microsoft-intune-app----4997846---"></a>Microsoft Intune alkalmazás frissítései <!-- 4997846 -->
Az Android rendszerhez készült Microsoft Intune alkalmazás a következő továbbfejlesztett funkciókkal bővült:
- Frissítve és javította az elrendezést, hogy a legfontosabb műveleteknél a legalsó szintű Navigálás szerepeljen.
- Hozzáadott egy további oldalt, amely megjeleníti a felhasználó profilját.
- Az alkalmazásban a felhasználó számára elérhető végrehajtható értesítések megjelenítése, például az eszköz beállításainak frissítése szükséges.
- Az egyéni leküldéses értesítések megjelenítése, az alkalmazás igazítása az iOS és Android rendszerhez készült Céges portál alkalmazásban nemrégiben hozzáadott támogatással. További információt [az egyéni értesítések küldése az Intune-ban](../remote-actions/custom-notifications.md)című témakörben talál.

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993---"></a>IOS-eszközök esetén szabja testre a beléptetési folyamat adatvédelmi képernyőjét a Céges portál <!-- 4394993 -->
A Markdown segítségével testre szabhatja a Céges portál adatvédelmi képernyőjét, amelyet a végfelhasználók az iOS-regisztráció során látnak. Pontosabban testreszabhatja azon dolgok listáját, amelyeket a szervezete nem lát vagy tesz az eszközön. További információ: [a Intune céges portál alkalmazás konfigurálása](../apps/company-portal-app.md#privacy-statement-customization).


## <a name="week-of-september-2-2019"></a>2019. szeptember 2. hét

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="intune-user-interface-update--tenant-status-dashboard-----5273210----"></a>Intune felhasználói felület frissítése – bérlői állapot irányítópultja  <!-- 5273210  -->
A bérlői állapot irányítópultjának felhasználói felülete frissítve lett az Azure felhasználói felületi stílusokkal való összehangoláshoz. További információ: [bérlői állapot](../tenant-status.md).


## <a name="week-of-august-26-2019"></a>2019. augusztus 26. hét

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer----5228061---"></a>A Microsoft Edge-beállítások konfigurálása a Windows 10 és újabb rendszerhez készült felügyeleti sablonok használatával <!-- 5228061 -->

Windows 10 és újabb rendszerű eszközökön felügyeleti sablonokat hozhat létre az Intune csoportházirend-beállításainak konfigurálásához. Ebben a frissítésben olyan beállításokat adhat meg, amelyek a Microsoft Edge 77-es vagy újabb verziójára vonatkoznak.

A felügyeleti sablonokkal kapcsolatos további információkért lásd: [Windows 10 sablonok használata a csoportházirend-beállítások konfigurálásához az Intune-ban](../configuration/administrative-templates-windows.md).

A következőkre vonatkozik:

- Windows 10 és újabb (Windows RS4 +)

## <a name="week-of-august-12-2019"></a>2019. augusztus 12-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144-----"></a>IOS-alkalmazások eltávolítási viselkedésének szabályozása az eszköz regisztrációjának törlése során <!-- 3504144   -->
A rendszergazdák kezelhetik, hogy egy alkalmazás el lett-e távolítva vagy meg van-e őrizni az eszközön, ha az eszköz regisztrálva van a felhasználó vagy az eszköz csoport szintjén. 

#### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Üzleti alkalmazások kategorizálása Microsoft Store <!-- 3926922 -->
A vállalati alkalmazások Microsoft Store kategorizálható. Ehhez válassza az **Intune** > **ügyfélalkalmazások** > **alkalmazások** > válasszon egy Microsoft Store for Business app > **alkalmazás adatai** > **kategóriában**. A legördülő menüben rendeljen hozzá egy kategóriát.

#### <a name="customized-notifications-for-microsoft-intune-app-users----4843354----"></a>Testreszabott értesítések Microsoft Intune alkalmazás felhasználói számára <!-- 4843354  -->
Az Androidhoz készült Microsoft Intune alkalmazás mostantól támogatja az egyéni leküldéses értesítések megjelenítését, valamint az iOS és Android rendszerhez készült Céges portál alkalmazásokban nemrégiben hozzáadott támogatással való összehangolását. További információt [az egyéni értesítések küldése az Intune-ban](../remote-actions/custom-notifications.md)című témakörben talál.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946-----"></a>Új funkciók androidos vállalati dedikált eszközökhöz többalkalmazásos módban <!-- 3755304 3041943 3041946   -->

Az Intune-ban a funkciók és beállítások az androidos vállalati dedikált eszközökön a kioszk stílusú felületén vezérelhetők (az**eszköz konfigurációja** > **profilok** > **create Profile** > **Android Enterprise** for platform > **csak az eszköz tulajdonosa, eszköz korlátozásai** a profil típusa esetén).

Ebben a frissítésben a következő szolgáltatások lesznek hozzáadva:

- **Dedikált eszközök** > **többalkalmazásos**: a **virtuális Kezdőlap gomb** megnyomásával megjeleníthető az eszközön, vagy a képernyőn lebegve, hogy a felhasználók áthelyezhetik azt.
- **Dedikált eszközök** **többalkalmazásos** > : a **zseblámpa-hozzáférés** lehetővé teszi a felhasználók számára a zseblámpa használatát. 
- **Dedikált eszközök**  > **multi-app**: a **Media Volume Control** lehetővé teszi a felhasználóknak, hogy az eszköz adathordozó-kötetét egy csúszka használatával szabályozzák. 
- **Dedikált eszközök**  > **többalkalmazásos**: **képernyővédő engedélyezése**, egyéni rendszerkép feltöltése és a képernyővédő megjelenítésének vezérlése.

Az aktuális beállítások megtekintéséhez lépjen az [Android Enterprise Device Settings elemre az Intune-t használó funkciók engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

A következőkre vonatkozik:

- Androidos vállalati dedikált eszközök

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215-3574238-3574235-3574232-----"></a>Új alkalmazás-és konfigurációs profilok Android Enterprise teljes körűen felügyelt eszközökhöz <!-- 3574215 3574238 3574235 3574232   -->
A profilok használatával olyan beállításokat konfigurálhat, amelyek a VPN-, e-mail-és Wi-Fi-beállításokat alkalmazzák az androidos vállalati eszköz tulajdonos (teljes mértékben felügyelt) eszközeire. Ebben a frissítésben a következőket teheti:

- Alkalmazás- [konfigurációs szabályzatok](../apps/app-configuration-policies-use-android.md) használatával telepítheti az Outlook, a Gmail és a Nine Work e-mail-beállításait.
- A [megbízható főtanúsítványok beállításainak](../protect/certificates-configure.md)üzembe helyezéséhez használjon eszköz-konfigurációs profilokat.
- A VPN-és [Wi-Fi-](../configuration/wi-fi-settings-android-enterprise.md) beállítások üzembe helyezéséhez használjon eszköz [-](../configuration/vpn-settings-android-enterprise.md) konfigurációs profilokat.

> [!IMPORTANT]
> Ezzel a funkcióval a felhasználók a VPN-, Wi-Fi-és e-mail-profilokhoz tartozó felhasználónevével és jelszavával hitelesítik magukat. A tanúsítvány alapú hitelesítés jelenleg nem érhető el.

A következőkre vonatkozik:  
- Androidos vállalati eszköz tulajdonosa (teljes mértékben felügyelt)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices---3914202-----"></a>A macOS-eszközökre való bejelentkezéskor megnyíló alkalmazások, fájlok, dokumentumok és mappák szabályozása <!--3914202   -->
A macOS-eszközök funkcióit engedélyezheti és konfigurálhatja (az**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **MacOS** a platform > **eszköz funkciói** a profil típusa esetén). 

Ebben a frissítésben új bejelentkezési elemek beállításával szabályozhatja, hogy mely alkalmazások, fájlok, dokumentumok és mappák nyílnak meg, amikor a felhasználó bejelentkezik a regisztrált eszközre. 

Az aktuális beállítások megtekintéséhez válassza a [MacOS-eszköz szolgáltatás beállításai az Intune-ban](../configuration/macos-device-features-settings.md)lehetőséget.

A következőkre vonatkozik:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings------4464404----------"></a>A határidők lecserélik a Windows Update gyűrűk lefoglalt újraindítási beállításait   <!-- 4464404        -->
A legutóbbi Windows- [karbantartási változások](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing)összehangolásához az Intune Windows 10-es frissítési gyűrűk mostantól [támogatják a határidők beállításait](../protect/windows-update-settings.md). A *határidők* határozzák meg, hogy egy eszköz Mikor telepítse a szolgáltatást és a biztonsági frissítéseket.  A Windows 10 1903-es vagy újabb verzióját futtató eszközökön a *határidők* felülírják a *felvállalt újraindítási*konfigurációkat.  A jövőben a *határidők* felülírják a Windows 10 korábbi verzióiban a megjelenő *újraindítást* is.  

Ha nem konfigurálja a *határidőket*, az eszközök továbbra is használják a kapcsolódó *Újraindítási* beállításokat, azonban az Intune a későbbi frissítésekben nem fogja támogatni a felvállalt újraindítási beállítások támogatását.  

Tervezze meg a *határidők* használatát a Windows 10-es eszközökön. A *határidők* beállításainak megadása után módosíthatja az Intune-konfigurációkat, hogy a rendszer ne konfigurálja a folyamatban lévő *újraindítást* . Ha a nincs konfigurálva értékre van állítva, az Intune leállítja a beállítások kezelését az eszközökön, de nem távolítja el a beállítás utolsó konfigurációját az eszközről. Ezért a *felvállalt újraindításhoz* beállított utolsó konfigurációk aktív állapotban maradnak, és csak az Intune-tól eltérő módon módosítják ezeket a beállításokat. Később, amikor az eszközök Windows-verziója megváltozik, vagy ha a *határidőkhöz* tartozó Intune-támogatás a Windows rendszerű eszközökre bővül, az eszköz a már meglévő új beállításokat fogja használni.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors--------4704642--------"></a>Több Microsoft Intune tanúsítvány-összekötő támogatása   <!--   4704642      -->
Az Intune mostantól támogatja több Microsoft Intune tanúsítvány-összekötő telepítését és használatát [a PKCS-műveletekhez](../protect/certficates-pfx-configure.md). Ez a változás támogatja a terheléselosztást és az összekötő magas rendelkezésre állását. Minden összekötő-példány feldolgozhatja a tanúsítványkérelmek az Intune-ból.  Ha az egyik összekötő nem érhető el, a többi összekötő továbbra is feldolgozza a kérelmeket. 

Több összekötő használatához nincs szükség az összekötő szoftver legújabb verziójára való frissítésre.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709-----"></a>Új beállítások és meglévő beállítások módosítása az iOS-és macOS-eszközök funkcióinak korlátozásához <!-- 4867699 4867709   -->
Létrehozhat profilokat az iOS és macOS rendszerű eszközök beállításainak korlátozásához (**Device configuration** > **profilok** > **profil létrehozása** > **iOS** vagy **MacOS** platform típusú > **eszközhöz korlátozások**). Ez a frissítés a következő funkciókat tartalmazza:

- **Macos** > **eszköz korlátozásai** > **felhő és tárterület**esetében az új **handoff** beállítással letilthatja a felhasználók számára a munkát egy MacOS-eszközön, és folytathatja a munkát egy másik MacOS vagy iOS rendszerű eszközön.

  Ha szeretné megtekinteni az aktuális beállításokat, lépjen a [MacOS eszközbeállítások lehetőségre, hogy engedélyezze vagy korlátozza a szolgáltatásokat az Intune használatával](../configuration/device-restrictions-macos.md).

- Az **iOS** > **eszköz korlátozásai**esetében néhány változás van:

  - **Beépített alkalmazások**  > **Keresés az iPhone-ban (csak felügyelt eszköz esetén)** : új beállítás, amely letiltja ezt a funkciót a Find My app szolgáltatásban. 
  - **Beépített alkalmazások**  >  a**barátok megkeresése (csak felügyelt eszköz esetén)** : új beállítás, amely letiltja ezt a funkciót a Find My app szolgáltatásban. 
  - Wi-Fi állapot **vezeték nélküli**  > **módosítása (csak felügyelt eszköz esetén)** : új beállítás, amely megakadályozza, hogy a felhasználók bekapcsolják vagy kikapcsolják a Wi-Fi-t az eszközön.
  - **Billentyűzet és szótár** > **QuickPath (csak felügyelt eszköz esetén)** : új beállítás, amely letiltja a QuickPath funkciót.
  - **Felhő és tárolás**: a **tevékenység folytatását** a rendszer átnevezi a **handoff**.

  Az aktuális beállítások megjelenítéséhez nyissa meg az [IOS-eszköz beállításait, és engedélyezze vagy korlátozza a szolgáltatásokat az Intune használatával](../configuration/device-restrictions-ios.md).

A következőkre vonatkozik:  
- macOS 10,15 és újabb verziók
- iOS 13 és újabb verziók

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809-----"></a>Néhány nem felügyelt iOS-eszközre vonatkozó korlátozás csak az iOS 13,0-es kiadással lesz felügyelve <!-- 4867809   -->
Ebben a frissítésben egyes beállítások csak a felügyelt eszközökre vonatkoznak az iOS 13,0 kiadással. Ha ezek a beállítások az iOS 13,0-es kiadás előtt konfigurálhatók és nem felügyelt eszközökhöz vannak hozzárendelve, a rendszer továbbra is alkalmazza a beállításokat a nem felügyelt eszközökre. Az eszközök az iOS 13,0-re való frissítés után is érvényben maradnak. Ezek a korlátozások el lesznek távolítva a nem felügyelt eszközökön, amelyek biztonsági mentése és visszaállítása megtörtént. 

Ezek a beállítások a következők:

- Alkalmazás-áruház, dokumentumok megtekintése, játékok
  - Alkalmazás-áruház
  - Explicit iTunes, zene, podcast vagy Hírek tartalma
  - Game Center ismerősök hozzáadása
  - Többrésztvevős játékok
- Beépített alkalmazások
  - Fényképezőgép
    - FaceTime
  - Safari
    - Autofill
- Felhő és tárolás
  - Biztonsági mentés az iCloudba
  - ICloud-dokumentumok szinkronizálásának letiltása
  - ICloud-kulcstartó szinkronizálásának letiltása

Az aktuális beállítások megjelenítéséhez nyissa meg az [IOS-eszköz beállításait, és engedélyezze vagy korlátozza a szolgáltatásokat az Intune használatával](../configuration/device-restrictions-ios.md).

A következőkre vonatkozik:  
- iOS 13,0 és újabb verziók

#### <a name="improved-device-status-for-macos-filevault-encryption-----4944983-----------"></a>Továbbfejlesztett eszköz állapota macOS FileVault titkosításhoz  <!-- 4944983         -->
A macOS rendszerű eszközökön a FileVault titkosításhoz több [eszköz állapotüzenetek](../protect/encryption-monitor.md#device-encryption-status) is frissültek.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status----5119229---"></a>A jelentések egyes Windows Defender víruskereső-keresési beállításai sikertelen állapotot mutatnak <!-- 5119229 -->
Az Intune-ban házirendeket hozhat létre a Windows Defender víruskereső használatával a Windows 10 rendszerű eszközök vizsgálatához (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **Windows 10 és újabb** platformokra >A profil típusa > a **Windows Defender víruskereső**eszközre vonatkozó korlátozások. A jelentéskészítés elvégzéséhez szükséges **napi gyors vizsgálat** és **rendszervizsgálati** idő a sikertelen állapotot jelzi, ha valójában sikeres állapotot jelent. 

Ebben a frissítésben ez a viselkedés kijavítva van. Így a **napi gyors vizsgálat** és a **rendszervizsgálatok elvégzéséhez szükséges** idő a sikeres ellenőrzések sikerességi állapotát jeleníti meg, és sikertelen állapotot jelez, ha a beállítások nem lesznek alkalmazva. 

A Windows Defender víruskereső beállításaival kapcsolatos további információkért lásd: [Windows 10 (és újabb) eszközbeállítások, amelyekkel engedélyezheti vagy korlátozhatja a szolgáltatásokat az Intune használatával](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus). 

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="default-scope-tags----3702875----"></a>Alapértelmezett hatókör-Címkék <!-- 3702875  -->
Mostantól elérhető egy új beépített alapértelmezett hatóköri címke. A hatóköri címkéket támogató összes nem címkézett Intune-objektum automatikusan hozzá lesz rendelve az alapértelmezett hatókör-címkéhez. Az **alapértelmezett** hatókör címkét a rendszer hozzáadja az összes meglévő szerepkör-hozzárendeléshez a paritásnak a rendszergazdai felülettel való fenntartásához. Ha nem szeretné, hogy a rendszergazda az alapértelmezett hatókör címkével lássa el az Intune-objektumokat, távolítsa el az alapértelmezett hatóköri címkét a szerepkör-hozzárendelésből. Ez a funkció hasonló a System Center Configuration Manager biztonsági hatókörök szolgáltatásához. További információ: a [RBAC és a hatókör-címkék használata a terjesztéshez](scope-tags.md).

#### <a name="android-enrollment-device-administrator-support----4869749-----"></a>Android beléptetési eszköz rendszergazdai támogatása <!-- 4869749   -->
Az Android-eszköz rendszergazdai beléptetési lehetősége hozzá lett adva az Android-eszközök regisztrálási lapjához (**Intune** > **eszközök beléptetése** > **Android-regisztráció**). Az Android-eszközök rendszergazdája alapértelmezés szerint továbbra is engedélyezve lesz az összes bérlő esetében.  További információ: Android- [eszközök rendszergazdai regisztrációja](../enrollment/android-enroll-device-administrator.md).

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>További képernyők kihagyása a beállítási Asszisztensben <!--4877451  -->
Készülékregisztrációs program profilokat is beállíthat, hogy kihagyja a következő beállítási asszisztens képernyőket:
- iOS rendszerhez
    - Megjelenését
    - Expressz nyelv
    - Előnyben részesített nyelv
    - Eszközről az eszközre való Migrálás
- MacOS esetén
    - Képernyő időpontja
    - Touch ID beállítása

A beállítási asszisztens testreszabásával kapcsolatos további információkért lásd: [Apple beléptetési profil létrehozása iOS rendszerhez](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) és [Apple regisztrációs profil létrehozása MacOS rendszerhez ](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile).

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process----3823054---"></a>Felhasználói oszlop hozzáadása az Autopilot-eszköz CSV-feltöltési folyamatához <!-- 3823054 -->
Mostantól hozzáadhat egy felhasználói oszlopot az Autopilot-eszközökhöz tartozó CSV-feltöltéshez. Ez lehetővé teszi a felhasználók tömeges hozzárendelését a CSV importálásakor. További információ: [Windows-eszközök regisztrálása az Intune-ban a Windows Autopilot használatával](../enrollment/enrollment-autopilot.md).


### <a name="device-management"></a>Eszközkezelés

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Az eszköz automatikus törlési időkorlátjának beállítása 30 nap alatt <!--4231059  -->
Megadhatja az automatikus eszköz tisztítási időkorlátját, amely az utolsó bejelentkezés után 30 nap (az előző korlát helyett a 90 nap). Ehhez nyissa meg az **Intune** > **eszközt** > **telepítő** > **eszköz tisztítási szabályok**.

#### <a name="build-number-included-on-android-device-hardware-page----4461910-----"></a>Az Android-eszköz hardveres oldalán található szám összeállítása <!-- 4461910   -->
Minden Android-eszköz hardver lapján megjelenik egy új bejegyzés, amely tartalmazza az eszköz operációs rendszerének Build-számát. További információ: [az eszköz adatainak megtekintése az Intune-ban](../remote-actions/device-inventory.md).


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>Hét augusztus 5-ig, 2019

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices-----4843713---"></a>A zebra Technologies egy támogatott OEM OEMConfig az androidos vállalati eszközökön  <!-- 4843713 -->

Az Intune-ban létrehozhat eszköz-konfigurációs profilokat, és beállításokat alkalmazhat az androidos vállalati eszközökre a OEMConfig használatával (**eszköz konfigurációja** > **profilok** > **create Profile** > **Android Enterprise** a platform > **OEMConfig** esetében).

Ebben a frissítésben a zebra Technologies a OEMConfig által támogatott eredeti berendezésgyártó (OEM). További információ a OEMConfig-ről: [androidos vállalati eszközök használata és kezelése a OEMConfig](../configuration/android-oem-configuration-overview.md)-mel.

A következőkre vonatkozik:  
- Android Enterprise

<!-- ########################## -->

## <a name="week-of-july-22-2019"></a>2019. július 22-i hét 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="customized-notifications-for-users-and-groups-------16766574------------"></a>Felhasználók és csoportok testreszabott értesítései    <!-- 16766574          -->
Egyéni leküldéses értesítések küldése a Céges portál alkalmazásból az Intune-nal felügyelt iOS-és Android-eszközökön lévő felhasználóknak. Ezek a mobil leküldéses értesítések nagyon testreszabhatók ingyenes szöveggel, és bármilyen célra használhatók. A szervezet különböző felhasználói csoportjaira is megcélozhatja őket. További információ: [Egyéni értesítések](../remote-actions/custom-notifications.md).

#### <a name="googles-device-policy-controller-app----3041950----"></a>A Google eszköz házirend-vezérlő alkalmazás <!-- 3041950  -->
A felügyelt kezdőképernyő alkalmazás mostantól hozzáférést biztosít a Google androidos eszköz házirend-alkalmazásához. A felügyelt kezdőképernyő alkalmazás egy egyéni indító, amelyet az Intune-ban regisztrált eszközökhöz az Android Enterprise (AE) dedikált eszközként használnak többalkalmazásos kioszk mód használatával. Elérheti az Android-eszköz házirend-alkalmazását, vagy megtekintheti a felhasználókat az Android-eszközök házirend-alkalmazásához, támogatási és hibakeresési célból. Ez az indítási képesség akkor érhető el, amikor az eszköz regisztrálja és zárolja a felügyelt kezdőképernyőn. A funkció használatához nincs szükség további telepítésekre.

#### <a name="outlook-protection-settings-for-ios-and-android-devices----3212619---"></a>Az Outlook védelmi beállításai iOS és Android rendszerű eszközökhöz <!-- 3212619 -->
Mostantól az iOS és az Android rendszerhez készült általános alkalmazások és adatvédelem konfigurációs beállításait is konfigurálhatja az egyszerű Intune rendszergazdai vezérlőkkel az eszközök regisztrálása nélkül. Az alkalmazás általános beállításainak megadása a rendszergazdák számára lehetővé teszi, hogy az Outlookot az iOS és az Android rendszerhez a regisztrált eszközökön is kezelhesse. Az Outlook-beállításokkal kapcsolatos további információkért lásd: [az Outlook telepítése iOS-és Android-alkalmazásokhoz konfigurációs beállítások](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready---idstaged---"></a>Az "alkalmazhatósági szabályok" használata Windows 10-es eszközök konfigurációs profiljainak létrehozásakor <!-- 2549910 eeready   idstaged -->

Windows 10-es eszköz konfigurációs profilokat hoz létre (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **Windows 10** platformra > **alkalmazhatósági szabályok**). Ebben a frissítésben létrehozhat egy **alkalmazhatósági szabályt** , hogy a profil csak egy adott kiadásra vagy adott verzióra vonatkozzon. Létrehozhat például egy olyan profilt, amely lehetővé teszi egyes BitLocker-beállítások használatát. A profil hozzáadása után alkalmazzon egy alkalmazhatósági szabályt, hogy a profil csak a Windows 10 Enterprise rendszert futtató eszközökre vonatkozzon.

Alkalmazhatósági szabály hozzáadásához lásd: [alkalmazhatósági szabályok](../configuration/device-profile-create.md#applicability-rules).

A Windows 10 és újabb verziókra vonatkozik

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices----3330008----"></a>A jogkivonatok használata az eszközre jellemző információk hozzáadásához az egyéni profilokban iOS-és macOS-eszközökhöz <!-- 3330008  -->
Az Intune-ban nem beépített beállítások és szolgáltatások konfigurálásához egyéni profilokat használhat iOS-és macOS-eszközökön (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **iOS** vagy **MacOS** a platformhoz > **Egyéni** a profil típusa). Ebben a frissítésben tokeneket adhat hozzá a `.mobileconfig` fájlhoz az eszközre vonatkozó információk hozzáadásához. Például hozzáadhat `Serial Number: {{serialnumber}}` értéket a konfigurációs fájlhoz az eszköz sorozatszámának megjelenítéséhez.

Egyéni profil létrehozásához tekintse meg az [Egyéni iOS-beállítások](../configuration/custom-settings-ios.md) vagy a MacOS-es [Egyéni beállítások](../configuration/custom-settings-macos.md)című témakört.

A következőkre vonatkozik:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769-----"></a>Új Configuration Designer az Android Enterprise-hoz készült OEMConfig-profil létrehozásakor <!-- 3712769   -->
Az Intune-ban létrehozhat egy OEMConfig-alkalmazást használó eszköz-konfigurációs profilt (az eszköz konfigurációjának > profiljait, > profilt hozhat létre > Android Enterprise platformon > OEMConfig). Ha ezt teszi, a rendszer egy JSON-szerkesztőt nyit meg a sablon és az értékek módosításával. 

Ez a frissítés egy továbbfejlesztett felhasználói élményt biztosító konfigurációs tervezőt tartalmaz, amely az alkalmazásban beágyazott részleteket jeleníti meg, beleértve a címeket, a leírásokat és egyebeket. A JSON-szerkesztő továbbra is elérhető, és a Configuration Designerben végrehajtott módosításokat jeleníti meg.

Az aktuális beállítások megtekintéséhez válassza az [androidos vállalati eszközök használata és kezelése a OEMConfig](../configuration/android-oem-configuration-overview.md)-mel című témakört.

A következőkre vonatkozik: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello-----4089576--------------"></a>Frissített felhasználói felület a Windows Hello konfigurálásához  <!-- 4089576            -->
Frissítettük a konzolt, amelyben az [Intune-t a vállalati Windows Hello használatára konfigurálja](../protect/windows-hello.md). A konfigurációs beállítások mostantól a konzol ugyanazon paneljén érhetők el, ahol engedélyezheti a Windows Hello használatát. 


#### <a name="intune-powershell-sdk----4924113---"></a>Intune PowerShell SDK <!-- 4924113 --> 
Az Intune PowerShell SDK, amely a Microsoft Graphon keresztül támogatja az Intune API-t, a 6.1907.1.0 verzióra frissült. Az SDK mostantól a következőket támogatja:
- Együttműködik Azure Automationokkal.
- A csak az alkalmazásra vonatkozó hitelesítési olvasási műveleteket támogatja. 
- Támogatja a rövid rövidített neveket aliasként.
- Megfelel a PowerShell elnevezési konvencióinak. Pontosabban a `PSCredential` paramétert (az `Connect-MSGraph` parancsmagon) átnevezték a következőre: `Credential`.
- A a `Invoke-MSGraphRequest` parancsmag használata esetén a `Content-Type` fejléc értékének manuális megadását támogatja.

További információ: [POWERSHELL SDK Microsoft Intune Graph API](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="updates-for-enrollment-restrictions-----2871968---"></a>Regisztrációs korlátozások frissítései  <!-- 2871968 -->
Az új bérlők regisztrálási korlátozásai frissültek, így az androidos vállalati munkahelyi profilok alapértelmezés szerint engedélyezve vannak. A meglévő bérlők semmilyen változást nem fognak tapasztalni. Az androidos vállalati munkahelyi profilok használatához továbbra is [össze kell kapcsolnia Intune-fiókját a felügyelt Google Play-fiókkal](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions---4089575-4089579----"></a>Felhasználói felületi frissítések az Apple-regisztrációhoz és a regisztrációs korlátozásokhoz <!--4089575, 4089579  -->
A következő folyamatok mindegyike egy varázsló stílusú felhasználói felületet használ:
- Apple-eszközök beléptetése. További információ: iOS- [eszközök automatikus regisztrálása az Apple Készülékregisztrációs program](../enrollment/device-enrollment-program-enroll-ios.md).
- Regisztráció korlátozásának létrehozása. További információkért lásd a [regisztrációs korlátozások beállítása](../enrollment/enrollment-restrictions-set.md)című témakört.

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices----4711509--idmiss---"></a>A vállalati eszközök azonosítóinak előzetes konfigurációjának kezeléséhez Android Q-eszközökhöz <!-- 4711509  idmiss -->
Az Android Q (v10)-ben a Google eltávolítja a MDM-ügynököket a örökölt felügyelt (eszköz-rendszergazda) Android-eszközökön az eszköz-azonosító információk összegyűjtéséhez.  Az Intune olyan funkcióval rendelkezik, amely lehetővé teszi a rendszergazdák számára, hogy [előre konfigurálják az eszközök sorozatszámait vagy IMEI-listáját](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) , hogy automatikusan címkével lássa el ezeket az eszközöket a vállalat tulajdonában. Ez a funkció nem működik az eszköz rendszergazdája által felügyelt Android Q-eszközökön.  Függetlenül attól, hogy az eszköz sorozatszáma vagy IMEI-je fel van-e töltve, a rendszer mindig személyesnek tekinti az Intune-regisztráció során.  A regisztráció után manuálisan is átválthatja a vállalati tulajdont.  Ez csak az új regisztrációkat érinti, és a meglévő regisztrált eszközöket nem érinti.  A munkahelyi profillal felügyelt Android-eszközöket ez a változás nem érinti, és továbbra is működik, ahogy ma.  Emellett az eszköz-rendszergazdaként regisztrált Android Q-eszközök nem tudnak a sorozatszámot vagy IMEI-t jelenteni az Intune-konzolon az eszköz tulajdonságaiként.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices----4977730---"></a>Az androidos vállalati regisztrációk (munkahelyi profil, dedikált eszközök és teljes körűen felügyelt eszközök) ikonjai módosultak. <!-- 4977730 -->
Az Android Enterprise beléptetési profilok ikonjai módosultak. Az új ikonok megjelenítéséhez nyissa meg az **Intune** > **Beléptetés** > **Android-regisztráció** > a **beléptetési profilok**területen.


#### <a name="windows-diagnostic-data-collection-change----4113859---"></a>Windows diagnosztikai adatgyűjtés módosítása <!-- 4113859 -->
A diagnosztikai adatgyűjtés alapértelmezett értéke megváltozott a Windows 10 1903-es vagy újabb verzióját futtató eszközökön. A Windows 10 1903-től kezdődően a diagnosztikai adatgyűjtés alapértelmezés szerint engedélyezve van. A Windows diagnosztikai adatok fontos műszaki adatok a Windows-eszközökről az eszközről, valamint a Windows és a kapcsolódó szoftverek működésének módjáról. További információ: [Windows diagnosztikai adatok konfigurálása a szervezetben](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization). Az Autopilot-eszközök is a "teljes" telemetria vannak kiválasztva, kivéve, ha az Autopilot-profilban nincs más beállítva a [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry).

### <a name="device-management"></a>Eszközkezelés

#### <a name="improve-device-location---3855417----"></a>Az eszköz helyének javítása<!-- 3855417  -->
Az eszköz **megkeresése** művelettel nagyíthatja az eszköz pontos koordinátáit. Az elveszett iOS-eszközök megkeresésével kapcsolatos további információkért lásd: [elveszett iOS-eszközök megkeresése](../remote-actions/device-locate.md).


### <a name="device-security"></a>Eszköz biztonsága

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview------1311949-------"></a>Speciális beállítások a Windows Defender-tűzfalhoz (nyilvános előzetes verzió)  <!--  1311949     -->  
Az Intune használatával kezelheti az egyéni tűzfalszabályok az Endpoint Protection [eszköz konfigurációs profiljának részeként](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) a Windows 10 rendszerben. A szabályok megadhatják a bejövő és kimenő viselkedést az alkalmazásokhoz, a hálózati címekhez és a portokhoz. 

#### <a name="updated-ui-for-managing-security-baselines------4091125-------"></a>Frissített felhasználói felület a biztonsági alapkonfigurációk kezeléséhez   <!-- 4091125     -->
A biztonsági alaptervek [létrehozásához és szerkesztéséhez](../protect/security-baselines.md#create-the-profile) az Intune-konzolon frissítettük az élményt. A módosítások a következők:

Egyszerűbb varázsló-stílusú formátum, amely egyetlen panelre van tömörítve. egy panelen belül. Ez az új kialakítás a panel terjeszkedésével foglalkozik, amely megköveteli, hogy az informatikai szakemberek több különálló ablaktáblán is megvizsgálják a részletezést.  
Mostantól a létrehozási és szerkesztési élmény részeként is létrehozhat hozzárendeléseket, ahelyett, hogy később vissza kellene térnie az alaptervek hozzárendeléséhez. Az új alapkonfiguráció létrehozása előtt megtekintheti a beállítások összegzését, és egy meglévőt is szerkeszthet. A szerkesztéskor az összefoglalás csak a szerkesztett tulajdonságok egy kategóriájában beállított elemek listáját jeleníti meg.



<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>2019. július 15-i hét 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="managed-home-screen-and-managed-settings-icons----4918107---"></a>Felügyelt kezdőképernyő és felügyelt beállítások ikonjai <!-- 4918107 -->
Frissült a felügyelt kezdőképernyő alkalmazás ikonja és a **felügyelt beállítások** ikon. A felügyelt kezdőképernyő alkalmazást csak az Intune-ban regisztrált eszközök használják az Android Enterprise (AE) dedikált eszközként, és több alkalmazásból álló kioszk módban futnak. A felügyelt kezdőképernyő alkalmazással kapcsolatos további információkért lásd: [az Android Enterprise rendszerhez készült Microsoft Managed Home Screen alkalmazás konfigurálása](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices----4918136---"></a>Androidos eszközök házirendje androidos vállalati dedikált eszközökön <!-- 4918136 -->
Az Android-eszközök házirendje alkalmazást a felügyelt kezdőképernyő alkalmazás hibakeresési képernyőjéről érheti el. A felügyelt kezdőképernyő alkalmazást csak az Intune-ban regisztrált eszközök használják az Android Enterprise (AE) dedikált eszközként, és több alkalmazásból álló kioszk módban futnak. További információ: [az Android Enterprise rendszerhez készült Microsoft Managed Home Screen alkalmazás konfigurálása](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates----3902931---"></a>iOS-Céges portál frissítései <!-- 3902931 -->
Az iOS app Management-kérések vállalatának neve lecseréli az aktuális "i.manage.microsoft.com" szöveget. A felhasználók például a "i.manage.microsoft.com" helyett a cég nevét fogják látni, ha a felhasználók iOS-alkalmazást próbálnak telepíteni a Céges portálról, vagy amikor a felhasználók engedélyezik az alkalmazás felügyeletét. Ezt a rendszer a következő néhány nap során minden ügyfélnek bevezeti.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="manage-filevault-for-macos-------3858502--4557986--1210104----"></a>FileVault kezelése macOS rendszerhez   <!--  3858502 + 4557986 + 1210104  -->
Az Intune segítségével [kezelheti a MacOS-eszközök FileVault-titkosítását](../protect/encrypt-devices.md). Az eszközök titkosításához az Endpoint Protection-eszköz konfigurációs profilját kell használnia.

A FileVault-támogatás magában foglalja a titkosítatlan eszközök titkosítását, az eszközök személyes helyreállítási kulcsának letétjét, a személyes titkosítási kulcsok automatikus vagy manuális elforgatását, valamint a vállalati eszközök legfontosabb lekérését. A végfelhasználók a Céges portál webhelyet is használhatják a titkosított eszközök személyes helyreállítási kulcsának beszerzéséhez. 

Kibővítettük a titkosítási jelentést is, hogy a BitLocker melletti [FileVault kapcsolatos információk](../protect/encryption-monitor.md) is szerepeljenek, így egyetlen helyen tekintheti meg az összes eszköz titkosítási részleteit. 

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user----4156123---"></a>A Windows Autopilot alaphelyzetbe állítása eltávolítja az eszköz elsődleges felhasználóját <!-- 4156123 -->
Ha az Autopilot alaphelyzetbe állítását egy eszközön használja, az eszköz elsődleges felhasználója el lesz távolítva. A következő felhasználó, aki az Alaphelyzetbe állítás után bejelentkezik, elsődleges felhasználóként lesz beállítva. A szolgáltatás a következő néhány nap során minden ügyfelünk számára elérhetővé válik.

## <a name="week-of-july-8-2019"></a>2019. július 8. hét

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Új Office-, Windows-és OneDrive-beállítások a Windows 10 felügyeleti sablonokban <!-- 3510695 -->

Az Intune-ban létrehozhat olyan felügyeleti sablonokat, amelyek a helyszíni csoportházirend-kezelést utánozzák (**eszközkezelés** > **profilok** > **profil létrehozása** > **Windows 10 és újabb verziók** a platformhoz >A profil típusához tartozó felügyeleti sablon).

Ez a frissítés több Office-, Windows-és OneDrive-beállítást is tartalmaz, amelyeket hozzáadhat a sablonokhoz. Ezekkel az új beállításokkal mostantól konfigurálhatja a 2500-es, 100%-os beállításokat.

A szolgáltatással kapcsolatos további tudnivalókért tekintse meg a csoportházirend [-beállítások konfigurálása az Intune-ban című témakört a Windows 10-es sablonok használatával](../configuration/administrative-templates-windows.md).

A Windows 10 és újabb verziókra vonatkozik

## <a name="week-of-july-1-2019"></a>2019. július 1. hét 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="aad-and-app-on-android-enterprise-devices----3574267---"></a>HRE és alkalmazás androidos vállalati eszközökön <!-- 3574267 -->
Teljes körűen felügyelt Android Enterprise-eszközök bevezetésével a felhasználók most már regisztrálva lesznek Azure Active Directory (HRE) az új vagy gyári visszaállítási eszköz kezdeti beállítása során. A teljes körűen felügyelt eszközhöz korábban a telepítés befejeződése után a felhasználónak manuálisan kell elindítania a Microsoft Intune alkalmazást a HRE-regisztráció elindításához. Most, amikor a felhasználó a kezdeti beállítás után az eszköz kezdőlapján landol, az eszköz regisztrálása és regisztrálása is megtörténik.

A HRE-frissítések mellett az Intune app Protection-szabályzatok (alkalmazás) mostantól teljes körűen felügyelt Android Enterprise-eszközökön is támogatottak. Ez a funkció az üzembe helyezés során elérhetővé válik. További információ: [felügyelt Google Play-alkalmazások hozzáadása androidos vállalati eszközökhöz az Intune](../apps/apps-add-android-for-work.md)-nal.

## <a name="week-of-june-24-2019"></a>2019. június 24-i hét 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Annak konfigurálása, hogy melyik böngésző számára engedélyezett a szervezeti adatkapcsolat <!-- 3145939 -->
Az Android és iOS rendszerű eszközökön elérhető Intune App Protection szabályzatok mostantól lehetővé teszik, hogy az Intune Managed Browser vagy a Microsoft Edge alkalmazáson kívül egy adott böngészőre is átvigye a szervezeti webhivatkozásokat.  További információ az ALKALMAZÁSról: [Mi az az App Protection-szabályzat?](../apps/app-protection-policy.md).

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Minden alkalmazás lap az online/offline Microsoft Store for Business Apps szolgáltatást azonosítja<!--4089647 -->
A **minden alkalmazás** oldalon elérhetők az Microsoft Store for Business (MSFB) alkalmazások online vagy offline alkalmazásként való azonosítására szolgáló címkék is. Minden MSFB-alkalmazás már tartalmaz egy utótagot **online** vagy **offline állapotba**. Az alkalmazás részletei lap a **licenc típusát** is tartalmazza, és **támogatja az eszközök környezetének telepítését** (csak offline licenccel rendelkező alkalmazások) kapcsolatos információk.

#### <a name="company-portal-app-on-windows-shared-devices---4393553---"></a>Céges portál alkalmazás a Windows megosztott eszközökön <!--4393553 -->
A felhasználók mostantól hozzáférhetnek a Céges portál alkalmazáshoz a Windows megosztott eszközökön. A végfelhasználók egy **megosztott** címkét fognak látni az eszköz csempén. Ez a Windows Céges portál alkalmazás 10.3.45609.0 és újabb verziójára vonatkozik.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page----4224326---"></a>Az összes telepített alkalmazás megtekintése új Céges portál weboldalról <!-- 4224326 -->
A Céges portál webhely új **telepített alkalmazások** lapja felsorolja a felhasználó eszközeire telepített összes felügyelt alkalmazást (mindkettő szükséges és elérhető). A hozzárendelés típusa mellett a felhasználók láthatják az alkalmazás közzétevőjét, a közzététel dátumát és a jelenlegi telepítési állapotot. Ha még nem tette meg a felhasználók számára szükséges vagy elérhető alkalmazásokat, egy üzenet jelenik meg arról, hogy nincs telepítve vállalati alkalmazás. Ha szeretné megtekinteni az új lapot a weben, lépjen a [céges portál webhelyére](https://portal.manage.microsoft.com) , és kattintson a **telepített alkalmazások**elemre.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device----2352913---"></a>Az új nézet lehetővé teszi, hogy az alkalmazások felhasználói lássák az eszközre telepített összes felügyelt alkalmazást. <!-- 2352913 -->  
A Windows Céges portál alkalmazás mostantól felsorolja a felhasználó eszközére telepített összes felügyelt alkalmazást (mindkettő kötelező és elérhető). A felhasználók láthatják a megkísérelt és függőben lévő alkalmazás-telepítéseket, valamint a jelenlegi állapotukat is. Ha még nem tette meg a felhasználók számára a szükséges vagy elérhető alkalmazásokat, megjelenik egy üzenet, amely arról tájékoztatja, hogy nincsenek telepítve a vállalati alkalmazások. Az új nézet megjelenítéséhez nyissa meg a Céges portál navigációs ablaktáblát, és válassza az **alkalmazások** > **telepített alkalmazások**elemet.    

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Kernel-bővítmények beállításainak konfigurálása macOS-eszközökön <!-- 2043024 -->
MacOS-eszközökön létrehozhat egy eszköz konfigurációs profilt (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > a **MacOS** a platformhoz lehetőséget). Ez a frissítés olyan új beállításokat tartalmaz, amelyek lehetővé teszik a kernel-bővítmények konfigurálását és használatát az eszközökön. Hozzáadhat konkrét bővítményeket, vagy engedélyezheti az összes bővítményt egy adott partnertől vagy fejlesztőtől.

További információ erről a szolgáltatásról: a [kernel-bővítmények áttekintése](../configuration/kernel-extensions-overview-macos.md) és a [kernel-bővítmény beállításai](../configuration/kernel-extensions-settings-macos.md).

A következőkre vonatkozik: macOS 10.13.2 és újabb verziók

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002---"></a>A csak áruházból származó alkalmazások Windows 10-es eszközökön való beállítása további konfigurációs beállításokat tartalmaz <!-- 2697002 -->
Ha Windows-eszközökhöz hoz létre egy eszköz-korlátozási profilt, a **csak az áruházból származó alkalmazásokat** használhatja, így a felhasználók csak a Windows App Store áruházból telepítik az alkalmazásokat (az**eszköz konfigurációja** > **profilok** > **Létrehozás profil** > **Windows 10 és újabb verzió** a platform > **eszközre vonatkozó korlátozások** a profil típusa esetén). Ebben a frissítésben ez a beállítás ki van bővítve a további beállítások támogatásához. 

Az új beállítás megjelenítéséhez nyissa meg a [Windows 10 (és újabb) eszközbeállítások beállításait a szolgáltatások engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-windows-10.md#app-store).

A Windows 10 és újabb verziókra vonatkozik

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Több Zebra Mobility Extensions-eszköz profiljának üzembe helyezése egy eszközön, azonos felhasználói csoporton vagy azonos eszközök csoporton <!-- 4089955 -->
Az Intune-ban az eszköz konfigurációs profiljában a zebra Mobility Extensions (MX) segítségével testre szabhatja az Intune-ba nem beépített Zebra-eszközök beállításait. Jelenleg egyetlen eszközre is telepíthet egyetlen profilt. Ebben a frissítésben több profilt is üzembe helyezhet:
- Ugyanazon felhasználói csoport
- Ugyanazok az eszközök csoport
- Egyetlen eszköz

Az MX használata az Intune-ban című témakörben Microsoft Intune bemutatja, hogyan használhatók a zebra- [eszközök a zebra Mobility Extensions bővítménnyel](../configuration/android-zebra-mx-overview.md) .

A következőkre vonatkozik: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Egyes kioszk-beállítások iOS-eszközökön a "letiltás" értékkel vannak beállítva, az "engedélyezés" kifejezés helyett <!-- 4404075  -->
Ha iOS-eszközökön hoz létre egy eszköz-korlátozási profilt (az**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **iOS** for platform > **eszközre vonatkozó korlátozások** a profil típusaként > **kioszk** ) beállítja az **automatikus zárolást**, a **csengetés kapcsolóját**, a **képernyő elforgatását**, a **képernyő alvó állapotának gombját**és a **hangerő gombokat**. 

Ebben a frissítésben az értékek **blokkolva** vannak (blokkolja a funkciót), és **nincs konfigurálva** (engedélyezi a funkciót). A beállítások megjelenítéséhez nyissa meg az [IOS-eszköz beállításait a funkciók engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-ios.md#kiosk). 

A következőre vonatkozik: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704---"></a>A jelszó-hitelesítéshez használja a Face ID-t iOS-eszközökön <!-- 4490704 -->
IOS-eszközökhöz tartozó eszköz-korlátozási profil létrehozásakor ujjlenyomatot használhat a jelszóhoz. Ebben a frissítésben az ujjlenyomat jelszavának beállításai is lehetővé teszik az Arcfelismerés (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **iOS** platformhoz > **eszközre vonatkozó korlátozások** a profilhoz írja be > **jelszót**). Ennek eredményeképpen a következő beállítások változtak:

- Az **ujjlenyomat feloldása** most érintse meg az **azonosító és a Face ID feloldása**lehetőséget.
- Az **ujjlenyomat módosítása (csak felügyelt** eszköz esetén) most érintse meg az **azonosító és a Face ID módosítását (csak felügyelt**eszköz esetén).

A Face ID az iOS 11,0-es és újabb verzióiban érhető el. A beállítások megjelenítéséhez nyissa meg az [IOS-eszköz beállításait, és engedélyezze vagy korlátozza a szolgáltatásokat az Intune használatával](../configuration/device-restrictions-ios.md#password).

A következőre vonatkozik: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region----4593948---"></a>A játékok és az App Store-szolgáltatások iOS-eszközökön való korlátozása mostantól a minősítési régiótól függ <!-- 4593948 -->
IOS-eszközökön engedélyezheti vagy korlátozhatja a játékokhoz, az App Store-hoz és a dokumentumok megtekintéséhez kapcsolódó funkciókat (**eszköz-konfiguráció**  > **profilok**  > **profil létrehozása**  > **iOS** platformon > **eszköz** a profil típusának korlátozásai > **App Store, doc Viewing, Gaming**). Kiválaszthatja a minősítési régiót is, például a Egyesült Államok. 

Ebben a frissítésben az **alkalmazások** szolgáltatás egy gyermek **minősítési régióba**kerül, és a **minősítési régiótól**függ. A beállítások megjelenítéséhez nyissa meg az [IOS-eszköz beállításait, és engedélyezze vagy korlátozza a szolgáltatásokat az Intune használatával](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

A következőre vonatkozik: iOS

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join----4809146--"></a>Windows Autopilot-támogatás hibrid Azure AD-csatlakozáshoz <!-- 4809146-->
A meglévő eszközökhöz készült Windows Autopilot mostantól támogatja a hibrid Azure AD-csatlakozást (a meglévő Azure AD-csatlakozás támogatása mellett). A Windows 10 1809-es vagy újabb verziójára vonatkozik. További információ: [a Windows Autopilot a meglévő eszközökhöz](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices).



### <a name="device-management"></a>Eszközkezelés

#### <a name="see-the-security-patch-level-for-android-devices----4461911---"></a>Tekintse meg az androidos eszközök biztonsági javítási szintjét <!-- 4461911 -->
Most már megtekintheti az Android-eszközök biztonsági javítási szintjét. Ehhez válassza az **Intune**  > **eszközök**  > **minden eszköz** lehetőséget, > válasszon egy eszközt > **hardver**.
A javítási szint az **operációs rendszer** szakaszban szerepel.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Hatókör-címkék társítása egy biztonsági csoportban lévő összes felügyelt eszközhöz <!-- 3173810 -->
Mostantól hozzárendelheti a hatókörhöz tartozó címkéket egy biztonsági csoporthoz, és a biztonsági csoportban lévő összes eszköz hozzá lesz rendelve a hatókörhöz tartozó címkékhez is. Az ezekben a csoportokban lévő összes eszköz hozzá lesz rendelve a hatókör címkéhez is. Az ezzel a szolgáltatással beállított hatókör-címkék felülírják az aktuális eszköz hatóköre címkék folyamatával beállított hatóköri címkéket. További információ: [a RBAC és a hatókör-címkék használata a terjesztéshez](scope-tags.md).

### <a name="device-security"></a>Eszköz biztonsága

#### <a name="use-keyword-search-with-security-baselines-------"></a>Kulcsszavas keresés használata biztonsági alaptervekkel <!--  -->
A [biztonsági](../protect/security-baselines.md#create-the-profile)alapkonfigurációk létrehozásakor vagy szerkesztésekor megadhat kulcsszavakat az új *keresési* sávban a keresési feltételeket tartalmazó elérhető csoportok szűréséhez. 

#### <a name="the-security-baselines-feature-is-now-generally-available-----3785395---"></a>A biztonsági alapkonfigurációk szolgáltatás mostantól általánosan elérhető  <!-- 3785395 -->
A **biztonsági** alapkonfigurációk szolgáltatás előzetes verzióban érhető el, és mostantól általánosan elérhető (GA).  Ez azt jelenti, hogy a szolgáltatás készen áll az éles környezetben való használatra. Az egyes alapkonfigurációk azonban előzetes verzióban is megmaradhatnak, és a saját ütemezésük alapján kiértékelik és kiadhatják a GA-nak.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available------3794072-4217151--3534649---"></a>A MDM biztonsági alapkonfiguráció sablonja már általánosan elérhető   <!-- 3794072, 4217151,  3534649 -->
A MDM biztonsági alapkonfiguráció sablonja ki lett helyezve az előzetes verzióra, és már általánosan elérhető (GA). A GA-sablon a 2019-as **Mdm biztonsági**alapkonfigurációként van azonosítva.  Ez egy új sablon, és nem az előzetes verzióról való frissítés.  Új sablonként át kell tekintenie a [benne található beállításokat](../protect/security-baseline-settings-mdm.md), majd új profilokat kell létrehoznia a sablon üzembe helyezéséhez az eszközön. Más biztonsági alapkonfigurációk is megmaradhatnak az előzetes verzióban. Az elérhető alapkonfigurációk listáját itt tekintheti meg: [elérhető biztonsági](../protect/security-baselines.md#available-security-baselines)alapkonfigurációk.  

Az új sablon mellett a *május 2019 sablon Mdm biztonsági alapterve* a következő két beállítást tartalmazza, amelyeket nemrégiben jelentettünk be a fejlesztési cikkben:  
- Zárolás fent: az alkalmazások hangvezérelt aktiválása zárolt képernyőről  
- DeviceGuard: a virtualizálás-alapú biztonság (VBS) használata az eszközök következő újraindításakor.  

A *május 2019-es Mdm biztonsági* alapkonfiguráció több új beállítás hozzáadását is magában foglalja, mások eltávolítását, valamint egy beállítás alapértelmezett értékének egy változatát. Az előzetes verzióról a GA-re való változások részletes listáját az **új sablon**változásai című részben tekintheti meg.

#### <a name="security-baseline-versioning-----3194322---"></a>Biztonsági alapterv verziószámozása  <!-- 3194322 -->
Az Intune biztonsági alapkonfigurációi támogatják a verziószámozást. Ha ezzel a támogatással az egyes biztonsági alapkonfigurációk új verziói jelennek meg, akkor a meglévő biztonsági alapkonfigurációkat úgy frissítheti, hogy az új alapterv újbóli létrehozása és üzembe helyezése nélkül is felhasználható legyen. Emellett az Intune-konzolon megtekintheti az egyes alapbeállításokkal kapcsolatos információkat, például az alapkonfigurációt használó egyedi profilok számát, a profilok által használt különböző alapkonfigurációkat, valamint az adott biztonság legújabb kiadását. az alapterv volt.  További információ: **biztonsági alaptervek**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved-----4501151---"></a>A bejelentkezési beállításhoz tartozó biztonsági kulcsok használata áthelyezve  <!-- 4501151 -->
A **bejelentkezéshez használt** "Identity Protection" nevű eszköz konfigurációs beállítása már nem található a *Windows Hello for Business konfigurálásának*albeállításaként. Ez most egy legfelső szintű beállítás, amely mindig elérhető, még akkor is, ha nem engedélyezi a vállalati Windows Hello használatát. További információ: [Identity Protection](../protect/identity-protection-windows-settings.md).

### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="new-permissions-for-assigned-group-admins------4504437-----"></a>Új engedélyek a hozzárendelt csoport rendszergazdái számára   <!-- 4504437   -->
Az Intune beépített iskolai rendszergazdai szerepköre mostantól rendelkezik a felügyelt alkalmazások létrehozására, olvasására, frissítésére és törlésére (szifilisz) vonatkozó engedélyekkel. Ez a frissítés azt jelenti, hogy ha Intune for Education-beli csoport-rendszergazdaként van társítva, mostantól létrehozhatja, megtekintheti, frissítheti és törölheti az iOS-MDM Push-tanúsítvány, az iOS MDM-kiszolgálói tokeneket, valamint az iOS VPP-tokeneket az [összes meglévő engedélyével](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions)együtt. A műveletek bármelyikének elvégzéséhez nyissa meg a **bérlői beállítások** > **iOS-eszközök felügyeletét**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials----4655885---"></a>Az alkalmazások a Graph API használatával felhasználói hitelesítő adatok nélkül hívhatják meg az olvasási műveleteket <!-- 4655885 -->
Az alkalmazások felhasználói hitelesítő adatok nélkül hívhatják meg az Intune-Graph API olvasási műveleteit az alkalmazás identitásával. További információ az Intune-hoz készült Microsoft Graph API eléréséről: az [Intune használata a Microsoft Graphban](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps----4392555---"></a>Hatókör-címkék alkalmazása Microsoft Store vállalati alkalmazásokhoz <!-- 4392555 -->
Mostantól alkalmazhat hatókör-címkéket Microsoft Store vállalati alkalmazásokhoz. A hatókör-címkékkel kapcsolatos további információkért lásd: [a szerepköralapú hozzáférés-vezérlés (RBAC) és a hatókör-címkék használata a terjesztéshez](scope-tags.md).

## <a name="week-of-june-17-2019"></a>2019. június 17-i hét 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="new-features-in-microsoft-intune-app"></a>Microsoft Intune alkalmazás új funkciói
Új funkciókkal bővült az Androidhoz készült Microsoft Intune alkalmazás (előzetes verzió). A teljes körűen felügyelt Android-eszközök felhasználói mostantól a következőket tehetik:  

* Megtekintheti és kezelheti az Intune Céges portál vagy Microsoft Intune alkalmazással regisztrált eszközöket.    
* Segítségért forduljon a szervezethez.    
* Küldjön visszajelzést a Microsoftnak.    
* Megtekintheti a feltételeket és kikötéseket, ha azokat a szervezete állítja be.    

## <a name="week-of-june-10-2019"></a>2019. június 10-i hét 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github----2653471---"></a>A GitHubon elérhető Intune SDK-integrációt bemutató új minta alkalmazások <!-- 2653471 -->
A msintuneappsdk GitHub-fiók új, az iOS (Swift), az Android, a Xamarin. iOS, a Xamarin Forms és a Xamarin. Android alkalmazásokhoz készült példákkal bővült. Ezeknek az alkalmazásoknak a célja, hogy kiegészítsék meglévő dokumentációját, és bemutatjuk, hogyan integrálhatja az Intune APP SDK-t a saját Mobile Apps szolgáltatásba. Ha olyan alkalmazás fejlesztője van, amelynek további Intune SDK-útmutatásra van szüksége, tekintse meg a következő csatolt mintákat:
- [Csevegés](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) – natív iOS (Swift) azonnali üzenetküldési alkalmazás, amely a Azure Active Directory Authentication Library (ADAL) protokollt használja a felügyelt hitelesítéshez.
- [TASKER](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) – a ADAL-t a felügyelt hitelesítéshez használó natív androidos Todo-lista alkalmazás.
- [TASKER](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) – Xamarin. Android Todo-lista alkalmazás, amely ADAL használ a felügyelt hitelesítéshez, ez a tárház a Xamarin. Forms alkalmazást is tartalmazza.
- [Xamarin. iOS minta alkalmazás](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) – A barebones Xamarin. iOS minta alkalmazás.

## <a name="week-of-may-27-2019"></a>Május 27., 2019. hét 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Az Android-eszközökön feltehetően ártalmas alkalmazások jelentése <!-- 4223162 -->
Az Intune mostantól további jelentéskészítési információkat biztosít az Android-eszközökön található potenciálisan ártalmas alkalmazásokról. 

## <a name="week-of-may-20-2019"></a>2019. május 20. hét 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="windows-company-portal-app----3316993---"></a>Windowsos Munkahelyi portál alkalmazás <!-- 3316993 -->
A Windows Céges portál alkalmazás mostantól egy új lap címkével ellátott **eszközeit**fogja tartalmazni. Az **eszközök** lap megjeleníti a végfelhasználók összes regisztrált eszközét. Ha a 10.3.4291.0 vagy újabb verziót használja, a felhasználók ezt a változást fogják látni a Céges portálban. További információ a Céges portál konfigurálásáról: [Microsoft Intune céges portál alkalmazás konfigurálása](../apps/company-portal-app.md).

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Az Autopilot-eszköz Rendeléskód attribútumának neve a csoport címkére módosult <!-- 4659453 -->

Ahhoz, hogy intuitívabb legyen, a **Rendeléskód** -attribútum neve az Autopilot-eszközökön **csoport címkére**módosult. Ha a CSV-t használja az Autopilot-eszköz adatainak feltöltésére, akkor a Group címkét oszlop fejlécként kell használni, a Rendeléskód nem.  

## <a name="week-of-may-13-2019"></a>Május 13-i hét, 2019 

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359----"></a>Az Intune-szabályzatok frissítik a hitelesítési módszert és Céges portál alkalmazás telepítését  <!-- 1927359  -->
A beállítási Asszisztensen keresztül már regisztrált eszközökön az Apple vállalati eszközök egyik regisztrációs módszerén keresztül az Intune többé nem fogja támogatni a Céges portál, ha az App Store-ból végfelhasználók manuálisan telepítik. Ez a módosítás csak akkor érvényes, ha a regisztráció során az Apple beállítási asszisztenssel végzi a hitelesítést. Ez a módosítás csak az alábbi módon beléptetett iOS-eszközökre vonatkozik:  
* Apple konfigurátor

* Apple Business Manager

* Apple School Manager

* Apple Készülékregisztrációs program (DEP)

Ha a felhasználók telepítik a Céges portál alkalmazást az App Store áruházból, majd megpróbálják regisztrálni ezeket az eszközöket, hibaüzenetet kapnak. Ezeket az eszközöket a rendszer csak akkor fogja használni, ha a regisztráció során az Intune automatikusan leküldte a Céges portál. Az Intune-ban lévő beléptetési profilok a Azure Portal frissülni fognak, így megadhatja, hogyan történjen az eszközök hitelesítése, és ha megkapják a Céges portál alkalmazást. Ha azt szeretné, hogy a DEP-eszköz felhasználói rendelkezzenek a Céges portál, meg kell adnia a beállításait egy beléptetési profilban. 

Emellett az iOS-Céges portálban az **eszköz azonosítása** képernyő is törlődik. Ezért a rendszergazdáknak, akik engedélyezni szeretnék a feltételes hozzáférést, vagy vállalati alkalmazásokat kell telepíteniük, frissíteniük kell a DEP regisztrációs profilt. Ez a követelmény csak akkor érvényes, ha a DEP-regisztráció a beállítási asszisztenssel van hitelesítve. Ebben az esetben a Céges portált az eszközre kell leküldeni. Ehhez válassza az **Intune** > **eszközök beléptetése** > **Apple-regisztráció** > **beléptetési program jogkivonatok** elemet > Válassza ki a tokent > **profilok** > válasszon egy profilt > **Tulajdonságok** > Set  **Telepítse a Céges portált** **Igen**értékre.

Ha a Céges portál a már regisztrált DEP-eszközökön szeretné telepíteni, akkor az Intune-ban > ügyfélalkalmazások elemre kell kattintania, és felügyelt alkalmazásként kell leküldeni az alkalmazás-konfigurációs házirendekkel. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Annak konfigurálása, hogy a végfelhasználók hogyan frissíthetnek egy üzletági (LOB) alkalmazást egy alkalmazás-védelmi házirend használatával <!-- 3568384 -->
Most már beállíthatja, hogy a végfelhasználók hol szerezhetik be az üzletági (LOB) alkalmazások frissített verzióját. A végfelhasználók láthatják ezt a szolgáltatást a **minimális app Version** feltételes indítási párbeszédpanelen, amely arra kéri a végfelhasználókat, hogy frissítsen az üzletági alkalmazás minimális verziójára. Ezeket a frissítés részleteit a LOB-alkalmazás védelmi házirendjének (alkalmazás) részeként kell megadnia. Ez a funkció iOS és Android rendszereken érhető el. IOS rendszeren ez a funkció megköveteli, hogy az alkalmazás integrálva legyen (vagy becsomagolva a burkoló eszköz használatával) az iOS-hez készült Intune SDK-val. 10.0.7 vagy újabb. Androidon a szolgáltatáshoz a legújabb Céges portál szükséges. Annak konfigurálásához, hogy a végfelhasználó hogyan frissítsen egy LOB-alkalmazást, az alkalmazásnak szüksége van egy felügyelt alkalmazás konfigurációs szabályzatára, amelyet a kulcsával, `com.microsoft.intune.myappstore` értékkel kell elküldeni. Az elküldés érték határozza meg, hogy a végfelhasználó melyik tárolóban tölti le az alkalmazást. Ha az alkalmazás a Céges portálon keresztül lett telepítve, az értéknek `CompanyPortal` értékűnek kell lennie. Bármely más áruház esetében teljes URL-címet kell megadnia.

#### <a name="intune-management-extension-powershell-scripts-----3734186----"></a>Intune felügyeleti bővítmény PowerShell-parancsfájlok  <!-- 3734186  -->
Konfigurálhatja a PowerShell-parancsfájlokat úgy, hogy az eszközön a felhasználó rendszergazdai jogosultságával fussanak. További információ: PowerShell- [parancsfájlok használata a Windows 10-es eszközökön az Intune-ban](../apps/intune-management-extension.md) és a [win32 app managementben](../apps/app-management.md).

#### <a name="android-enterprise-app-management----4459905---"></a>Androidos vállalati alkalmazások kezelése <!-- 4459905 -->
Annak érdekében, hogy a rendszergazdák könnyebben konfigurálják és használják az Android Enterprise managementet, az Intune automatikusan négy általános androidos vállalati alkalmazást ad hozzá az Intune felügyeleti konzolhoz. A négy androidos vállalati alkalmazás a következő alkalmazások:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** – az Android Enterprise teljes körűen felügyelt forgatókönyvekhez használható.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** – segít bejelentkezni a fiókjába, ha kétfaktoros ellenőrzést használ.
- **[Intune céges portál](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** – az alkalmazás-és az Android Enterprise Work-profil forgatókönyvek esetében használatos.
- [Felügyelt kezdőképernyő](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) – az Android Enterprise dedikált/kioszk forgatókönyvek esetében használható.

Korábban a rendszergazdáknak manuálisan kell megkeresniük és jóváhagynia ezeket az alkalmazásokat a [felügyelt Google Play áruházban](https://play.google.com/store/apps) a telepítés részeként. Ez a módosítás eltávolítja ezeket a korábban kézi lépéseket, így egyszerűbbé és gyorsabbá teszi az ügyfelek számára az Android Enterprise Management használatát.

A rendszergazdák láthatják, hogy ezek a négy alkalmazás automatikusan hozzá lesz adva az Intune-alkalmazások listájához, amikor először csatlakoznak az Intune-bérlőhöz a felügyelt Google Play szolgáltatáshoz. További információ: [az Intune-fiók összekötése a felügyelt Google Play-fiókkal](../enrollment/connect-intune-android-enterprise.md). Azok a bérlők, akik már csatlakoztak a bérlőhöz, vagy akik már használják az Android Enterprise-t, nincs szükség a rendszergazdákra. A következő négy alkalmazás automatikusan megjelenik a május 2019 szolgáltatás bevezetésének befejezését követő 7 napon belül.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune-----1533038---"></a>A PFX tanúsítvány-összekötő frissítése a Microsoft Intune  <!-- 1533038 -->
Kiadott egy frissítést a [pfx tanúsítvány-összekötőhöz Microsoft Intune számára](../protect/certficates-pfx-configure.md#whats-new-for-connectors) , amely egy olyan hibával foglalkozik, amelyben a meglévő pfx-tanúsítványok továbbra is újrafeldolgozásra kerülnek, ami miatt az összekötő leállítja az új kérések feldolgozását.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Intune-beli biztonsági feladatok a Defender ATP-ben (nyilvános előzetes verzió)     <!-- 3208597 -->
A nyilvános előzetes verzióban az Intune használatával kezelheti a [Microsoft Defender komplex veszélyforrások elleni védelem (ATP) biztonsági feladatait](../protect/atp-manage-vulnerabilities.md). Ez az ATP-integráció és a kockázati alapú megközelítés a végponti biztonsági rések és helytelen konfigurációk felderítéséhez, rangsorolásához és javításához, valamint a felderítés és a hibák enyhítése közötti idő csökkentéséhez.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>TPM-chipkészlet keresése Windows 10-es eszköz megfelelőségi szabályzatában <!-- 3617671   idstaged-->
Számos Windows 10 és újabb rendszerű eszköz rendelkezik platformmegbízhatósági modul (TPM) chipsettel. Ez a frissítés egy új megfelelőségi beállítást tartalmaz, amely ellenőrzi a TPM-lapka verzióját az eszközön. 

A [Windows 10-es és újabb megfelelőségi szabályzatok beállításai](../protect/compliance-policy-create-windows.md#device-security) ezt a beállítást ismertetik.

A Windows 10 és újabb verziókra vonatkozik

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Annak megakadályozása, hogy a végfelhasználók módosíthassák a személyes hozzáférési pontokat, és tiltsa le a Siri Server naplózását iOS-eszközökön <!-- 4097904   -->  
Létrehozhat egy eszköz-korlátozási profilt iOS-eszközön (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **iOS** a platform > **eszközre vonatkozó korlátozások** a profil típusa esetén). Ez a frissítés olyan új beállításokat is tartalmaz, amelyeket konfigurálhat:

- **Beépített alkalmazások**: kiszolgálóoldali naplózás a Siri-parancsokhoz
- **Vezeték nélküli**: a személyes hozzáférési pont felhasználói módosítása (csak felügyelt eszköz esetén)

Ezeknek a beállításoknak a megtekintéséhez nyissa meg az iOS és a [vezeték nélküli beállítások](../configuration/device-restrictions-ios.md#wireless)iOS-hez című [beépített alkalmazás beállításait](../configuration/device-restrictions-ios.md#built-in-apps) .

A következőkre vonatkozik: iOS 12,2 és újabb

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Új osztályterem alkalmazás-eszköz korlátozási beállításai macOS-eszközökhöz <!-- 4097905   --> 
A macOS-eszközökhöz létrehozhat eszköz-konfigurációs profilokat (**eszköz-konfiguráció**  > **profilok**  > **profil létrehozása**  > **MacOS** platformon > **eszközre vonatkozó korlátozások** a profil típusa esetén). Ez a frissítés magában foglalja az új osztályterem alkalmazás beállításait, a képernyőképek blokkolásának lehetőségét, valamint az iCloud Photo Library letiltásának lehetőségét.

Ha szeretné megtekinteni az aktuális beállításokat, lépjen a [MacOS eszközbeállítások lehetőségre, hogy engedélyezze vagy korlátozza a szolgáltatásokat az Intune használatával](../configuration/device-restrictions-macos.md).

A következőkre vonatkozik: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>Az App Store-beállítások eléréséhez használt iOS-jelszó átnevezve<!-- 4557891  -->
Az **App Store-hoz való hozzáféréshez használt jelszó** átnevezve van az **iTunes Store-jelszó megkövetelése minden vásárláshoz** (**eszköz konfigurációja** > **profil** > **Create Profile** > **iOS** for platform > A profil típusa > az **App Store, a doc Viewing és a Gaming** **eszközre vonatkozó korlátozások** .

Az elérhető beállítások megjelenítéséhez nyissa meg az [App Store, a doc Viewing, a Gaming iOS beállításait](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

A következőre vonatkozik: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Microsoft Defender komplex veszélyforrások elleni védelem alapterve (előzetes verzió)  <!--  3754134 -->
Bővítettük a [Microsoft Defender komplex veszélyforrások elleni védelemhez](../protect/security-baseline-settings-defender-atp.md) tartozó biztonsági alapkonfiguráció előzetes verzióját. Ez az alapterv akkor érhető el, ha a környezet megfelel a [Microsoft Defender komplex veszélyforrások elleni védelem](../protect/advanced-threat-protection.md#prerequisites)használatának előfeltételeinek.

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>A Windows-regisztráció állapota lap (ESP) már általánosan elérhető <!-- 3605348 -->
A regisztráció állapota lap már nem előzetes verzió. További információ: [regisztráció állapotának beállítása lap](../enrollment/windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Intune felhasználói felület frissítése – Autopilot beléptetési profil létrehozása  <!-- 4593669 -->
Az Autopilot-beléptetési profil létrehozásához szükséges felhasználói felület frissítve lett az Azure felhasználói felületi stílusokkal való összehangolás érdekében. További információt az Autopilot- [beléptetési profil létrehozása](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile)című témakörben talál. A továbbítást követően további Intune-forgatókönyvek is frissülnek az új felhasználói felületi stílusba.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Az Autopilot alaphelyzetbe állításának engedélyezése az összes Windows-eszközön <!-- 4225665 -->
Az Autopilot alaphelyzetbe állítása mostantól minden Windows-eszközön működik, még azok is, amelyek nincsenek konfigurálva a regisztrációs állapot lap használatára. Ha a regisztráció állapotát jelző lap nem lett konfigurálva az eszközre a kezdeti eszközök beléptetése során, az eszköz a bejelentkezés után egyenesen az asztalra kerül. Akár nyolc órát is igénybe vehet, és az Intune-ban megfelelőnek tűnik. További információ: [eszközök alaphelyzetbe állítása a távoli Windows Autopilot alaphelyzetbe állításával](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>Az összes eszköz keresésekor nem szükséges pontos IMEI-formátum <!--30407680 -->
A **minden eszköz**keresésekor nem szükséges szóközöket bevenni az IMEI-számba.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Az eszközök az Apple Portalon való törlése az Intune-portálon jelenik meg <!--2489996 -->
Ha egy eszközt törölnek az Apple Készülékregisztrációs program vagy az Apple Business Manager portálról, az eszköz automatikusan törlődik az Intune-ból a következő szinkronizálás során.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>A regisztráció állapota lap most nyomon követi a Win32-alkalmazásokat <!-- 2714451 -->
Ez csak a Windows 10 1903-es vagy újabb verzióját futtató eszközökre vonatkozik. További információ: [regisztráció állapotának beállítása lap](../enrollment/windows-enrollment-status.md).

### <a name="device-management"></a>Eszközkezelés

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Eszközök tömeges visszaállítása és törlése a Graph API használatával <!-- 3295288 -->
Most visszaállíthatja és törölheti a több mint 100 eszközt a Graph API használatával.


### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>A titkosítási jelentés kívül esik a nyilvános előzetes verzióban   <!-- 4587546      -->
A [BitLocker és az eszközök titkosítására vonatkozó jelentés](../protect/encryption-monitor.md) már általánosan elérhető, és már nem része a nyilvános előzetes verziónak. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Az Outlook-aláírás és a biometrikus beállítások iOS és Android rendszerű eszközökhöz <!-- 4050557 -->
Mostantól megadhatja, hogy az alapértelmezett aláírás engedélyezve van-e az Outlookban iOS-és Android-eszközökön. Emellett dönthet úgy is, hogy lehetővé teszi a felhasználók számára, hogy megváltoztassák a biometrikus beállításokat az Outlookban az iOS-ben.

## <a name="week-of-may-6-2019"></a>Május 6-i hét, 2019 

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Hálózati Access Control (NAC) támogatása az iOS-eszközökre vonatkozó F5-hozzáféréshez <!-- 4500808 -->

F5 kiadott egy frissítést a BIG-IP 13-hez, amely lehetővé teszi, hogy a nagyvállalati funkciók F5-ös verzióhoz hozzáférjenek az Intune-ban A szolgáltatás használata:

- A BIG-IP frissítése a 13.1.1.5 frissítéséhez. A BIG-IP 14 nem támogatott.
- A BIG-IP integrálása az Intune-nal a NAC-hoz. Az [Áttekintés lépései: az APM konfigurálása eszköz-testtartási ellenőrzésekhez végpont-felügyeleti rendszerekkel](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Jelölje be a **hálózati Access Control (NAC) engedélyezése** beállítást a VPN-profilban az Intune-ban.

Az elérhető beállítások megjelenítéséhez nyissa [meg a VPN-beállítások konfigurálása iOS-eszközökön](../configuration/vpn-settings-ios.md)című témakört.

A következőre vonatkozik: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>A PFX tanúsítvány-összekötő frissítése a Microsoft Intune <!-- doc-vso 1521237  -->  
Kiadott egy frissítést a [pfx tanúsítvány-összekötőhöz a Microsoft Intune számára](../protect/certficates-pfx-configure.md#whats-new-for-connectors) , amely 5 perctől 30 másodpercre lecsökken a lekérdezési időköz.

## <a name="week-of-april-22-2019"></a>2019. április 22-i hét

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>A megfelelőség-kezelő használata a Microsoft Intune értékelésének létrehozásához<!-- 4404750 -->

A [megfelelőség-kezelő](https://servicetrust.microsoft.com/ComplianceManager) (egy másik Microsoft-webhely megnyitása) a Microsoft szolgáltatás megbízhatósági portálján a munkafolyamat-alapú kockázatfelmérési eszköz. Lehetővé teszi a szervezet Microsoft-szolgáltatásokkal kapcsolatos szabályozási megfelelőségi tevékenységeinek nyomon követését, hozzárendelését és ellenőrzését. Saját megfelelőségi értékelést hozhat létre az Office 365, az Azure, a Dynamics, a Professional Services és az Intune használatával. Az Intune-ban két értékelés érhető el: FFIEC és GDPR.

A megfelelőség-kezelő a Microsoft által felügyelt vezérlők és a szervezet által felügyelt vezérlőelemek lebontásával segít összpontosítani az erőfeszítéseket. Elvégezheti az értékeléseket, majd exportálhatja és kinyomtathatja az értékeléseket.

A [szövetségi pénzügyi intézmények vizsgáló Tanácsa (FFIEC)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (egy másik Microsoft-webhely megnyitása) a megfelelőség a FFIEC által kiállított online banki szabványok összessége. Ez az Intune-t használó pénzügyi intézmények által kért Értékelés. Azt értelmezi, hogy az Intune hogyan segít a nyilvános Felhőbeli munkaterhelésekkel kapcsolatos FFIEC-kiberbiztonsági-irányelvek teljesítésében. Az Intune FFIEC-felmérése a második FFIEC értékelés a megfelelőség-kezelőben.

A következő példában a FFIEC-vezérlők részletezése látható. A Microsoft 64-es vezérlőket tartalmaz. A fennmaradó 12 vezérlőért felelős.

![Tekintse meg a FFIEC Intune-értékelését, beleértve az ügyfél-és a Microsoft-műveleteket is](./media/whats-new/intune-ffiec-assessment-status.png)

[Általános adatvédelmi rendelet (GDPR)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (egy másik Microsoft-webhely megnyitása) az Európai Unió (EU) törvénye, amely segít a magánszemélyek és az adataik védelmében. Az adatvédelmi szabályozásoknak való megfelelés érdekében a GDPR a leginkább kért Értékelés. 

A következő példában a GDPR-vezérlők részletezése látható. A Microsoft 49-es vezérlőket tartalmaz. A fennmaradó 66-ellenőrzésért felelős.

![Tekintse meg a GDPR Intune-értékelését, beleértve az ügyfél-és a Microsoft-műveleteket is](./media/whats-new/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>2019. április 15-i hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>OpenSSL titkosítás androidos alkalmazás-védelmi házirendekhez <!-- 3747362 -->
Az Android-eszközökön az Intune app Protection-szabályzatok (alkalmazás) mostantól a FIPS 140-2 szabványnak megfelelő OpenSSL titkosítási függvénytárat használ. További információ: az [Android-alkalmazások védelmére vonatkozó házirend-beállítások](../apps/app-protection-policy-settings-android.md) [titkosítási](../apps/app-protection-policy-settings-android.md#encryption) szakasza Microsoft Intune.

#### <a name="enable-win32-app-dependencies----2617348----"></a>Win32-alkalmazások függőségeinek engedélyezése <!-- 2617348  -->
Rendszergazdaként szükség lehet arra, hogy a Win32-alkalmazás telepítése előtt más alkalmazások is a függőségként legyenek telepítve. Pontosabban, az eszköznek a Win32-alkalmazás telepítése előtt telepítenie kell a függő alkalmazást (ka) t. Az Intune-ban válassza az **ügyfélalkalmazások** > **alkalmazások** > **Hozzáadás** elemet az **alkalmazás hozzáadása** panel megjelenítéséhez. Az **alkalmazás típusaként**válassza a **Windows-alkalmazás (Win32)** lehetőséget. Az alkalmazás hozzáadása után a **függőségek** lehetőség kiválasztásával hozzáadhatja azokat a függő alkalmazásokat, amelyeket telepíteni kell a Win32-alkalmazás telepítése előtt. További információ: az [önálló Intune-win32 app Management](./../apps/app-management.md). 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Az alkalmazások verziójának telepítési információi a Microsoft Store for Business alkalmazásokhoz <!-- 3537391   -->
Az alkalmazás-telepítési jelentések a Microsoft Store for Business alkalmazások alkalmazás-verziójának információit tartalmazzák. Az Intune-ban válassza a **Client apps** > **alkalmazások**elemet. Válasszon ki egy **Microsoft Store for Business alkalmazást** , majd válassza az **eszköz telepítésének állapota** lehetőséget a **figyelés** szakaszban.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>A Win32-alkalmazások követelmény-szabályainak kiegészítése <!-- 3676883   -->
A követelmények szabályai a PowerShell-parancsfájlok, a beállításjegyzék-értékek és a fájlrendszer-információk alapján hozhatók létre. Az Intune-ban válassza a **Client apps** > **alkalmazások** > **Hozzáadás**elemet. Ezután válassza a **Windows-alkalmazás (Win32)** lehetőséget az alkalmazás **hozzáadása** panel **alkalmazás típusa** területén.  Válassza a **követelmények**  > **Hozzáadás** elemet a további követelmények szabályainak konfigurálásához. Ezután válassza a **Fájltípus**, a **beállításjegyzék**vagy a **parancsfájl** lehetőséget a **követelmény típusaként**. További információ: [win32 app Management](./../apps/app-management.md).

#### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>A Win32-alkalmazások konfigurálása az Intune-ban regisztrált Azure AD-hez csatlakoztatott eszközökre <!-- 3695227  -->
Hozzárendelheti a Win32-alkalmazásokat az Intune-ban regisztrált Azure AD-hez csatlakoztatott eszközökhöz. További információ az Intune-beli Win32-alkalmazásokról: [win32 app Management](./../apps/app-management.md).

#### <a name="device-overview-shows-primary-user---3794259----"></a>Az eszköz áttekintése az elsődleges felhasználót mutatja <!--3794259  -->
Az eszköz áttekintő oldala az elsődleges felhasználót, más néven a felhasználó-eszköz kapcsolat felhasználóját (UDA) fogja megjeleníteni. Az eszköz elsődleges felhasználójának megtekintéséhez válassza az **Intune**  > **eszközök**  > **minden eszköz** lehetőséget, > válasszon egy eszközt. Az elsődleges felhasználó megjelenik az **Áttekintés** oldal tetején.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>További felügyelt Google Play-alkalmazások jelentéskészítése androidos vállalati munkahelyi Profilos eszközökhöz <!-- 4105925  -->
Az Android Enterprise Work profiling-eszközökre telepített felügyelt Google Play-alkalmazások esetében megtekintheti az eszközre telepített alkalmazás adott verziószámát. Ez csak a szükséges alkalmazásokra vonatkozik.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>Harmadik féltől származó iOS-billentyűzetek <!-- 4111843   -->
Az iOS platformon a **harmadik féltől származó billentyűzetek** beállításához az Intune app Protection-szabályzat (alkalmazás) támogatása már nem támogatott. Ezt a beállítást nem fogja tudni konfigurálni az Intune felügyeleti konzolján, és nem lesz kikényszerítve az ügyfélen az Intune app SDK-ban.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>A bejelentkezési beállítások és a vezérlés újraindítási beállításainak megadása macOS-eszközökön <!-- 1210083  -->
MacOS-eszközökön létrehozhat egy eszköz konfigurációs profilt (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > válassza a **MacOS** lehetőséget a platform > **eszköz funkciói** a profil típusa számára). Ez a frissítés új bejelentkezési ablak-beállításokat tartalmaz, például egyéni szalagcímet jelenít meg, kiválaszthatja a felhasználók bejelentkezésének módját, az energiaellátási beállítások megjelenítését és elrejtését.

A beállítások megtekintéséhez válassza a MacOS- [eszköz funkció beállításait](../configuration/macos-device-features-settings.md).

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>WiFi konfigurálása Android Enterprise rendszerű eszközökön, a több alkalmazásból álló kioszk módban futó eszköz tulajdonos dedikált eszközei <!--3041940  -->
Engedélyezheti az Android Enterprise, az eszköz tulajdonosának beállításait, ha dedikált eszközként fut többalkalmazásos kioszk módban. Ebben a frissítésben engedélyezheti a felhasználók számára a WiFi hálózatok konfigurálását és csatlakoztatását (**Intune** > **eszköz konfigurációja** > **profilok** > **create Profile** > **Android Enterprise** for platform >  **Csak az eszköz tulajdonosa, az eszközre vonatkozó korlátozások** a profil típusa > **dedikált eszközök**1**kioszk mód**: **multi-app**4**WiFi konfiguráció**). 

Az összes konfigurálható beállítás megjelenítéséhez nyissa meg az [Android Enterprise-eszköz beállításait a funkciók engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-android-for-work.md).

A következőkre vonatkozik: a többalkalmazásos kioszk módban futó androidos vállalati dedikált eszközök


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>A Bluetooth és a párosítás konfigurálása az Android Enterprise-on, az eszköz tulajdonosának dedikált eszközei többalkalmazásos kioszk módban <!-- 3041941  -->
Engedélyezheti az Android Enterprise, az eszköz tulajdonosának beállításait, ha dedikált eszközként fut többalkalmazásos kioszk módban. Ebben a frissítésben engedélyezheti a végfelhasználók számára a Bluetooth használatát, és párosíthatja az eszközöket Bluetooth-kapcsolaton keresztül (**Intune** > **eszköz konfigurációja** > **profilok** > **create Profile** > **Android Enterprise** for csak a platform > **eszköz tulajdonosa,** az eszközre vonatkozó korlátozások a profil típusa > **dedikált eszközök**1**kioszk mód**: **multi-app**4**Bluetooth-konfiguráció**). 

Az összes konfigurálható beállítás megjelenítéséhez nyissa meg az [Android Enterprise-eszköz beállításait a funkciók engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-android-for-work.md).

A következőkre vonatkozik: a többalkalmazásos kioszk módban futó androidos vállalati dedikált eszközök

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>OEMConfig-eszközök konfigurációs profiljainak létrehozása és használata az Intune-ban <!-- 3305883  -->
Ebben a frissítésben az Intune támogatja az androidos vállalati eszközök konfigurálását a OEMConfig. Konkrétan létrehozhat egy eszköz-konfigurációs profilt, és beállításokat alkalmazhat az androidos vállalati eszközökre a OEMConfig használatával (**eszköz konfigurációja** > **profilok** > **create Profile** > **Android Enterprise** platform esetében).

A számítógépgyártók támogatása jelenleg OEM-alapú. Ha a használni kívánt OEMConfig-alkalmazás nem érhető el a OEMConfig-alkalmazások listájában, forduljon a `IntuneOEMConfig@microsoft.com`hoz.

A szolgáltatással kapcsolatos további információkért tekintse meg az [androidos nagyvállalati eszközök használata és kezelése a Microsoft Intune OEMConfig](../configuration/android-oem-configuration-overview.md)című témakört.

A következőkre vonatkozik: Android Enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Értesítések Windows Update  <!-- 3316758, 3316782  -->
Két *felhasználói élményre vonatkozó beállítást* adtunk hozzá az Intune-konzolon belül felügyelhető Windows Update Ring-konfigurációkhoz. Mostantól a következőket teheti:
- A [Windows-frissítések keresésének](../protect/windows-update-settings.md)tiltása vagy engedélyezése a felhasználóknak.
- Kezelheti a felhasználók által megjelenített [Windows Update értesítési szintet](../protect/windows-update-settings.md) .

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Az Android Enterprise, az eszköz tulajdonosa új eszköz korlátozási beállításai <!-- 3574254  -->
Az Android Enterprise rendszerű eszközökön létrehozhat egy eszköz-korlátozási profilt a funkciók engedélyezéséhez vagy korlátozásához, jelszó-szabályok beállításához és egyebekhez (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > az **Android kiválasztása Enterprise** for platform > **eszköz tulajdonosa csak > eszköz korlátozásai** a profil típusa). 

Ez a frissítés új jelszavas beállításokat tartalmaz, lehetővé teszi az alkalmazások teljes hozzáférését Google Play Áruház a teljes körűen felügyelt eszközökhöz és egyebekhez. A beállítások aktuális listájának megtekintéséhez lépjen az [Android Enterprise-eszköz beállításai lehetőségre a funkciók engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-android-for-work.md). 

A következőkre vonatkozik: Android Enterprise teljes körűen felügyelt eszközök

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>TPM-chipkészlet keresése Windows 10-es eszköz megfelelőségi szabályzatában <!-- 3617671 -->

Ez a szolgáltatás késleltetve van, és a tervek szerint később lesz közzétéve.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Frissített felhasználói felületi változások a Microsoft Edge böngészőhöz Windows 10 és újabb rendszerű eszközökön <!-- 3775833   -->
Az eszköz konfigurációs profiljának létrehozásakor engedélyezheti vagy korlátozhatja a Microsoft Edge-szolgáltatásokat a Windows 10 és újabb rendszerű eszközökön (**eszköz konfigurációja** > **profilok** > **create Profile** > **Windows 10 és újabb verziók** platform esetében > **eszközre vonatkozó korlátozásokat** a profil típusa > **Microsoft Edge böngésző**). Ebben a frissítésben a Microsoft Edge-beállítások jobban leíró jellegűek, és könnyebben megérthetők. 

A funkciók megjelenítéséhez nyissa meg a [Microsoft Edge böngésző eszközének korlátozási beállításait](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

A Windows 10 és újabb verziókra vonatkozik

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Bővített támogatás Android Enterprise teljes körűen felügyelt eszközökhöz (előzetes verzió)  <!--   3903241, 3903244, 3903246   -->
Még egy nyilvános előzetes verzióban is kibővítettük az Android Enterprise teljes körűen felügyelt eszközök támogatását (az[első a 2019 januárjában jelent](whats-new.md#week-of-january-14-2019) meg, amely a következőket tartalmazza: 

- A teljes körűen felügyelt és dedikált eszközökön [megfelelőségi szabályzatokat](../protect/compliance-policy-create-android-for-work.md) hozhat létre, amelyekkel belefoglalhatja a jelszavak szabályait és az operációs rendszerre vonatkozó követelményeket (**eszköz megfelelőségi**  > **szabályzatok**  >   > **házirend létrehozása**  **Vállalati** platform >- **eszköz tulajdonosa** a profil típusaként). 

  A dedikált eszközökön előfordulhat, hogy az eszköz **nem megfelelőként**jelenik meg. A feltételes hozzáférés nem érhető el dedikált eszközökön. Ügyeljen arra, hogy minden feladatot vagy műveletet végrehajtson, hogy a dedikált eszközök megfeleljenek a hozzárendelt szabályzatoknak.

- [Feltételes hozzáférés](../protect/conditional-access.md) – az Androidra érvényes feltételes hozzáférési szabályzatok az Android Enterprise teljes körűen felügyelt eszközökre is érvényesek. A felhasználók mostantól regisztrálhatják teljes mértékben felügyelt eszközét Azure Active Directory a **Microsoft Intune alkalmazással**. Ezután tekintse meg és oldja meg a szervezeti erőforrások elérésére vonatkozó megfelelőségi problémákat.

- Új végfelhasználói alkalmazás (Microsoft Intune alkalmazás) – új végfelhasználói alkalmazás érhető el az Android rendszerű, teljes mértékben felügyelt eszközökhöz, amelyeket **Microsoft Intune**. Ez az új alkalmazás könnyű és modern, és hasonlóan működik a Céges portál alkalmazáshoz, de a teljes körűen felügyelt eszközökhöz. További információ: [Microsoft Intune alkalmazás a Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune)áruházban.

Az Android teljes körűen felügyelt eszközeinek beállításához lépjen az **eszközök beléptetése** > **Android-regisztráció** > **vállalati tulajdonú, teljes körűen felügyelt felhasználói eszközök**elemre. A teljes körűen felügyelt Android-eszközök támogatása előzetes verzióban érhető el, és előfordulhat, hogy egyes Intune-funkciók nem teljesen működőképesek.  

Ha többet szeretne megtudni erről az előzetes verzióról, tekintse meg a blogot, [Microsoft Intune-Preview 2 for Android Enterprise teljes körűen felügyelt eszközeit](https://aka.ms/preview2_AE_fullymanaged).


### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Profil beállítása a képernyők kihagyására a beállítási asszisztens során <!-- 2276470  -->
MacOS-regisztrációs profil létrehozásakor beállíthatja, hogy a következő képernyők bármelyikét kiugorja, amikor a felhasználó áthalad a beállítási Asszisztensen:
- Megjelenését
- Hang megjelenítése
- iCloudStorage ha új profilt hoz létre, vagy szerkeszt egy profilt, a kijelölt kihagyási képernyőknek szinkronizálnia kell az Apple MDM-kiszolgálóval.  A felhasználók manuálisan is szinkronizálhatják az eszközöket, így nincs késés a profil módosításainak felvételekor.
További információ: macOS- [eszközök automatikus regisztrálása a Készülékregisztrációs program vagy az Apple School Managerrel](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Csoportos eszköz elnevezése vállalati iOS-eszközök regisztrálásakor<!--3566569  -->
Ha az Apple vállalati beléptetési módszereit (DEP/ABM/ASM) használja, megadhatja az eszköz nevének formátumát a bejövő iOS-eszközök automatikus neveként. Megadhat egy olyan formátumot, amely tartalmazza az eszköz típusát és a sorozatszámot a sablonban. Ehhez válassza az **Intune** > **eszközök beléptetése** > **Apple-regisztráció** > **beléptetési program jogkivonatok** > **token** >**profil létrehozása**1**eszköz elnevezése elemet. formátum**. Szerkesztheti a meglévő profilokat, de csak az újonnan szinkronizált eszközök lesznek érvényesek.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Frissített alapértelmezett időtúllépési üzenet a regisztráció állapota lapon <!-- 3959331 -->
Frissítettük az alapértelmezett időtúllépési üzenet felhasználóit, ha a regisztrációs állapot lap (ESP) meghaladja az ESP-profilban megadott időtúllépési értéket. Az új alapértelmezett üzenet az, amit a felhasználók látnak és segítenek megérteni a következő műveleteket az ESP-telepítéssel.  

### <a name="device-management"></a>Eszközkezelés

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Nem megfelelő eszközök kivonása  <!-- 1827291   -->
A szolgáltatás késleltetve lett, és egy későbbi kiadásra van tervezve.


### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Az Intune-adattárház 1.0-s verziójának módosításai visszaállnak a bétaverzióba <!-- 4403765 -->
Ha a 1.0-s verzió először mutatkozott be a 1808-ben, a Beta API néhány jelentős módon eltért. 1903 ezek a változások a Beta API-verzióba kerülnek vissza. Ha olyan fontos jelentésekkel rendelkezik, amelyek a Beta API verzióját használják, javasoljuk, hogy a módosítások elvégzése érdekében váltson át a jelentéseket a 1.0-s verzióra. További információkért lásd: [az Intune-adattárház API változási naplójának módosítása](../developer/reports-changelog.md#1903-part-2).

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>A biztonsági alapterv állapotának figyelése (nyilvános előzetes verzió) <!-- 3082047 --> 
A biztonsági alapkonfigurációk figyeléséhez egy [kategóriánkénti nézetet](../protect/security-baselines-monitor.md#per-category-view) adtunk hozzá. (A biztonsági alapkonfigurációk az előzetes verzióban maradnak). A kategóriánkénti nézet az alaptervből származó összes kategóriát jeleníti meg, valamint az adott kategóriába tartozó egyes állapotüzenetek alá tartozó eszközök százalékos arányát. Most már láthatja, hogy hány eszköz nem felel meg az egyes kategóriáknak, helytelenül vannak konfigurálva, vagy nem alkalmazhatók.

### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Az Apple VPP-tokenek hatókör-címkéi <!--2371886  -->
Mostantól hozzáadhat hatókör-címkéket az Apple VPP-tokenekhez. Csak az azonos hatókörű címkével rendelkező felhasználók férhetnek hozzá az Apple VPP-tokenhez az adott címkével. A jogkivonattal vásárolt VPP-alkalmazások és-e-könyvek a hatókörük címkéit öröklik. A hatókör-címkékkel kapcsolatos további információkért lásd: [RBAC és hatóköri címkék használata](scope-tags.md).







## <a name="week-of-april-1-2019"></a>2019. április 1. hét

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Frissített tanúsítvány-összekötők  <!-- ICM 113304612 -->
Az [Intune tanúsítvány-összekötőhöz és a pfx tanúsítvány-összekötőhöz](../protect/certficates-pfx-configure.md#whats-new-for-connectors)is kiadott frissítéseket a Microsoft Intunehoz. Az új kiadások számos ismert problémát javítanak.  

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Az iOS rendszerhez készült Céges portál alkalmazás felhasználói élményének frissítése <!-- 2536024 -->
Az iOS-eszközökhöz készült Céges portál alkalmazás kezdőlapja újratervezve. Ezzel a módosítással a Kezdőlap jobban követheti az iOS felhasználói felületének mintáit, és jobb felderíthetővé teheti az alkalmazásokat és az e-könyveket.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Az iOS 12 eszköz felhasználóinak Céges portál regisztrációjának módosításai <!--3448635 -->  
Az iOS-es beléptetési képernyők és lépések Céges portál frissült az Apple iOS 12,2-ben kiadott MDM-regisztráció módosításaival. A frissített munkafolyamat a következőket kéri a felhasználóktól:  

* A Céges portál webhely megnyitásának engedélyezése a Safari számára, és a Céges portál alkalmazásba való visszatérés előtt töltse le a felügyeleti profilt.  
* A beállítások alkalmazás megnyitásával telepítse a felügyeleti profilt az eszközére.
* A regisztráció befejezéséhez térjen vissza a Céges portál alkalmazáshoz.  

A regisztrációs lépések és képernyők frissítésével kapcsolatban lásd: [IOS-eszköz regisztrálása az Intune-ban](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).  

## <a name="week-of-march-25-2019"></a>2019. március 25-i hét

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>A Power BI megfelelőségi alkalmazás támogatása az adattárház paneljén Microsoft Intune <!-- 4260871 -->
Korábban a **letöltés Power bi fájl** hivatkozás az Intune- **adattárház** panelen letöltött egy Intune-adattárház-jelentést (. pbix fájl). Ezt a jelentést a Power BI megfelelőségi alkalmazás váltotta fel. A Power BI megfelelőségi alkalmazás nem igényel speciális betöltést vagy beállítást. Közvetlenül a Power BI online portálon nyílik meg, és a hitelesítő adatai alapján kifejezetten az Intune-bérlő adatait jeleníti meg. Az Intune-ban kattintson az Intune- **adattárház beállítása** hivatkozásra az Intune panel jobb oldalán. Ezután kattintson az **Power bi alkalmazás beolvasása**elemre. További információ: [Kapcsolódás az Adattárházhoz Power bi használatával](../developer/reports-proc-get-a-link-powerbi.md).

## <a name="week-of-march-18-2019"></a>2019. március 18. hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>A Microsoft Visio és a Microsoft Project üzembe helyezése <!-- 3725386  -->
Most már telepítheti a Microsoft Visio Pro for Office 365 és a Microsoft Project online asztali ügyfelet független alkalmazásként Windows 10-es eszközökre Microsoft Intune használatával, ha ezekhez az alkalmazásokhoz saját licence van. Az Intune-ból válassza a **Client apps** > **alkalmazások** > **Hozzáadás** elemet az **alkalmazás hozzáadása** panel megjelenítéséhez. Az **alkalmazás hozzáadása** panelen válassza a **Windows 10** lehetőséget az **alkalmazás típusaként**. Ezután válassza az **alkalmazáscsomag konfigurálása** elemet a telepítendő alkalmazások kiválasztásához. További információ a Windows 10-es eszközök Office 365-alkalmazásairól: [office 365-alkalmazások kiosztása Windows 10-es eszközökhöz Microsoft Intune használatával](../apps/apps-add-office365.md).

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Microsoft Visio Pro for Office 365 terméknév változása <!-- 3593653  -->
**A Microsoft Visio Pro for Office 365** mostantól a **Microsoft Visio online 2. csomagjának**lesz a neve.  A Microsoft Visio szolgáltatással kapcsolatos további információkért lásd: [Visio online 2. csomag](https://products.office.com/visio/visio-online-plan-2). További információ a Windows 10-es eszközök Office 365-alkalmazásairól: [office 365-alkalmazások kiosztása Windows 10-es eszközökhöz Microsoft Intune használatával](../apps/apps-add-office365.md).

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Az Intune app Protection-szabályzat (alkalmazás) karakteres korlátjának beállítása <!-- 3291302  -->
Az Intune-rendszergazdák kivételt adhatnak meg az Intune-alkalmazás számára a **kivágási, másolási és beillesztési műveletek korlátozása más alkalmazásokkal** házirend-beállítással.  Rendszergazdaként megadhatja, hogy hány karakterből lehet kivágni vagy másolni egy felügyelt alkalmazást. Ez a beállítás lehetővé teszi a megadott számú karakter megosztását bármely alkalmazásra, a "Kivágás, másolás és beillesztés más alkalmazásokkal" beállítástól függetlenül. Vegye figyelembe, hogy az Androidhoz készült Intune Céges portál alkalmazás verziójának 5.0.4364.0 vagy újabb verziójúnak kell lennie. További információ: [iOS](../apps/app-protection-policy-settings-ios.md#data-protection)-adatvédelem, Android- [Adatvédelem](../apps/app-protection-policy-settings-android.md#data-protection)és az ügyfélalkalmazás- [védelmi naplók áttekintése](../apps/app-protection-policy-settings-log.md#app-protection-policy-settings).

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>Office Deployment Tool (ODT) XML az Office ProPlus telepítéséhez <!-- 3192477   -->
Az Office Pro Plus egy példányának létrehozásakor az Intune felügyeleti konzolján megadhatja az Office Deployment Tool (ODT) XML-t. Ez nagyobb testreszabhatóság lehetővé tétele, ha a meglévő Intune felhasználói felületi lehetőségek nem felelnek meg az igényeinek. További információ: [office 365-alkalmazások kiosztása Windows 10-es eszközökhöz Microsoft Intune](../apps/apps-add-office365.md) és [konfigurációs beállításokkal az Office-telepítő eszközhöz](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>Az alkalmazás ikonjai ekkor automatikusan generált háttérrel jelennek meg <!-- 1429026  -->
A Windows Céges portál alkalmazásban az alkalmazás ikonjai mostantól automatikusan generált háttérrel jelennek meg az ikon domináns színe alapján (ha ez észlelhető). Ha alkalmazható, ez a háttér azt a szürke szegélyt váltja fel, amely korábban már látható az alkalmazás csempén. A felhasználók ezt a változást a Céges portál későbbi verzióiban fogják látni a 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Elérhető alkalmazások telepítése a Céges portál alkalmazással a Windows tömeges beléptetése után <!-- 2751523   -->
Azok a Windows-eszközök, amelyek az Intune-ba regisztrált [Windows csoportos beléptetéssel](../enrollment/windows-bulk-enroll.md) (kiépítési csomagokkal) a céges portál alkalmazás használatával telepíthetik az elérhető alkalmazásokat. A Céges portál alkalmazással kapcsolatos további információkért lásd: [a Windows 10 céges portál manuális hozzáadása](../apps/store-apps-company-portal-app.md) és [az Microsoft Intune céges portál alkalmazás konfigurálása](../apps/company-portal-app.md).

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>A Microsoft Teams alkalmazás az Office App Suite részeként is kiválasztható <!-- 3828932  -->
A Microsoft Teams alkalmazás az Office Pro Plus App Suite telepítésének részeként is beépíthető vagy kizárható. Ez a funkció az Office Pro Plus Build Number 16.0.11328.20116 + csomaggal működik. A felhasználónak ki kell jelentkeznie, majd be kell jelentkeznie az eszközre a telepítés befejezéséhez. Az Intune-ban válassza a **Client apps** > **alkalmazások** > **Hozzáadás**elemet. Válassza ki az **Office 365 Suite** -alkalmazások egyikét, majd válassza az **App Suite konfigurálása**lehetőséget.

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Alkalmazás automatikus elindítása, ha a Windows 10 és újabb rendszerű eszközökön több alkalmazást futtat kioszk módban <!-- 2351390 -->

Windows 10 és újabb rendszerű eszközökön az eszközt teljes képernyős módban futtathatja, és számos alkalmazást futtathat. Ebben a frissítésben van egy automatikus **indítási** beállítás (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **Windows 10 és újabb verziók** a platform > **kioszk** számára a profil típusaként >  **Többalkalmazásos kioszk**). Ezzel a beállítással automatikusan elindíthat egy alkalmazást, amikor a felhasználó bejelentkezik az eszközre.

A teljes képernyős beállítások listájának és leírásának megtekintéséhez lásd: a [Windows 10 és újabb rendszerű eszközök beállításai, amelyek kioszkként futnak az Intune-ban](../configuration/kiosk-settings-windows.md).

A Windows 10 és újabb verziókra vonatkozik

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Az operatív naplók a nem megfelelő eszközök részleteit is mutatják <!-- 4063755  -->
Amikor az Intune az Azure monitor szolgáltatásban naplózza a funkciókat, az operatív naplókat is átirányíthatja. Ebben a frissítésben az operatív naplók a nem megfelelő eszközökről is biztosítanak információkat. 

További információ erről a szolgáltatásról: [naplófájlok küldése tárolóba, Event hubokba vagy log analyticsbe az Intune-ban](../review-logs-using-azure-monitor.md).

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Naplók átirányítása Azure Monitorre több Intune-beli számítási feladatban <!-- 3804627 -->
Az Intune-ban átirányíthatja a naplózási és működési naplókat az események hubokba, a Storage-ba és a log analyticsbe Azure Monitor (**Intune**  > **monitoring**  > **diagnosztikai beállítások**). Ebben a frissítésben ezeket a naplókat több Intune-beli számítási feladatban is átirányíthatja, beleértve a megfelelőséget, a konfigurációkat, az ügyfélalkalmazások és egyebeket. 

Ha többet szeretne megtudni a Azure Monitor útválasztási naplóiról, tekintse meg a [naplófájlok küldése tárolóba, az Event hubokba vagy a log analyticsbe](../review-logs-using-azure-monitor.md)című témakört.

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Mobilitási bővítmények létrehozása és használata az androidos Zebra-eszközökön az Intune-ban <!-- 3305880   -->
Ebben a frissítésben az Intune támogatja az androidos Zebra-eszközök konfigurálását. Pontosabban létrehozhat egy eszköz konfigurációs profilt, és beállításokat alkalmazhat az Android Zebra-eszközökre a StageNow által generált mobilitási bővítmények (az**eszköz konfigurációja** > **profilok** > **profil létrehozása**  > **Android** for platform > **MX-profil (csak Zebra)** a profil típusa esetén).

A szolgáltatással kapcsolatos további információkért lásd: a [Zebra-eszközök használata és kezelése a mobilitási bővítményekkel az Intune-ban](../configuration/android-zebra-mx-overview.md).

A következőkre vonatkozik: Android

### <a name="device-management"></a>Eszközkezelés

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Titkosítási jelentés Windows 10-es eszközökhöz (nyilvános előzetes verzió)<!-- 2351538 -->  
Az új [titkosítási jelentés (előzetes verzió)](../protect/encryption-monitor.md) használatával megtekintheti a Windows 10-es eszközök titkosítási állapotának részleteit. Az elérhető részletek közé tartozik az eszközök TPM-verziója, a titkosítás készültsége és az állapot, a hibajelentés és egyebek.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Hozzáférés a BitLocker helyreállítási kulcsaihoz az Intune-portálon (nyilvános előzetes verzió) <!-- 2351547   -->  
Mostantól az Intune-nal is [megtekintheti](../protect/encryption-monitor.md) a BitLocker-kulcs azonosítóját és a BitLocker helyreállítási kulcsait a Azure Active Directoryból.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Microsoft Edge-támogatás az Intune-forgatókönyvekhez iOS-és Android-eszközökön <!-- 3411007 -->
A Microsoft Edge minden olyan felügyeleti forgatókönyvet támogat, mint a Intune Managed Browser a végfelhasználói élmény fokozása mellett. Az Intune-szabályzatok által engedélyezett Microsoft Edge Enterprise-funkciók közé tartozik a kettős identitás, az alkalmazás-védelmi házirendek integrációja, az Azure alkalmazásproxy-integráció, valamint a felügyelt kedvencek és a Kezdőlap parancsikonjai. További információ: [Microsoft Edge-támogatás](../apps/app-configuration-managed-browser.md#microsoft-edge-support).

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Az Exchange Online/Intune-összekötő elavult csak EAS-eszközök támogatása <!--3105122  -->
Az Intune-konzol már nem támogatja az Exchange Online-hoz az Intune-összekötővel csatlakoztatott EAS-eszközök megtekintését és felügyeletét. Ehelyett a következő lehetőségek közül választhat:
- Eszközök regisztrálása a mobileszköz-felügyeletben (MDM)
- Intune App Protection szabályzatok használata az eszközök kezeléséhez
- Exchange-vezérlők használata az [ügyfelek és a mobil Exchange Online-](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) ban vázolt módon

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>A [név] használatával keresse meg a pontos eszköz minden eszköz lapját. <!--4254930 -->
Most már megkeresheti az eszköznév pontos nevét. Nyissa meg az **Intune** > **eszközt** > **minden eszköz** > a keresőmezőbe, és az eszköz nevét a {} értékkel megkeresve keresse meg a pontos egyezést. Például: **{Device12345}** .

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>További összekötők támogatása a bérlő állapota lapon <!-- 3617202  -->
A [bérlő állapota lap](../tenant-status.md) ekkor megjeleníti a további összekötők állapotinformációkat, beleértve a *Windows Defender komplex veszélyforrások elleni védelmet* (ATP) és más Mobile Threat Defense-összekötőket.

### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Az Intune írásvédett hozzáférésének biztosítása néhány Azure Active Directory szerepkörhöz <!-- 3637917  -->
Az Intune írásvédett hozzáférése a következő Azure AD-szerepkörökhöz lett megadva. Az Azure AD-szerepkörökhöz megadott engedélyek felülírják az Intune szerepköralapú hozzáférés-vezérléssel (RBAC) biztosított engedélyeket.

Írásvédett hozzáférés az Intune-beli naplózási információkhoz:

- Megfelelőségi rendszergazda
- Megfelelőségi adatkezelő

Olvasási hozzáférés az összes Intune-adattal:

- Biztonsági rendszergazda
- Biztonsági operátor
- Biztonsági olvasó

További információ: [szerepköralapú hozzáférés-vezérlés](role-based-access-control.md).

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>A hatókör címkéi az iOS-alkalmazások létesítési profiljaihoz <!--2934430   -->
Hozzáadhat egy hatóköri címkét egy iOS-alkalmazás létesítési profiljához, így csak a szerepkörökhöz hozzárendelt felhasználók férhetnek hozzá az iOS-alkalmazások létesítési profiljához. További információ: [RBAC és hatókör-címkék használata](scope-tags.md).

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Alkalmazás-konfigurációs házirendek hatókör-címkéi <!--2371891   -->
Hatókör-címkét adhat hozzá egy alkalmazás-konfigurációs házirendhez, így csak a szerepkörökhöz hozzárendelt felhasználók férhetnek hozzá az alkalmazás konfigurációs házirendjéhez. Az alkalmazás-konfigurációs házirend csak az ugyanahhoz a hatóköri címkéhez hozzárendelt alkalmazásokhoz célozható vagy társítható. További információ: [RBAC és hatókör-címkék használata](scope-tags.md).

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Microsoft Edge-támogatás az Intune-forgatókönyvekhez iOS-és Android-eszközökön <!-- 3411007 -->
A Microsoft Edge minden olyan felügyeleti forgatókönyvet támogat, mint a Intune Managed Browser a végfelhasználói élmény fokozása mellett. Az Intune-szabályzatok által engedélyezett Microsoft Edge Enterprise-funkciók közé tartozik a kettős identitás, az alkalmazás-védelmi házirendek integrációja, az Azure alkalmazásproxy-integráció, valamint a felügyelt kedvencek és a Kezdőlap parancsikonjai. További információ: [Microsoft Edge-támogatás](../apps/app-configuration-managed-browser.md#microsoft-edge-support).

## <a name="week-of-february-25-2019"></a>2019. február 25-i hét

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="intune-powershell-module----951068----"></a>Intune PowerShell-modul <!-- 951068  -->
Az Intune PowerShell-modul, amely a Microsoft Graphon keresztül támogatja az Intune API-t, mostantól elérhető a [Microsoft PowerShell-Galéria](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [A modul használatának részletei](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Példa a modult használó forgatókönyvekre](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Továbbfejlesztett támogatás a kézbesítés optimalizálásához  <!--3183757  -->
Kibővítettük az Intune támogatását a kézbesítés optimalizálásának konfigurálásához. Mostantól az Intune-konzolról is konfigurálhatja a [kézbesítési optimalizálási beállítások](../configuration/delivery-optimization-settings.md) kibontott listáját, és megcélozhatja azokat az eszközökre.


## <a name="week-of-february-18-2019"></a>2019. február 18. hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Az Intune kihasználja a Google Play Protect API-kat Android-eszközökön <!-- 2577355   -->
Egyes IT-rendszergazdák egy BYOD-környezettel szembesülnek, ahol a végfelhasználók felhasználhatják a begyökerező vagy a mobiltelefonról érkező felhasználókat. Ez a viselkedés, miközben néha nem szándékosan van kipróbálva, a rendszer számos olyan Intune-szabályzat megkerülését eredményezi, amely a szervezet végfelhasználói eszközökön tárolt adatainak védelme érdekében be van állítva. Így az Intune a regisztrált és a nem regisztrált eszközök gyökerét és szökik észlelését is lehetővé teszi. Ebben a kiadásban az Intune mostantól kihasználja a Google Play Protect API-kat, hogy hozzáadja a meglévő gyökérszintű észlelési ellenőrzésekhez a nem regisztrált eszközökhöz. Míg a Google nem osztja meg a legfelső szintű észlelési ellenőrzéseket, az API-k elvárják, hogy észlelni tudják az eszközeiket az eszköz testreszabásával kapcsolatban, hogy az operációs rendszer újabb frissítései a régebbi eszközökön legyenek leképezve. Ezek a felhasználók Ezután letilthatja a vállalati adatok elérését, vagy a vállalati fiókjaikat a szabályzattal kompatibilis alkalmazásokból is törölhetik. További érték esetén a rendszergazda mostantól több jelentéskészítési frissítést is tartalmaz a Intune App Protection panelen – a "megjelölt felhasználók" jelentés megmutatja, hogy mely felhasználók észlelhetők a Google Play Protect biztonság API-vizsgálatán keresztül, a "potenciálisan ártalmas alkalmazások" jelentés Megjeleníti, hogy mely alkalmazások észlelhetők a Google ellenőrzési alkalmazások API-vizsgálatán keresztül. Ez a funkció Androidon érhető el.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>A Win32-alkalmazások információi a Hibaelhárítás panelen érhetők el <!-- 2617342   -->
Mostantól az Intune-alkalmazások **hibaelhárítási** paneljén is gyűjthet egy Win32-alkalmazás telepítésének sikertelen naplófájljait. Az alkalmazások telepítésével kapcsolatos hibaelhárítással kapcsolatos további információkért lásd: az [alkalmazások telepítésével kapcsolatos problémák elhárítása](./../apps/troubleshoot-app-install.md) és a Win32-alkalmazások hibáinak [elhárítása](./../apps/troubleshoot-app-install.md#win32-app-installation-troubleshooting).

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Alkalmazások állapotának részletei iOS-alkalmazásokhoz <!-- 3761235   -->
A következőhöz kapcsolódó új alkalmazás-telepítési hibaüzenetek találhatók:
- Nem sikerült a VPP-alkalmazások megosztott iPadre való telepítésekor
- Hiba az App Store letiltásakor
- Nem található a VPP-licenc az alkalmazáshoz
- Nem sikerült telepíteni a rendszeralkalmazásokat a MDM Provider szolgáltatással
- Nem sikerült telepíteni az alkalmazásokat, ha az eszköz elveszett vagy teljes képernyős módban van
- Nem sikerült telepíteni az alkalmazást, ha a felhasználó nincs bejelentkezve az App Store-ba

Az Intune-ban válassza a **Client apps** > **alkalmazások** > "alkalmazás neve" > **eszköz telepítési állapota**lehetőséget. Az új hibaüzenetek az **állapot részletei** oszlopban lesznek elérhetők.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Új alkalmazás-kategóriák képernyő a Windows 10-es Céges portál alkalmazásban<!-- 3834780  -->
Az alkalmazás- **Kategóriák** nevű új képernyő lett hozzáadva az alkalmazások böngészési és kiválasztási élményének javításához a Windows 10-es céges portál. A felhasználók mostantól a **Kiemelt**, az **oktatási**és a **termelékenység**kategóriák szerint rendezve láthatják az alkalmazásaikat. Ez a módosítás Céges portál 10.3.3451.0 és újabb verziókban jelenik meg. Az új képernyő megtekintéséhez tekintse [meg az alkalmazás felhasználói felületének újdonságai](whats-new-app-ui.md)című témakört. A Céges portál alkalmazásokkal kapcsolatos további információkért lásd: [alkalmazások telepítése és megosztása az eszközön](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Megfelelőségi alkalmazás Power BI <!-- 1455231 doc-work-item -->
Az Intune [megfelelőségi (adattárház-)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) alkalmazásával érheti el az Intune-adattárházat Power bi online-ban. Ezzel a Power BI alkalmazással mostantól a telepítés nélkül is elérheti és megoszthatja az előre létrehozott jelentéseket anélkül, hogy a böngészőt el kellene hagynia. További információkért lásd: a [log-Power bi megfelelőségi alkalmazás módosítása](../developer/reports-changelog.md#power-bi-compliance-app).


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>A PowerShell-parancsfájlok 64 bites gazdagépen futtathatók 64 bites eszközökön <!-- 1862675   -->
Ha egy PowerShell-parancsfájlt ad hozzá egy eszköz konfigurációs profiljához, a parancsfájl a 32 bites verzióban, még a 64 bites operációs rendszereken is végrehajtja. Ezzel a frissítéssel a rendszergazda a 64 bites PowerShell-gazdagépen futtathatja a szkriptet a 64 bites eszközökön (az**eszköz konfigurációja**  > **powershell-parancsfájlok**  > **Hozzáadás**  > **konfigurálása**  > **futtatási parancsfájl 64 bites verzióban PowerShell-gazdagép**).

A PowerShell használatával kapcsolatos további információkért lásd: [PowerShell-parancsfájlok az Intune-ban](../apps/intune-management-extension.md).

A Windows 10 és újabb verziókra vonatkozik

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>a macOS-felhasználók a jelszavuk frissítésére kérik <!-- 1873216 -->
Az Intune a macOS-eszközök **ChangeAtNextAuth** beállítását érvényesíti. Ez a beállítás hatással van a végfelhasználók és az eszközök megfelelőségi jelszavas szabályzatokkal vagy az eszköz korlátozási jelszavas profiljaival. A rendszer egyszer kéri a végfelhasználókat a jelszavuk frissítésére. Ez akkor fordul elő, amikor egy felhasználó először futtat egy hitelesítést igénylő feladatot, például bejelentkezik az eszközre. A felhasználókat arra is kérheti, hogy a rendszergazdai jogosultságokat igénylő bármit, például a kulcstartók elérésének kérésével frissítse a jelszavát. 

A rendszergazda által megjelenő új vagy meglévő jelszóházirend-módosítások ismét frissítik a jelszavukat.

A következőkre vonatkozik:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521------"></a>SCEP-tanúsítványok társítása egy felhasználó nélküli macOS-eszközhöz    <!-- 2340521    -->
Egyszerű tanúsítványigénylési protokoll (SCEP) tanúsítványokat a macOS-eszközökhöz, például a felhasználói affinitás nélküli eszközökhöz, valamint a tanúsítvány profiljának a Wi-Fi-vagy VPN-profilokhoz való társításához rendelhet hozzá. Ez kibővíti azt a támogatást, amelyhez már hozzá van rendelve a SCEP-tanúsítványok a Windows, iOS és Android rendszerű [felhasználói affinitással rendelkező és azok nélküli eszközökhöz](../protect/certificates-profile-scep.md) .  Ezzel a frissítéssel kiválaszthatja az *eszköz* SCEP, ha a MacOS-hez konfigurálja a tanúsítvány-profilt.

A következőkre vonatkozik: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Intune feltételes hozzáférés felhasználói felületének frissítése   <!-- 2432313   -->
Javítottuk a feltételes hozzáférés felhasználói felületét az Intune-konzolon. Ezek a következők:
- Lecserélte az Intune *feltételes hozzáférés* paneljét Azure Active Directoryról a panelre. Ez biztosítja, hogy a [feltételes hozzáférés](../protect/conditional-access.md) összes beállítását és konfigurációját (amely egy Azure ad-technológia marad) az Intune-konzolon belülről elérheti. 
- Átnevezte a helyszíni *hozzáférés* panelt az *Exchange-hozzáférésre*, és áthelyezte az *Exchange Service Connector* telepítőjét erre az átnevezett panelre.  Ez a változás összevonja az [Exchange Online-hoz és a helyszíni környezethez kapcsolódó részletek konfigurálásának és figyelésének](../protect/exchange-connector-install.md)helyét.  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>A teljes képernyős böngésző és a Microsoft Edge böngésző alkalmazásai a Windows 10-es eszközökön is futtathatók a kioszk módban <!-- 2935135   -->
A Windows 10-es eszközök teljes képernyős módban futtathatók egy alkalmazás vagy számos alkalmazás futtatásához. Ez a frissítés több módosítást is tartalmaz a böngészőbeli alkalmazások teljes képernyős módban való használatával, beleértve a következőket:

- Adja hozzá a Microsoft Edge böngészőt vagy a kioszk böngészőt a kioszk eszközön futó alkalmazások futtatásához (**eszköz-konfiguráció**  > **profilok**  > **új profil**  > **Windows 10 és újabb verziók** a platform > **kioszk** a profil típusa ).
- Új funkciók és beállítások érhetők el az engedélyezéshez vagy a korlátozáshoz (**Device configuration** > **profilok** > **új profil** > **Windows 10 és újabb verziók** a platform > **eszköz korlátozásai** a profil típusa esetén), beleértve

- Microsoft Edge böngésző:
  - A Microsoft Edge kioszk mód használata
  - Böngésző frissítése üresjárati idő után

- Kedvencek és keresés:
  - Keresőmotor módosításának engedélyezése

A beállítások listáját a következő témakörben tekintheti meg:

- [A Windows 10 és újabb rendszerű eszközök beállításai kioszkként való futtatásra](../configuration/kiosk-settings-windows.md)
- [Microsoft Edge böngésző eszköz korlátozásai](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)
- [Kedvencek és keresési eszközre vonatkozó korlátozások](../configuration/device-restrictions-windows-10.md##favorites-and-search)

A Windows 10 és újabb verziókra vonatkozik

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Az iOS-és macOS-eszközök új eszköz-korlátozási beállításai <!-- 3448774   -->
Az iOS és macOS rendszerű eszközökön bizonyos beállításokat és szolgáltatásokat korlátozhat (az**eszköz konfigurációs**  > **profiljai**  > **új profil**  > **iOS** vagy **MacOS** platformra > **eszköz korlátozásai** a profil típusa). Ez a frissítés további funkciókat és beállításokat tartalmaz, amelyekkel szabályozható, például a képernyő időpontjának beállítása, a eSIM-beállítások és a mobil csomagok módosítása, valamint az iOS-eszközökön található további beállítások. Emellett a felhasználók a szoftverfrissítések láthatóságát, valamint a tartalom gyorsítótárazásának a macOS-eszközökön való blokkolását is késleltetheti. 

A korlátozni kívánt funkciók és beállítások megtekintéséhez tekintse meg a következőt:

- [iOS-eszközök korlátozási beállításai](../configuration/device-restrictions-ios.md)
- [macOS-eszköz korlátozási beállításai](../configuration/device-restrictions-macos.md)

A következőkre vonatkozik:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>A "kioszk" eszközök mostantól "dedikált eszközök" néven jelennek meg az Android Enterprise-eszközökön <!-- 3598402   -->
Az Android-terminológiához való igazításhoz a **kioszkot** az Android Enterprise-eszközökhöz készült **dedikált eszközökre** változtatja (**eszköz konfigurációja** > **profil** > **profil létrehozása** > * * Android Enterprise for platform > **Eszköz tulajdonosának csak** > **eszköz korlátozása**0**dedikált eszköz**).

Az elérhető beállítások megtekintéséhez válassza az [eszközbeállítások lehetőséget a funkciók engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

A következőkre vonatkozik:  
Vállalati Android

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>A Safari és a késleltetés a felhasználó szoftverfrissítés láthatósága iOS-beállítások az Intune felhasználói felületén lesznek áthelyezve <!-- 3640850, 3803313   -->
IOS-eszközök esetén a Safari beállításait és a szoftverfrissítések konfigurálását is megadhatja. Ebben a frissítésben ezeket a beállításokat az Intune felhasználói felületének különböző részeire helyezi át:

- A **Safari (** **eszköz konfigurációja** > **profilok** > **új profil** > **iOS** a platform > **eszközre vonatkozó korlátozásai** a profil típusa esetén) a **[beépített alkalmazások](../configuration/device-restrictions-ios.md#built-in-apps)** számára lettek áthelyezve.
- A **felügyelt iOS-eszközökre** vonatkozó (a**szoftverfrissítések**  >  iOS-re vonatkozó**frissítési szabályzatok**) felhasználói szoftverfrissítés láthatósága az **eszközök korlátozásait**  >  **[általános](../configuration/device-restrictions-ios.md#general)** .  További információ a meglévő szabályzatok hatásáról: [iOS-szoftverfrissítések](../protect/software-updates-ios.md#configure-the-policy). 

A beállítások listáját a következő témakörben tekintheti meg:

- [iOS-eszközök korlátozásai](../configuration/device-restrictions-ios.md) 
- [iOS-szoftverfrissítések](../protect/software-updates-ios.md)

Ez a funkció az alábbiakra vonatkozik: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>Az eszközbeállítások korlátozásait a rendszer az iOS-eszközökön a képernyő időpontjára átnevezi <!-- 3699164   -->
Konfigurálhatja a **korlátozásokat a** felügyelt iOS-eszközök beállításainál (**eszköz konfigurációja** > **profilok** > **új profil** > **iOS** a platform > **eszközhöz** a profil típusának korlátozásai > **általános**). Ebben a frissítésben ezt a beállítást a rendszer a **képernyő időpontjára nevezi át (csak felügyelt**eszköz esetén). 

A viselkedés ugyanaz. Kifejezetten 

- iOS-11.4.1 és korábbi verziók: a **Letiltás** megakadályozza, hogy a végfelhasználók saját korlátozásokat állítsanak be az eszközbeállítások között. 
- iOS 12,0 és újabb verziók: a **Letiltás** megakadályozza, hogy a végfelhasználók saját **képernyős időt** állítsanak be az eszközbeállítások során, beleértve a tartalmakat & adatvédelmi korlátozásokat. Az iOS 12,0-re frissített eszközök többé nem látják a korlátozások lapot az eszközbeállítások lapon. Ezek a beállítások a **képernyőn**jelennek meg. 

A beállítások listáját az [iOS-eszközök korlátozásai](../configuration/device-restrictions-ios.md#general)című témakörben tekintheti meg.

A következőkre vonatkozik: 
- iOS


### <a name="device-management"></a>Eszközkezelés

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>Regisztrált Windows-eszköz átnevezése <!-- 1911112  -->
Most már átnevezheti a regisztrált Windows 10-es eszközöket (RS4 vagy újabb). Ehhez válassza az **Intune**  > **eszközök**  > **minden eszköz** lehetőséget, > válasszon ki egy eszközt > **átnevezése eszközre**. Ez a funkció jelenleg nem támogatja a hibrid Azure AD Windows-eszközök átnevezését.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Hatókör-címkék automatikus társítása az adott hatókörrel rendelkező rendszergazda által létrehozott erőforrásokhoz <!-- 3173823  -->
Amikor egy rendszergazda létrehoz egy erőforrást, a rendszergazda számára rendelt összes hatókör-címke automatikusan hozzá lesz rendelve az új erőforrásokhoz.

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Sikertelen beléptetési jelentés az eszközök beléptetése panelre <!-- 3560202  -->
A **sikertelen regisztrációk** jelentés át lett helyezve az **eszközök beléptetése** panel **figyelő** szakaszába. Két új oszlop (regisztrációs módszer és operációsrendszer-verzió) lett hozzáadva.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>Céges portál a lemondás jelentés átnevezve hiányos felhasználói regisztrációra <!--3815076 eemiss -->
A **céges portál-megszakítási** jelentés átnevezve **hiányos felhasználói regisztrációra**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>2019. február 4. hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Intune macOS Céges portál sötét üzemmód <!-- 3300524  -->
Az Intune macOS Céges portál mostantól támogatja a sötét üzemmódot macOS rendszeren. Ha egy macOS 10.14 + eszközön engedélyezi a sötét üzemmódot, a Céges portál az adott üzemmódot tükröző színekre módosítja a megjelenését.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>2019. január 21. hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Bejelentési értesítések a Win32-alkalmazásokhoz <!-- 3136566   -->
A végfelhasználói bejelentési értesítések megjelenítése az alkalmazás-hozzárendelések esetében letiltható. Az Intune-ból válassza az **ügyfélalkalmazások** > **alkalmazások** lehetőséget > válassza ki az alkalmazást > **hozzárendelések** > **csoportok belefoglalása**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Az Intune app Protection-szabályzatok felhasználói felületének frissítése <!-- 3251427  -->
Módosítottuk az Intune app Protection beállításainak és gombjainak feliratait, hogy könnyebben érthetőek legyenek. A módosítások némelyike a következőkből áll:  
- A vezérlőelemek az **igen** /  értékről változnak, így **elsődlegesen** **nem** lehet letiltani a  / **engedélyezését** és **letiltását** / **enable** vezérlőket. A címkék is frissülnek.  
- A beállítások formázva lesznek, így a beállítás és a címkéje egymás mellett, a vezérlőn belül, a jobb navigálás érdekében.   

Az alapértelmezett beállítások és a beállítások száma változatlan marad, de ez a módosítás lehetővé teszi, hogy a felhasználó könnyebben megértse, navigálja és használja a beállításokat a kiválasztott alkalmazás-védelmi szabályzatok alkalmazásához. További információ: [iOS-beállítások](../apps/app-protection-policy-settings-ios.md) és [Android-beállítások](../apps/app-protection-policy-settings-android.md).

### <a name="additional-settings-for-outlook----3301182----"></a>További beállítások az Outlookhoz <!-- 3301182  -->
Mostantól az Intune-nal az iOS-hez és az Androidhoz készült Outlook további beállításait is konfigurálhatja:

- Csak a munkahelyi vagy iskolai fiókok használatának engedélyezése az Outlookban az iOS és az Android rendszerű eszközökön
- Modern hitelesítés üzembe helyezése az Office 365-ben és a modern hibrid hitelesítés helyszíni fiókoknál
- Az egyszerű hitelesítés kiválasztásakor használja a `SAMAccountName` értéket az e-mail profil username mezőjénél
- Névjegyek mentésének engedélyezése
- Külső címzettek beállítása – levelezési tippek
- **Fókuszált beérkezett** fájlok konfigurálása
- A biometria megkövetelése az Outlook iOS-hez való hozzáféréséhez
- Külső lemezképek letiltása

> [!NOTE]
> Ha Intune App Protection házirendeket használ a vállalati identitásokhoz való hozzáférés kezelésére, érdemes megfontolnia, hogy ne engedélyezze a **biometrikus azonosítók megkövetelését**. További információ: **vállalati hitelesítő adatok megkövetelése az** [iOS-hozzáférési beállítások](../apps/app-protection-policy-settings-ios.md#access-requirements) és az [Android-hozzáférési beállítások](../apps/app-protection-policy-settings-android.md#access-requirements)eléréséhez.

További információ: [Microsoft Outlook konfigurációs beállítások](../apps/app-configuration-policies-outlook.md).

#### <a name="delete-android-enterprise-apps----1352553---"></a>Androidos vállalati alkalmazások törlése <!-- 1352553 -->
A felügyelt Google Play-alkalmazásokat törölheti Microsoft Intuneról. Felügyelt Google Play-alkalmazás törléséhez nyissa meg Microsoft Intune a Azure Portal, és válassza az **ügyfélalkalmazások** > **alkalmazások**elemet. Az alkalmazás listából válassza a felügyelt Google Play alkalmazás jobb oldalán található három pontot (...), majd válassza a **Törlés** lehetőséget a megjelenített listából. Ha töröl egy felügyelt Google Play-alkalmazást az alkalmazások listájáról, a felügyelt Google Play-alkalmazás automatikusan nem lesz jóváhagyva.

#### <a name="managed-google-play-app-type----1352580---"></a>Felügyelt Google Play-alkalmazás típusa <!-- 1352580 -->
A **felügyelt Google Play** -alkalmazás típusa lehetővé teszi a [felügyelt Google Play-alkalmazások](https://play.google.com/work/search?q=microsoft&c=apps) konkrét hozzáadását az Intune-hoz. Intune-rendszergazdaként mostantól böngészhet, kereshet, jóváhagyhatja, szinkronizálhatja és hozzárendelheti a jóváhagyott felügyelt Google Play-alkalmazásokat az Intune-on belül.  Többé nem kell külön megkeresnie a felügyelt Google Play-konzolt, és többé nem kell újrahitelesítenie.  Az Intune-ban válassza a **Client apps** > **alkalmazások** > **Hozzáadás**elemet. Az **alkalmazás típusa** listában válassza a **felügyelt Google Play** lehetőséget az alkalmazás típusa mezőben.

### <a name="default-android-pin-keyboard----3802457---"></a>Alapértelmezett androidos PIN-kód billentyűzete <!-- 3802457 -->
Azok a végfelhasználók, akik a "numerikus" PIN-kód típussal beállították az androidos eszközökön a Intune App Protection szabályzat (alkalmazás) PIN-kódját, az alapértelmezett Android-billentyűzetet fogják látni a korábban tervezett, rögzített androidos billentyűzet helyett. Ez a változás konzisztens volt az Android és az iOS alapértelmezett billentyűzetének használatakor, mind a "numerikus", mind a "PIN-kód" típusnál. További információ az Android rendszerhez készült végfelhasználói hozzáférési beállításokról, például az alkalmazás PIN-kódjáról: [Android-hozzáférési követelmények](../apps/app-protection-policy-settings-android.md#access-requirements).

### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>A Microsoft által ajánlott beállítások használata biztonsági alaptervekkel (nyilvános előzetes verzió) <!-- 2055484   -->

Az Intune integrálható más, biztonsági célú szolgáltatásokkal, például a Windows Defender ATP-vel és az Office 365 ATP-vel. Az ügyfelek a Microsoft 365-szolgáltatásokon átívelő közös stratégiát és összefüggő, teljes körű biztonsági munkafolyamatokat kérnek. Célunk a stratégiák összehangolása és ezáltal olyan megoldások létrehozása, amelyek hidat képeznek a biztonsági műveletek és a gyakori felügyeleti feladatok között. Az Intune-ban ezen cél elérésére a Microsoft által ajánlott „biztonsági előírások” közzétételével törekszünk (**Intune** > **Biztonsági előírások**).  A rendszergazda biztonsági házirendeket hozhat létre közvetlenül ezekből az alaptervekről, majd telepítheti azokat a felhasználók számára. Testre szabhatja az ajánlott eljárásokat, hogy megfeleljenek a szervezet igényeinek. Az Intune biztosítja, hogy az eszközök megfeleljenek ezeknek az előírásoknak, és értesíti a rendszergazdákat, ha egy felhasználó vagy eszköz nem felel meg.

Ez a funkció nyilvános előzetes verzióban érhető el, így a most létrehozott profilok nem kerülnek át az általánosan elérhető (GA) biztonsági alapkonfigurációs sablonokra. Ezeket az előnézeti sablonokat nem ajánlott éles környezetben használni.

További információ a biztonsági alaptervekről: [a Windows 10 biztonsági alapkonfigurációjának létrehozása az Intune-ban](../protect/security-baselines-monitor.md).

A szolgáltatás a következőre vonatkozik: Windows 10 és újabb

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>A nem rendszergazdák engedélyezhetik a BitLocker használatát az Azure AD-hez csatlakoztatott Windows 10-es eszközökön<!-- 2147379   -->
Ha engedélyezi a BitLocker beállításait a Windows 10-es eszközökön (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > **Windows 10 és újabb verzió** a platform > **Endpoint Protection** a profil típusaként > **Windows-titkosítás**) a BitLocker-beállításokat adja hozzá. 

Ez a frissítés egy új BitLocker-beállítást tartalmaz, amely lehetővé teszi, hogy az általános jogú felhasználók (nem rendszergazdák) engedélyezzék a titkosítást. 

A beállítások megjelenítéséhez nyissa meg a [Windows 10 Endpoint Protection-beállításai](../protect/endpoint-protection-windows-10.md#windows-encryption)című témakört.

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Configuration Manager megfelelőségének ellenőrzése <!-- 2192052  eepublished  -->
Ez a frissítés új System Center Configuration Manager megfelelőségi beállítást tartalmaz (**eszköz megfelelőségi** > **szabályzatok** > **házirend létrehozása** > **Windows 10 és újabb** > **Configuration Manager Megfelelőség**). A Configuration Manager megfelelőségi jeleket küldi az Intune-nak. Ezzel a beállítással megkövetelheti, hogy az összes Configuration Manager-jel "megfelelő" értéket ad vissza.

Megkövetelhető például, hogy minden szoftverfrissítés telepítve legyen az eszközökön. A Configuration Managerben az ehhez a követelményhez tartozó állapot a „Telepítve”. Ha az eszközön bármely program ismeretlen állapotban van, akkor az eszköz nem megfelelő az Intune-ban.

A [Configuration Manager megfelelősége](../protect/compliance-policy-create-windows.md#configuration-manager-compliance) ezt a beállítást ismerteti.

A Windows 10 és újabb verziókra vonatkozik

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Háttérkép testreszabása felügyelt iOS-eszközökön az eszköz konfigurációs profiljának használatával <!-- 2809324   -->
Az iOS-eszközökhöz készült konfigurációs profil létrehozásakor testre szabhatja bizonyos funkciókat (**eszköz konfigurációja** > **profilok** > **create Profile** > **iOS** for platform > **eszköz funkciói** a profil típusa). Ez a frissítés új **tapéta** -beállításokat tartalmaz, amelyek lehetővé teszik, hogy a rendszergazda. png,. jpg vagy. jpeg képet használjon a kezdőképernyőn vagy a zárolási képernyőn. Ezek a háttérkép-beállítások csak a felügyelt eszközökre érvényesek. 

A beállítások listájáért lásd: iOS- [eszköz funkciójának beállításai](../configuration/ios-device-features-settings.md).

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Általánosan elérhető a Windows 10 kioszk <!-- 3594661  -->
Ebben a frissítésben a Windows 10-es és újabb rendszerű eszközökön a kioszk funkció általánosan elérhető (GA). Az összes felvehető és konfigurálható beállítás megjelenítéséhez tekintse meg a [Windows 10-es (és újabb) kioszk-beállítások](../configuration/kiosk-settings.md)című témakört.

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>A névjegyek Bluetooth-kapcsolaton keresztüli megosztása el lesz távolítva az eszköz-korlátozásokkal > Android Enterprise-eszköz tulajdonosa <!-- 3598396   -->
Ha az androidos vállalati eszközökhöz hoz létre egy eszköz-korlátozási profilt, a rendszer **Bluetooth-kapcsolaton keresztül megosztja a partneri kapcsolatot** . Ebben a frissítésben a **névjegyek Bluetooth-kapcsolaton keresztüli megosztása** el lesz távolítva (**eszköz konfigurációja** > **Profiles** > **profil létrehozása** > **Android Enterprise** for platform > **eszköz korlátozásai > Eszköz tulajdonosa** a profil típusa > **általános**). 

Az androidos vállalati eszközök tulajdonosi felügyelete nem támogatja a **névjegyek Bluetooth-kapcsolaton keresztüli** beállítását. Így ha eltávolítja ezt a beállítást, az nem érinti az eszközöket és a bérlőket, még akkor sem, ha ez a beállítás engedélyezve van és konfigurálva van a környezetben.

A beállítások aktuális listájának megtekintéséhez lépjen az [Android Enterprise-eszköz beállításai lehetőségre a funkciók engedélyezéséhez vagy korlátozásához](../configuration/device-restrictions-android-for-work.md).

A következőkre vonatkozik: Android Enterprise-eszköz tulajdonosa

### <a name="device-management"></a>Eszközkezelés

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Szelektív törlés támogatása beléptetési eszközök nélkül <!-- 1434452 -->
A Windows Information Protection regisztráció nélkül (folyamatban lévő – mi) lehetővé teszi, hogy az ügyfelek teljes MDM-regisztráció nélkül védjék a vállalati adataikat a Windows 10-es eszközökön. Ha a dokumentumok egy BEFEJEZetlen munkaterheléssel védettek, a védett adatok szelektíven törölhetők egy Intune-rendszergazda által. A felhasználó és az eszköz kiválasztásával, valamint a törlési kérelem elküldésével az összes, a folyamatban lévő munkaterületen keresztül védett adat használhatatlanná válik. Ehhez az Azure Portal Intune részén válassza a **Mobilalkalmazás** > **Alkalmazás szelektív törlése** lehetőséget.

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Új operatív naplók, és naplók küldésének lehetősége Azure Monitor szolgáltatásokba <!-- 3762211  -->
Az Intune beépített naplózási naplózással rendelkezik, amely nyomon követi az eseményeket. Ez a frissítés új naplózási funkciókat tartalmaz, beleértve a következőket: 
- Működési naplók (előzetes verzió), amelyek a regisztrált felhasználókra és eszközökre vonatkozó adatokat jelenítik meg, beleértve a sikeres és sikertelen kísérleteket.
- A naplók és az operatív naplók a Azure Monitorba küldhetők, beleértve a Storage-fiókokat, az Event hubokat és a log Analytics-t is. Ezek a szolgáltatások lehetővé teszik az olyan elemzések tárolását, mint például a splunk és a QRadar, valamint a naplózási adataik vizualizációinak beolvasása.

A [naplózási adatok elküldése a tárolóba, az Event hubokba vagy a log analyticsbe az Intune-ban](../review-logs-using-azure-monitor.md) további információk jelennek meg a szolgáltatással kapcsolatban.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>További beállítási asszisztens képernyők kihagyása iOS DEP-eszközön <!-- 2687509  -->
A jelenleg kihagyható képernyők mellett beállíthatja, hogy az iOS DEP-eszközök az alábbi képernyőket is kihagyják a beállítási Asszisztensben, amikor egy felhasználó regisztrálja az eszközt: hangjelzés, adatvédelem, Android-áttelepítés, Kezdőlap gomb, iMessage & FaceTime, előkészítés, megtekintés Áttelepítés, megjelenés, képernyő időpontja, szoftverfrissítés, SIM-beállítás.
A kihagyni kívánt képernyők kiválasztásához nyissa meg az **eszközök**beléptetése  > **Apple-regisztráció** > **beléptetési program jogkivonatait** > válassza ki a token > **profiljait** > válasszon egy profilt > **Tulajdonságok** > **telepítő Asszisztens testreszabása** > válassza az **Elrejtés** lehetőséget minden olyan képernyő esetében, amelyet ki szeretne hagyni > **az OK gombra**.
Ha új profilt hoz létre vagy szerkeszt egy profilt, a kijelölt kihagyási képernyőknek szinkronizálnia kell az Apple MDM-kiszolgálóval. A felhasználók manuálisan is szinkronizálhatják az eszközöket, így nincs késés a profil módosításainak felvételekor.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise-alkalmazás – alkalmazás üzembe helyezése <!-- 1171203 -->
A nem regisztrált app Protection-szabályzatok (APP-WE) üzembe helyezési forgatókönyve nélküli Android-eszközök esetén a felügyelt Google Play használatával telepítheti az áruházbeli alkalmazásokat és ÜZLETÁGI alkalmazásokat a felhasználók számára. Pontosabban megadhatja a végfelhasználók számára egy olyan alkalmazás-katalógust és telepítési folyamatot, amely már nem igényli a végfelhasználók számára, hogy az ismeretlen forrásból származó telepítések engedélyezésével fellazítsák az eszközeik biztonsági állapotát. Emellett ez a telepítési forgatókönyv javítja a végfelhasználói élményt.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>2019. január 14-i hét

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Az Android vállalat által birtokolt, teljes körűen felügyelt eszközök támogatásának előzetes verziója <!-- 1574342  -->
Az Intune mostantól támogatja a teljes körűen felügyelt Android-eszközöket, a vállalat által birtokolt "eszköz tulajdonosa" forgatókönyvet, amelyben az eszközöket szorosan felügyelik, és az egyes felhasználókhoz kapcsolódnak. Ez lehetővé teszi a rendszergazdák számára a teljes eszköz felügyeletét, a szabályzatok kiterjesztett tartományának érvénybe léptetését a munkahelyi profilokhoz, és korlátozza a felhasználókat, hogy csak a felügyelt Google Play áruházból telepítsenek alkalmazásokat. További információkért lásd: az [Android teljes körűen felügyelt eszközök Intune-regisztrációjának beállítása](../enrollment/android-fully-managed-enroll.md) és [a dedikált eszközök vagy teljes körűen felügyelt eszközök regisztrálása](../enrollment/android-dedicated-devices-fully-managed-enroll.md).  Vegye figyelembe, hogy ez a funkció előzetes verzióban érhető el. Bizonyos Intune-képességek, például a tanúsítványok, a megfelelőség és a feltételes hozzáférés jelenleg nem érhetők el az Android teljes körűen felügyelt felhasználói eszközeivel.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>2019. január 7. hét

### <a name="app-management"></a>Alkalmazáskezelés

#### <a name="intune-app-pin----2298397---"></a>Intune-alkalmazás PIN-kódja <!-- 2298397 -->
A rendszergazdaként beállíthatja, hogy a végfelhasználók hány napig várhatják el az Intune-alkalmazás PIN-kódjának módosítását. Az új beállítás *PIN-kód alaphelyzetbe állítása a napok száma* és a Azure Portal az **Intune**  > **ügyfélalkalmazások**  > **alkalmazás-védelmi szabályzatok**  >  házirend- > **Beállítások** **létrehozása** lehetőség kiválasztásával érhető el. 0**hozzáférési követelmények**. [IOS](../apps/app-protection-policy-settings-ios.md) -és [Android](../apps/app-protection-policy-settings-android.md) -eszközökhöz érhető el, ez a funkció pozitív egész értéket támogat.


#### <a name="intune-device-reporting-fields----2748738---"></a>Intune-eszközök jelentéskészítési mezői <!-- 2748738 -->
Az Intune további eszköz-jelentési mezőket biztosít, beleértve az alkalmazás regisztrációs AZONOSÍTÓját, az Android-gyártót, a modellt és a biztonsági javítás verzióját, valamint az iOS-modellt is. Az Intune-ban ezek a mezők az **ügyfélalkalmazások** > **app Protection-állapot** kiválasztásával és az App Protection-jelentés kiválasztásával érhetők el **: iOS, Android**. Emellett ezek a paraméterek segítséget nyújtanak az eszközök gyártójának (Android) **engedélyezési** listájának konfigurálásához, az eszköz modelljének **engedélyezési** listájának (Android és iOS) és az androidos biztonsági javítás minimális verziójának beállításához. 


### <a name="device-configuration"></a>Eszközök konfigurálása

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>A felügyeleti sablonok nyilvános előzetes verzióban érhetők el, és a saját konfigurációs profiljába kerülnek <!-- 3322847 -->

A felügyeleti sablonok az Intune-ban (az**eszköz konfigurációja** > **felügyeleti sablon**) jelenleg nyilvános előzetes verzióban érhető el. Ezzel a frissítéssel:

- A felügyeleti sablonok tartalmazzák az Intune-ban felügyelhető 300-beállításokat. Korábban ezek a beállítások csak a csoportházirend-szerkesztőben léteztek.
- A felügyeleti sablonok nyilvános előzetes verzióban érhetők el.
- A felügyeleti sablonok átkerülnek az **eszköz konfigurációjától** > **felügyeleti sablonokból** az **eszköz konfigurációja** > **profilok** > **create Profile** > a **platformon**, válassza **a Windows 10 és újabb** > a **Profil típusa**területen válassza a **Felügyeleti sablonok**lehetőséget.
- A jelentéskészítés engedélyezve van

A szolgáltatással kapcsolatos további információkért látogasson el a [Windows 10 sablonjaira a csoportházirend-beállítások konfigurálásához](../configuration/administrative-templates-windows.md).

A Windows 10 és újabb verziókra vonatkozik

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>Az S/MIME használata több eszköz titkosításához és aláírásához a felhasználó számára  <!-- 1333642 -->
A frissítés része az új importált tanúsítványprofilt használó S/MIME e-mail-titkosítás (**Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** > platform kiválasztása > **Importált PKCS-tanúsítvány** profiltípus). Az Intune-ban a tanúsítványok PFX formátumban importálhatók. Az Intune képes ugyanazokat a tanúsítványokat az egy felhasználó által regisztrált több eszközre is telepíteni. Ez a következőket is magában foglalja:
- A natív iOS-es e-mail-profil támogatja az S/MIME titkosítás PFX formátumú importált tanúsítványok használatával történő engedélyezését.
- Windows Phone-telefon 10 eszközön a natív posta alkalmazás automatikusan az S/MIME-tanúsítványt használja.
- A privát tanúsítványok több platformon is telepíthetők. A S/MIME-ot azonban nem minden e-mail-alkalmazás támogatja.
- Más platformokon az S/MIME engedélyezéséhez szükség lehet a levelező alkalmazás manuális konfigurálására.  
- Az S/MIME titkosítást támogató e-mail-alkalmazások esetleg az MDM által nem támogatható módon kezelik az S/MIME e-mail-titkosításhoz szükséges tanúsítványok fogadását, például a közzétevőjük tanúsítványtárából olvassák ki azokat.
A szolgáltatással kapcsolatos további információkért tekintse meg az [S/MIME-áttekintést az e-mailek aláírásához és titkosításához](../protect/certificates-s-mime-encryption-sign.md).
Támogatott a következőkön: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Új beállítások a szabályok automatikus csatlakoztatásához és a DNS-beállítások Windows 10 és újabb rendszerű eszközökön való használatakor <!-- 1333665, 2999078 -->
Windows 10 és újabb rendszerű eszközökön létrehozhat egy VPN-konfigurációs profilt, amely tartalmazza a tartományok feloldására szolgáló DNS-kiszolgálók listáját, például contoso.com. Ez a frissítés új beállításokat tartalmaz a névfeloldáshoz (**eszköz konfigurációja** > **profilok** > **profil létrehozása** > válassza a **Windows 10 és újabb verziók** a platformhoz lehetőséget > válassza a **VPN** lehetőséget a profil típusa > **DNS beállítások** >**Hozzáadás**): 
- **Automatikus csatlakozás**: Ha **engedélyezve van**, az eszköz automatikusan csatlakozik a VPN-hez, amikor az eszköz kapcsolatba lép egy megadott tartománnyal (például contoso.com).
- **Állandó**: alapértelmezés szerint az összes Name Resolution Policy Table (NRPT) szabály aktív, ha az eszköz ehhez a VPN-profilhoz van csatlakoztatva. Ha a beállítás **engedélyezve** van egy NRPT-szabályon, a szabály aktív marad az eszközön, még akkor is, ha a VPN megszakad. A szabály addig marad, amíg el nem távolítja a VPN-profilt, vagy amíg a szabályt manuálisan nem távolítja el, ami a PowerShell használatával végezhető el.
A [Windows 10-es VPN-beállítások](../configuration/vpn-settings-windows-10.md) a beállításokat ismertetik. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>A VPN-profilok megbízható hálózati észlelésének használata Windows 10-es eszközökön <!-- 1500165 -->
A megbízható hálózati észlelés használata esetén megakadályozhatja, hogy a VPN-profilok automatikusan hozzanak létre VPN-kapcsolatokat, ha a felhasználó már megbízható hálózaton van. Ezzel a frissítéssel hozzáadhat DNS-utótagokat a megbízható hálózatok észlelésének engedélyezéséhez a Windows 10 vagy újabb rendszerű eszközökön (**eszköz konfigurációja** > **profilok** > **create Profile** > **Windows 10 és újabb verziók** a következőhöz: platform > **VPN** a profil típusaként).
A [Windows 10-es VPN-beállítások](../configuration/vpn-settings-windows-10.md) a jelenlegi VPN-beállításokat listázza.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Több felhasználó által használt Windows holografikus for Business-eszközök kezelése <!-- 1907917, 1063203 -->
Jelenleg az egyéni OMA-URI beállítás használatával konfigurálhatja a Windows 10 és a Windows holografikus for Business rendszerű eszközök megosztott számítógép-beállításait. Ezzel a frissítéssel új profilt ad hozzá a megosztott eszközök beállításainak konfigurálásához (**eszköz konfigurációja** > **profilok** > **create Profile** > **Windows 10 és újabb** > **megosztott többfelhasználós eszköz**).
Ha többet szeretne megtudni erről a szolgáltatásról, lépjen az Intune-beállítások elemre a [megosztott eszközök kezeléséhez](../configuration/shared-user-device-settings.md).
A következőkre vonatkozik: Windows 10 és újabb, Windows holografikus for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Új Windows 10 frissítési beállítások <!--2626030  2512994  -->
A [Windows 10-es frissítési gyűrűkhöz](../protect/windows-update-for-business-configure.md)a következőket állíthatja be:
- **Automatikus frissítési viselkedés** – új lehetőség használata, *Alaphelyzetbe állítás az alapértelmezett* értékre, ha vissza szeretné állítani az eredeti automatikus frissítési beállításokat egy Windows 10-es gépen az *október 2018 frissítést* futtató gépeken.
- A **felhasználó megakadályozása a Windows-frissítések szüneteltetésében** – új szoftverfrissítési beállítások konfigurálása, amely lehetővé teszi a felhasználók számára, hogy letiltsák vagy engedélyezzék a frissítések telepítését a gépek *beállításaiból* . 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>az iOS-es e-mail profilok az S/MIME-aláírást és a titkosítást is használhatják <!-- 2662949 -->
Létrehozhat egy olyan e-mail-profilt, amely különböző beállításokat tartalmaz. Ez a frissítés olyan S/MIME-beállításokat tartalmaz, amelyek az iOS-eszközökön az e-mailes kommunikáció aláírására és titkosítására használhatók (**eszköz-konfiguráció**  > **profilok**  > **profil létrehozása** > válassza az **iOS** lehetőséget a platformhoz >  **A profil típusának e-mail-címe** .
az [iOS e-mail konfigurációs beállításai](../configuration/email-settings-ios.md) a beállításokat listázza.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Egyes BitLocker-beállítások a Windows 10 Pro kiadását támogatják<!-- 2727036 -->
Létrehozhat egy olyan konfigurációs profilt, amely az Endpoint Protection beállításait beállítja Windows 10-es eszközökön, beleértve a BitLockert is. Ez a frissítés az egyes BitLocker-beállításokhoz nyújt támogatást a Windows 10 Professional Edition rendszerhez. A védelmi beállítások megtekintéséhez válassza a [Windows 10 Endpoint Protection-beállítások](../protect/endpoint-protection-windows-10.md#windows-encryption)elemét.

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>A megosztott eszköz konfigurációját a rendszer a Azure Portal iOS-eszközök zárolási képernyőjének üzenetére átnevezi<!-- 2809362 -->
Az iOS-eszközökhöz készült konfigurációs profil létrehozásakor megadhatja a **megosztott eszköz konfigurációs** beállításait a zárolási képernyőn megadott szöveg megjelenítéséhez. Ez a frissítés a következő módosításokat tartalmazza: 
- A Azure Portal **megosztott eszköz konfigurációs** beállításait a rendszer átnevezi a "zárolási képernyő üzenete (csak felügyelt)" (**eszköz konfigurációja**  > **profilok**  > **Létrehozás profil** > válassza az **iOS** lehetőséget a platformhoz > Válassza ki a profil típusa > a **zárolási képernyő üzenete** **) elemet.**
- A zárolási képernyő üzeneteinek hozzáadásakor beszúrhat egy sorozatszámot, egy eszköznév vagy egy másik, az eszközre jellemző értéket változóként az **eszköz címkéjének adatai** és a **zárolási képernyő lábjegyzetében**. Megadhatja például a `Device name: {{devicename}}` vagy a `Serial number is {{serialnumber}}` kapcsos zárójelek használatával. az [iOS-tokenek](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) felsorolják a használható elérhető jogkivonatokat.
A [zárolási képernyőn lévő üzenetek megjelenítéséhez szükséges beállítások](../configuration/ios-device-features-settings.md#lock-screen-message) a beállításokat jelenítik meg.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Új App Store, doc Viewing, Gaming Device korlátozási beállítások hozzáadása iOS-eszközökhöz <!-- 2827760-->
Az **eszköz konfigurációja** > **profilok** > **profil létrehozása** > **iOS** platformon > **eszközre vonatkozó korlátozások** a profil típusa > **App Store, doc Viewing, Gaming**, a következő beállítások hozzáadva: a felügyelt alkalmazások számára lehetővé teszi a névjegyek írását a nem felügyelt Névjegyalbum-fiókok számára, hogy a nem felügyelt alkalmazások beolvassák a felügyelt névjegyek fiókjait a beállítások megtekintéséhez, az [iOS-eszközök korlátozásai](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming)című részben

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Új értesítések, tippek és billentyűzár-beállítások az androidos vállalati eszközök tulajdonosi eszközeihez <!-- 3201839 3201843 -->
Ez a frissítés több új funkciót is tartalmaz az Android Enterprise rendszerű eszközökön, ha az eszköz tulajdonosaként fut. A szolgáltatások használatához nyissa meg az **eszköz konfigurációja** > **profilok** > **profil létrehozása** > a **platformon**, válassza az **Android Enterprise** > **Profil típusa**lehetőséget, majd válassza az **eszköz tulajdonosa csak**@no__ t-9**eszközre vonatkozó korlátozások**.

Új funkciók többek között az alábbiak: 

- Tiltsa le a rendszerértesítéseket, beleértve a bejövő hívásokat, a rendszerriasztásokat, a rendszerhibákat és egyebeket.
- Azt javasolja, hogy kiugorjon az első alkalommal megnyitott alkalmazásokhoz kapcsolódó oktatóanyagok és útmutatók.
- Tiltsa le a speciális billentyűzár-beállításokat, például a kamerát, az értesítéseket, az ujjlenyomatok feloldását és egyebeket.


A beállítások megjelenítéséhez nyissa meg az [Android Enterprise-eszközök korlátozási beállításait](../configuration/device-restrictions-android-for-work.md).

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Az androidos vállalati eszközök tulajdonosi eszközei mindig a VPN-kapcsolatokon keresztül használhatók <!-- 3202194 -->
Ebben a frissítésben az androidos vállalati eszközök tulajdonosi eszközein az Always-On VPN-kapcsolatokat használhatja. A mindig bekapcsolt VPN-kapcsolatokkal a kapcsolat folyamatosan fenntartható vagy azonnal újraindítható, ha a felhasználó feloldja az eszközét, ha az eszköz újraindul, vagy ha a vezeték nélküli hálózat megváltozik. A kapcsolat „zárolt” módba is állítható, amely blokkol minden hálózati forgalmat, amíg a VPN-kapcsolat aktív.
Engedélyezheti a VPN-t az **eszköz konfigurációjában** > **profilok** > **profil létrehozása** > **Android Enterprise** for platform > **eszköz-korlátozások** az eszköz tulajdonosának csak > **kapcsolat** beállítások. A beállítások megjelenítéséhez nyissa meg az [Android Enterprise-eszközök korlátozási beállításait](../configuration/device-restrictions-android-for-work.md).

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Új beállítás a Windows 10-es eszközök Feladatkezelő-folyamatainak befejezéséhez <!-- 3285177 --> 
Ez a frissítés egy új beállítást tartalmaz a feladatok befejezéséhez a Feladatkezelő használatával a Windows 10-es eszközökön. Az eszköz konfigurációs profiljának használatával (**eszköz konfigurációja**  > **profilok**  > **profil létrehozása** > a **platformon**válassza a **Windows 10** > lehetőséget a **Profil típusa**területen, majd válassza az **eszközök korlátozásai** elemet.  > **általános** beállítások) a beállítás engedélyezéséhez vagy megtiltásához válassza a beállítást.
A beállítások megtekintéséhez nyissa meg a [Windows 10-es eszközök korlátozási beállításait](../configuration/device-restrictions-windows-10.md).
A Windows 10 és újabb verziókra vonatkozik

### <a name="device-enrollment"></a>Eszközök beléptetése

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Részletesebb regisztrációt korlátozó sikertelen üzenetküldés <!-- 3111564 -->
Részletesebb hibaüzenetek érhetők el, ha a regisztrációs korlátozások nem teljesülnek. Az üzenetek megjelenítéséhez nyissa meg az **Intune**  >  a > a**hibák elhárítása** című témakört, és ellenőrizze a regisztrálási hibák táblázatát. További információ: a [beléptetési hibák listája](help-desk-operators.md#enrollment-failure-reference).

### <a name="monitor-and-troubleshoot"></a>Monitorozás és hibaelhárítás

#### <a name="tenant-status-dashboard-----1124854---"></a>Bérlői állapot irányítópultja  <!-- 1124854 -->
Az új [bérlő állapota lap](tenant-status.md) egyetlen helyet biztosít, ahol megtekintheti a bérlő állapotát és kapcsolódó részleteit.  Az irányítópult négy területre oszlik:
- **Bérlői adatok** – megjeleníti a bérlő nevét és helyét, a Mdm-szolgáltatót, a bérlő összes regisztrált eszközét, valamint a licencek számát. Ez a szakasz a bérlő aktuális szolgáltatásának kiadását is felsorolja.
- **Összekötő állapota** – megjeleníti a konfigurált elérhető összekötők adatait, és azokat is listázhatja, amelyek még nincsenek engedélyezve.  
   Az egyes összekötők aktuális állapota alapján a rendszer Kifogástalanként, figyelmeztetésként vagy sérültként jelöli meg őket. Válasszon ki egy összekötőt a részletezéshez, és tekintse meg a részleteket, vagy konfiguráljon további információkat.
- **Intune Service Health** – a Bérlővel kapcsolatos aktív incidensek és kimaradások részleteit jeleníti meg. Az ebben a szakaszban található információkat a rendszer közvetlenül az Office Message Centerből kéri le.
- **Intune Hírek** – megjeleníti a bérlőhöz tartozó aktív üzeneteket. Az üzenetek olyan dolgok, mint például az értesítések, amikor a bérlő megkapja az Intune legújabb funkcióit.  Az ebben a szakaszban található információkat a rendszer közvetlenül az Office Message Centerből kéri le.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Új Súgó-és támogatási élmény a Windows 10-es Céges portál <!-- 1488939-->
Az új Céges portál Súgó & támogatási oldal segít a felhasználóknak a hibaelhárításban, és segítséget kérni az alkalmazás-és hozzáférési problémákhoz. Az új lapon e-mail-hibaüzeneteket és a diagnosztikai napló részleteit is megtalálhatja, és megkeresheti a szervezet ügyfélszolgálatának részleteit. Emellett a kapcsolódó Intune-dokumentációra mutató hivatkozásokkal is megtalálják a gyakori kérdések szakaszt. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Új Súgó és támogatási élmény az Intune-hoz   <!-- #3307080 -->
Az új Súgó és támogatás élményét minden bérlő számára elérhetővé tesszük a következő néhány napban. Ez az új felhasználói felület elérhető az Intune-ban, és a [Azure Portalban](https://portal.azure.com/)található Intune-pengék használatával érhető el.
Az új felületen saját szavaival fejtheti ki problémáját, valamint hibaelhárítási ötleteket kaphat, és webalapú szervizelési tartalmakat találhat. Ezeket a megoldásokat egy, a felhasználói lekérdezések által vezérelt, szabályon alapuló gépi tanulási algoritmus segítségével ajánljuk. A probléma-specifikus útmutatás mellett az új eset-létrehozási munkafolyamattal is megnyithat egy támogatási esetet e-mailben vagy telefonon. Ez az új felhasználói élmény a Súgó és támogatás megnyitásakor a konzol területén alapuló, előre kiválasztott beállítások statikus készletének korábbi súgóját és támogatását váltja fel. További információkért lásd: [a Microsoft Intune támogatásának beszerzése](get-support.md).

### <a name="role-based-access-control"></a>Szerepköralapú hozzáférés-vezérlés

#### <a name="scope-tags-for-apps----1081941---"></a>Alkalmazások hatókör-címkéi <!-- 1081941 -->
Hatókör-címkéket hozhat létre a szerepkörök és alkalmazások hozzáférésének korlátozásához. Hatókör-címkét adhat hozzá egy alkalmazáshoz, hogy csak a szerepkörökhöz hozzárendelt felhasználók férjenek hozzá az alkalmazáshoz. Jelenleg az Intune-hoz hozzáadott, felügyelt Google Play-vagy Apple Volume Purchase Program-(VPP-) alkalmazással megvásárolt alkalmazások nem rendelhetők hozzá hatóköri címkékhez (a jövőbeli támogatás tervezett). További információkért lásd: [hatókör-címkék használata a házirendek szűréséhez](scope-tags.md).

## <a name="notices"></a>Értesítések

[!INCLUDE [Intune notices](../includes/intune-notices.md)]