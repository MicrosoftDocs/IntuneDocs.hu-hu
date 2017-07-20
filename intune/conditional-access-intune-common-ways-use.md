---
title: "Feltételes hozzáférés az Intune-nal"
titleSuffix: Intune on Azure
description: "A feltételes hozzáférés használatának szokásos módjai az Intune-ban"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ba1f12d762a6288fc2e7a3bfdae637f8ae13a94
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2017
---
# <a name="common-ways-to-use-conditional-access-with-intune"></a>A feltételes hozzáférés használatának szokásos módjai az Intune-ban

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ahhoz, hogy a cégénél ellenőrizhesse a feltételes hozzáférési megfelelőséget, konfigurálnia kell az Intune mobileszköz-megfelelőségi szabályzatát és az Intune mobilalkalmazás-kezelési (MAM) funkcióit. Ez a cikk a feltételes hozzáférés Intune-ban alkalmazott leggyakoribb módjait mutatja be.

## <a name="device-based-conditional-access"></a>Eszközalapú feltételes hozzáférés

Az Intune és az Azure Active Directory együtt gondoskodik róla, hogy csak felügyelt és megfelelő eszközök férhessenek hozzá az e-mailekhez, az Office 365-szolgáltatásokhoz, a szolgáltatott szoftverként (SaaS) használt alkalmazásokhoz és a [helyszíni alkalmazásokhoz](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). Ezenkívül olyan szabályzatot is beállíthat az Azure Active Directoryban, amely az Office 365-szolgáltatásokhoz való hozzáférést csak tartományhoz csatlakozó számítógépek vagy az Intune-ban regisztrált mobileszközök számára engedélyezi.

Az Intune biztosítja az eszközök megfelelőségi állapotát értékelő eszközmegfelelőségi szabályzatokat. A rendszer jelenti a megfelelőségi állapotot az Azure Active Directorynak, amely azon szabályzat érvényre juttatásához fogja azt használni, amely akkor jön létre az Azure Active Directoryban, amikor a felhasználó kísérletet tesz a céges erőforrások elérésére.

Az [új Azure Portaltól](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) kezdődően az Exchange Online és más Office 365-termékek eszközalapú feltételes hozzáférési szabályzatainak konfigurálása az Azure Portalon keresztül történik.

-   További tudnivalók: [Feltételes hozzáférés az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

-   További tudnivalók: [Eszközmegfelelőség az Intune szolgáltatásban](device-compliance.md).

-   További tudnivalók: [A levelezés, az Office 365 és más szolgáltatások védelme az Intune feltételes hozzáférési funkciójának használatával](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="conditional-access-for-exchange-on-premises"></a>Feltételes hozzáférés a helyszíni Exchange-hez

A feltételes hozzáférés használatával az eszközfelügyeleti szabályzatok és az eszközregisztráció állapota alapján engedélyezhető, illetve tiltható a hozzáférés a **helyszíni Exchange-hez**. A feltételes hozzáférés és az eszközmegfelelőségi szabályzat együttes alkalmazásával elérheti, hogy csak megfelelő eszközök férhessenek hozzá a helyszíni Exchange-hez.

A részletesebb vezérléshez speciális feltételes hozzáférési beállításokat is megadhat, például:

-   Egyes platformok engedélyezése vagy letiltása.

-   Az Intune által nem felügyelt eszközök azonnali letiltása.

Az eszközmegfelelőségi és feltételes hozzáférési szabályzatok alkalmazása esetén a rendszer ellenőrzi a helyszíni Exchange elérésére használt összes eszköz megfelelőségét.

Ha egy eszköz nem tesz eleget az adott feltételeknek, a rendszer végigvezeti a felhasználót az eszközregisztráció lépésein, hogy megszűnjön az eszköz megfelelőségét akadályozó probléma.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>A feltételes hozzáférés működése helyszíni Exchange esetén

Az Intune Exchange Connector lekéri az Exchange-kiszolgálón lévő összes Exchange Active Sync- (EAS-) rekordot, amelyeket az Intune átvesz, és megfeleltet az Intune-eszközrekordoknak. Ezek a rekordok az Intune által regisztrált és felismert eszközöknek felelnek meg. A folyamat engedélyezi vagy tiltja a hozzáférést az e-mailekhez.

Ha az EAS-rekord olyan friss, hogy az Intune még nem ismeri fel, az Intune kiad egy olyan parancsmagot, amely letiltja az e-mailekhez való hozzáférést. Az alábbi ábrán részletesen látható a folyamat:

![Folyamatábra: Feltételes hozzáférés helyszíni Exchange esetén](./media/ca-intune-common-ways-1.png)

1.  A felhasználó megkísérel hozzáférni a helyszíni Exchange 2010 SP1-es vagy későbbi verziójában tárolt céges e-mailekhez.

2.  Ha az Intune által nem felügyelt eszközt használ, a rendszer letiltja az eszköz e-mail-hozzáférését. Az Intune letiltási értesítést küld az EAS-ügyfélnek.

3.  Az EAS megkapja a letiltási értesítést, karanténba helyezi az eszközt, majd karanténüzenetet küld a korrekciós lépésekkel és azon hivatkozásokkal, amelyekkel a felhasználó regisztrálhatja az eszközt.

4.  A munkahelyi csatlakozás létrejöttével megtörténik az első lépés ahhoz, hogy az eszköz az Intune felügyelete alá kerüljön.

5.  A rendszer regisztrálja az eszközt az Intune-ban.

6.  Az Intune egy eszközrekordba képezi le az EAS-rekordot, és menti az eszközmegfelelőségi állapotot.

7.  Az eszközök Azure AD-beli regisztrációjának folyamata során a rendszer regisztrálja az EAS-es ügyfél-azonosítót, ami kapcsolatot létesít az Intune-eszközrekord és az EAS-es ügyfél-azonosító között.

8.  Az eszközök Azure AD-beli regisztrációja menti az eszköz állapotadatait.

9.  Ha a felhasználó teljesíti a feltételes hozzáférési szabályzatok feltételeit, az Intune parancsmagot ad ki az Intune Exchange Connectoron keresztül, amely lehetővé teszi a postaláda szinkronizálását.

10. Az Exchange-kiszolgáló elküldi az értesítést az EAS-ügyfélhez, hogy a felhasználó hozzáférhessen az e-mailjeihez.

#### <a name="whats-the-intune-role"></a>Mi az Intune szerepe?

Az Intune értékeli és felügyeli az eszközök állapotát.

#### <a name="whats-the-exchange-server-role"></a>Mi az Exchange-kiszolgáló szerepe?

Az Exchange-kiszolgáló biztosítja az API-t és az infrastruktúrát az eszközök karanténba helyezéséhez.

> [!IMPORTANT] 
> Ne feledje, hogy az eszközmegfelelőség értékeléséhez az eszköz felhasználójának rendelkeznie kell egy hozzárendelt megfelelőségi profillal. Amennyiben a felhasználóra nem vonatkozik megfelelőségi szabályzat, a rendszer megfelelőként kezeli az eszközt, és egyáltalán nem korlátozza a hozzáférést.

### <a name="conditional-access-based-on-network-access-control"></a>Hálózati hozzáférés-vezérlésen alapuló feltételes hozzáférés

Az Intune-nak számos integrált partnere van (köztük a Cisco ISE, az Aruba Clear Pass és a Citrix NetScaler), amelyek segítségével biztosítja az Intune-regisztráción és az eszközmegfelelőségi állapoton alapuló hozzáférés-vezérlést.

A rendszer attól függően engedélyezheti vagy tilthatja a felhasználók hozzáférését a céges Wi-Fi-hez vagy VPN-erőforrásokhoz, hogy az eszközüket felügyelik-e az Intune eszközmegfelelőségi szabályzatai, illetve az eszköz megfelel-e azoknak.

-   További tudnivalókért lásd: [Hálózati hozzáférés-vezérlés (NAC) integrációja az Intune-nal](network-access-control-integrate.md).

### <a name="conditional-access-based-on-device-risk"></a>Eszközkockázaton alapuló feltételes hozzáférés

Az Intune partnerkapcsolatot kötött a Mobile Threat Defense forgalmazóival. Ez a szolgáltatás biztonsági megoldást nyújt a mobileszközökön megjelenő kártevők, trójai vírusok és egyéb fenyegetések észleléséhez.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Hogy működik az Intune és a Mobile Threat Defense integrációja?

Ha a mobileszközökön telepítve van a Mobile Threat Defense ügynöke, az ügynök megfelelőségiállapot-üzenetekben jelentheti az Intune-nak, hogy fenyegetés jelent meg az eszközön.

Az Intune és a Mobile Threat Defense integrációja fontos szerepet játszik az eszközkockázat alapján hozott feltételes hozzáférési döntésekben.

-   További tudnivalók: [Intune Mobile Threat Defense](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).

### <a name="conditional-access-for-windows-pcs"></a>Feltételes hozzáférés Windows rendszerű számítógépeken

A Windows rendszerű számítógépek feltételes hozzáférése hasonló képességeket biztosít, mint a mobileszközöké. Ez a szakasz a feltételes hozzáférés Intune által felügyelt Windows rendszerű gépeken alkalmazható módjait tekinti át.

#### <a name="corporate-owned"></a>Céges tulajdonú eszközök

-   **Helyszíni AD-tartományhoz csatlakoztatott eszköz:** Ez a feltételes hozzáférés leggyakoribb rendszerbe állítási megoldása azon szervezeteknél, amelyek megfelelőnek tartják, hogy Windows rendszerű számítógépeiket eleve AD-csoportházirendekkel és/vagy a System Center Configuration Managerrel felügyelik.

-   **Azure AD-tartományhoz csatlakoztatott és Intune által felügyelt eszköz:** Ez a megoldás általában a saját eszközök választásán (CYOD) alapuló és laptophordozásos forgatókönyvekhez kapcsolódik, ahol az eszközök csak ritkán csatlakoznak a céges hálózatra. Az eszköz az Azure AD-hoz csatlakozik, és az Intune-ban regisztrálják, ami eltávolít minden, a helyszíni AD-tól és tartományvezérlőktől való függőséget. A céges erőforrások kezelésekor ez lehet a feltételes hozzáférés feltétele.

-   **AD-tartományhoz csatlakoztatott eszköz és System Center Configuration Manager:** A System Center Configuration Manager aktuális ága feltételes hozzáférési képességeket nyújt bizonyos – a gép tartományhoz való csatlakoztatásán kívüli – megfelelőségi feltételek ellenőrzésére:

    -   Titkosították-e a számítógépet?

    -   Telepítve van-e rajta kártevő szoftver? Frissítették az eszközt?

    -   Jailbreakelték vagy rootolták az eszközt?

#### <a name="bring-your-own-device-byod"></a>Saját eszközök használata (BYOD)

-   **Munkahelyi csatlakozás és Intune-felügyelet:** A felhasználók ebben az esetben a saját eszközeiket csatlakoztatva érhetik el a céges erőforrásokat és szolgáltatásokat. A munkahelyi csatlakozás használatával és az eszközök Intune-regisztrációjával eszközszintű szabályzatokat kaphat, ami újabb lehetőséget nyújt a feltételes hozzáférés feltételeinek értékeléséhez.

## <a name="app-based-conditional-access"></a>Alkalmazásalapú feltételes hozzáférés

Az Intune és az Azure Active Directory együtt biztosítja, hogy csak felügyelt alkalmazások férhessenek hozzá a céges e-mailekhez vagy más Office 365-szolgáltatásokhoz.

-   További tudnivalók: [Alkalmazásalapú feltételes hozzáférés az Intune-nal](app-based-conditional-access-intune.md).

## <a name="next-steps"></a>További lépések

[Feltételes hozzáférés konfigurálása az Azure Active Directoryban](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Helyszíni Exchange Connector telepítése az Intune-nal](https://docs.microsoft.com/intune/exchange-connector-install).

[Feltételes hozzáférési szabályzat létrehozása a helyszíni Exchange-hez](conditional-access-exchange-create.md)