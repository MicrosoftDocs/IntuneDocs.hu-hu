---
title: A Windows Update Vállalatoknak konfigurálása a Microsoft Intune-ban – Azure | Microsoft Docs
description: A profilok szoftverfrissítési beállításainak frissítésével frissítési kört hozhat létre, áttekintheti a megfelelőséget, és szüneteltetheti a Windows Update Vállalatoknak frissítéseit a Microsoft Intune Windows 10-es eszközökön való használatával.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d34e44c6e046ddbc9b47bbe90900f5992df9e85
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72584561"
---
# <a name="manage-software-updates-in-intune"></a>Szoftverfrissítések kezelése az Intune-ban

Az Intune segítségével definiálhatja a frissítési köröket, amelyek meghatározzák, hogy a Windows mint szolgáltatás hogyan frissíti a Windows 10-es eszközöket. A frissítési körök az eszközök csoportjaihoz hozzárendelt szabályzatok. Frissítési körök használatával kialakítható az üzleti igényeknek leginkább megfelelő frissítési stratégia. További információ: [Frissítések kezelése a Vállalati Windows Update használatával](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

A Windows 10-ben az új funkció- és minőségi frissítések magukban foglalják valamennyi korábbi frissítés tartalmát. Így a legújabb frissítés telepítésével biztosítható, hogy a Windows 10 rendszerű eszközök naprakészek legyenek. A Windows korábbi verzióitól eltérően a frissítés egy része helyett már a teljes frissítést telepíteni kell.


A Windows Update Vállalatoknak használatával leegyszerűsítheti a frissítéskezelést. Nem kell jóváhagynia az eszközcsoportok egyes frissítéseit. A környezetek kockázatkezelését egy frissítéskibocsátási stratégia konfigurálásával intézheti. Az Intune lehetővé teszi a [frissítési beállítások konfigurálását](../windows-update-settings.md) az eszközökön, és lehetővé teszi a frissítések telepítésének késleltetését. Az Intune nem tárolja a frissítéseket, csak a frissítési szabályzat-hozzárendelést. Az eszközök közvetlenül a Microsoft Update-hez fordulnak a frissítésekért. Azon beállítások gyűjteménye, amelyek a Windows 10 frissítéseinek telepítése során konfigurálhatók, *Windows 10-es frissítési gyűrűnek*nevezzük.

A Windows 10-es frissítési gyűrűk támogatják a [hatókör címkéit](../fundamentals/scope-tags.md). A frissítési körökkel rendelkező hatókör-címkék segítségével szűrheti és kezelheti a használt konfigurációk készleteit.

## <a name="prerequisites"></a>Előfeltételek  

A Windows 10 rendszerű eszközök Intune-ban való használatához a következő előfeltételeknek kell teljesülniük.  

- A Windows 10 rendszerű számítógépeken legalább Windows 10 Pro rendszernek kell futnia a Windows évfordulós frissítéssel vagy újabb verzióval (1607-es vagy újabb verzió)
- Windows Update a következő Windows 10 kiadásokat támogatja:
  - Windows 10
  - Windows 10 Team (Surface Hub-eszközök esetén)
  - Windows Holographic for Business  

    A Windows holografikus for Business támogatja a Windows-frissítések egy részhalmazát, beleértve a következőket:
    - **Az automatikus frissítés viselkedése**
    - **Microsoft-termékek frissítései**
    - **Karbantartási csatorna**: támogatja a **féléves csatornát** és a **féléves Channel (Targeted)** lehetőségeket. További információ: a [Windows holografikus kezelése](../fundamentals/windows-holographic-for-business.md).  

    > [!NOTE]  
    > Nem **támogatott verziók és kiadások**:
    > - Windows 10 mobil verzió  
    > - Windows 10 Enterprise LTSC. A Windows Update for Business (WUfB) jelenleg nem támogatja a *hosszú távú szolgáltatási csatornák* kiadásait. Alternatív javítási módszerek, például a WSUS vagy a Configuration Manager használatának megtervezése.  

- Windows-eszközökön a **visszajelzések & a diagnosztika** >  a**diagnosztikai és használati adatokat** **alapszintű**, **bővített**vagy **teljes**értékre kell beállítani.  

  A Windows 10-es eszközök *diagnosztikai és használati adatokra* vonatkozó beállítását manuálisan is konfigurálhatja, vagy a Windows 10 és újabb rendszerekhez készült Intune-eszközök korlátozási profilját használhatja. Ha eszköz-korlátozási profilt használ, állítsa be a **használati adatok megosztására** szolgáló [eszköz korlátozási beállítását](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry) legalább **alapszintű**értékre. Ez a beállítás a Windows 10 vagy újabb rendszerű eszközök korlátozási szabályzatának konfigurálásakor a **jelentéskészítés és a telemetria** kategóriában található.

  Az eszközprofilokról további információt nyújt az [Eszközkorlátozási beállítások konfigurálása](../configuration/device-restrictions-configure.md) című témakör.  

- Ha a klasszikus Azure portált használja, a [beállításokat áttelepítheti a Azure Portalra](#migrate-update-settings-to-the-azure-portal).  


## <a name="create-and-assign-update-rings"></a>Frissítési körök létrehozása és hozzárendelése

1. Jelentkezzen be az [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) -ba, majd válassza a **szoftverfrissítések**  > **Windows 10 frissítési** körök  > **Létrehozás**lehetőséget.  

2. Az alapvető beállítások lapon adjon meg egy nevet, egy leírást (nem kötelező), majd kattintson a **tovább**gombra.  

   ![Windows 10 frissítési kör munkafolyamat létrehozása](./media/windows-update-for-business-configure/basics-tab.png)

3. A **frissítési kör beállításai** lapon adja meg az üzleti igényeknek megfelelő beállításokat. Az elérhető beállításokkal kapcsolatos további információkért lásd: a [Windows Update beállításai](windows-update-settings.md). A *frissítési* és *felhasználói élmény* beállításainak konfigurálása után kattintson a **Tovább gombra**.  

4. A **hatókör címkék** lapon válassza a **hatókör címkék** kiválasztása lehetőséget a *címkék kiválasztása* ablaktábla megnyitásához, ha alkalmazni szeretné őket a frissítési gyűrűre.  

   - A **címkék kiválasztása** panelen válasszon ki egy vagy több címkét, majd kattintson a **kiválasztás** elemre, és adja hozzá őket a frissítési gyűrűhöz, és térjen vissza a *hatókör címkék* panelre.  

   Ha elkészült, kattintson a **tovább** gombra a *hozzárendelések*folytatásához. 

5. A **hozzárendelések** lapon válassza a **+ csoportok kiválasztása lehetőséget** , majd rendelje hozzá a frissítési kört egy vagy több csoporthoz. **Válassza a + csoportok kiválasztása lehetőséget** a hozzárendelés finomhangolásához. A folytatáshoz kattintson a **tovább** gombra.  

6. A **felülvizsgálat + létrehozás** lapon tekintse át a beállításokat, majd válassza a **Létrehozás** lehetőséget, amikor készen áll a Windows 10-es frissítési kör mentéséhez. Az új frissítési kör megjelenik a frissítési körök listájában.

## <a name="manage-your-windows-10-update-rings"></a>Windows 10-es frissítési gyűrűk kezelése

A portálon kiválaszthatja a Windows 10 frissítési gyűrűjét az **Áttekintés** panel megnyitásához. Ebből a panelből megtekintheti a gyűrűk hozzárendelési állapotát, és további műveleteket hajthat végre a gyűrű kezeléséhez.

### <a name="to-view-an-updates-rings-overview-pane"></a>A frissítési körök áttekintése panel megtekintése: 

1. Jelentkezzen be az Azure Portalra.
2. Navigáljon az **Intune** > **szoftverfrissítések** > **Windows 10 frissítési**körök elemre.
3. Válassza ki a megtekinteni vagy kezelni kívánt frissítési kört.  

A hozzárendelési állapot megtekintése mellett a következő műveleteket is kiválaszthatja az Áttekintés ablaktábla tetején a frissítési kör kezeléséhez:  
- [Törlés](#delete)  
- [Szünet](#pause)  
- [Folytatása](#resume)  
- [Kiterjesztése](#extend)  
- [Eltávolítása](#uninstall)  

![Elérhető műveletek](./media/windows-update-for-business-configure/overview-actions.png)

### <a name="delete"></a>Törlés  

A kiválasztott Windows 10-es frissítési kör beállításainak kényszerítéséhez válassza a **Törlés** lehetőséget. A gyűrű törlése eltávolítja annak konfigurációját az Intune-ból, így az Intune már nem érvényes, és nem kényszeríti ki ezeket a beállításokat.  

A gyűrűnek az Intune-ból való törlése nem módosítja a frissítési gyűrűhöz rendelt eszközök beállításait.  Ehelyett az eszköz megtartja a jelenlegi beállításait. Az eszközök nem tartanak fenn korábbi rekordot a korábban megtartott beállításokról. Az eszközök további frissítési köröktől származó beállításokat is fogadhatnak, amelyek aktívak maradnak.  

#### <a name="to-delete-a-ring"></a>Gyűrű törlése  

1. Egy frissítési kör Áttekintés lapjának megtekintésekor válassza a **Törlés**lehetőséget.  
2. Válassza az **OK** gombot.  

### <a name="pause"></a>Szünet  

A **pause (szüneteltetés** ) lehetőség kiválasztásával megakadályozhatja, hogy a hozzárendelt eszközök a szolgáltatáshoz tartozó frissítéseket és a minőségi frissítéseket a gyűrű szüneteltetése után akár 35 napig is megkapják. A megadott időtartam után a felfüggesztés automatikusan megszűnik, és az eszköz keresni kezdi az alkalmazható Windows-frissítéseket. A keresés után a frissítések ismét felfüggeszthetők. Ha folytatja a szüneteltetett frissítési kör folytatását, majd újra szünetelteti a gyűrűt, a szüneteltetési időszak 35 napra visszaállítható.  

#### <a name="to-pause-a-ring"></a>Gyűrű szüneteltetése  

1. Egy frissítési kör Áttekintés lapjának megtekintésekor válassza a **szüneteltetés**lehetőséget.  
2. Válassza a **funkció** vagy a **minőség** lehetőséget a frissítés szüneteltetéséhez, majd kattintson **az OK gombra**.  
3. Egy frissítési típus felfüggesztése után a másik frissítési típus szüneteltetéséhez válassza a Szüneteltetés újra lehetőséget.  

Ha a frissítési típus szüneteltetve van, az adott gyűrű áttekintő panelje azt jeleníti meg, hogy hány nap van hátra a frissítési típus folytatása előtt.

> [!IMPORTANT]  
> A szüneteltetési parancs kiadása után az eszközök akkor kapják meg ezt a parancsot, amikor legközelebb bejelentkeznek a szolgáltatásba. Megtörténhet, hogy mielőtt bejelentkeznek, még telepítenek egy ütemezett frissítést. Ha az adott eszköz ki van kapcsolva a felfüggesztési parancs kiadásakor, akkor a bekapcsolása után esetleg letölthet és telepíthet ütemezett frissítéseket, mielőtt bejelentkezik az Intune-ba.

### <a name="resume"></a>Folytatása  

Amíg a frissítési kör szünetel, a **Folytatás** gombra kattintva visszaállíthatja a szolgáltatás és a minőségi frissítéseket az adott gyűrű aktív működéséhez. A frissítési kör folytatása után újra szüneteltetheti a gyűrűt.  

#### <a name="to-resume-a-ring"></a>Gyűrű folytatása  

1. Ha megtekinti a szüneteltetett frissítési kör áttekintés lapját, válassza a **Folytatás**lehetőséget.  
2. Válassza ki az elérhető lehetőségek közül a **funkció** vagy a **minőségi** frissítések folytatásához, majd kattintson **az OK gombra**.  
3. Egy frissítési típus folytatása után a másik frissítés folytatásához válassza a folytatás újra lehetőséget.  

### <a name="extend"></a>Kiterjesztése  

Amíg a frissítési kör szünetel, a **kiterjesztés** lehetőség kiválasztásával alaphelyzetbe állíthatja a szüneteltetési időszakot a szolgáltatás és a minőségi frissítések esetében az adott frissítési kör 35 napra.  

#### <a name="to-extend-the-pause-period-for-a-ring"></a>A szünet időtartamának meghosszabbítása egy adott gyűrűn  

1. Ha megtekinti a szüneteltetett frissítési kör áttekintés lapját, válassza a **kiterjesztés**lehetőséget. 
2. Válassza ki az elérhető lehetőségek közül a **funkció** vagy a **minőségi** frissítések folytatásához, majd kattintson **az OK gombra**.  
3. Miután kiterjesztte az egyik frissítési típus szüneteltetését, kiválaszthatja az újbóli bővítés lehetőséget a másik frissítési típus kiterjesztéséhez.  

### <a name="uninstall"></a>Eltávolítás  

Az Intune-rendszergazdák az **Eltávolítás** használatával eltávolíthatják (visszaállítják) a legújabb *szolgáltatás* frissítését, vagy egy aktív vagy szüneteltetett frissítési kör legújabb *minőségi* frissítését. Egy típus eltávolítását követően eltávolíthatja a másik típust. Az Intune nem támogatja vagy nem felügyeli, hogy a felhasználók nem tudják eltávolítani a frissítéseket.  

> [!IMPORTANT] 
> Az *eltávolítási* lehetőség használatakor az Intune azonnal átadja az eltávolítási kérést az eszközöknek. 
> - A Windows-eszközök azonnal megkezdik a frissítések eltávolítását, amint megkapják az Intune-szabályzat módosításait. A frissítés eltávolítása nem korlátozódik a karbantartási ütemtervekre, még akkor is, ha azok a frissítési kör részeként vannak konfigurálva. 
> - Ha a frissítés eltávolításához az eszköz újraindítása szükséges, az eszköz újraindul, anélkül, hogy az eszköz felhasználóinak késleltetést kellene felajánlani.


Az Eltávolítás sikerességéhez:  
- Az eszköznek a Windows 10 április 2018 frissítést (1803-es verzió) vagy újabb verzióját kell futtatnia.  

Az eszköznek telepítenie kell a legújabb frissítést. Mivel a frissítések összegző jellegűek, a legújabb frissítést telepítő eszközök a legújabb szolgáltatás-és minőségi frissítést fogják tartalmazni. Ha ezt a lehetőséget választja, akkor az utolsó frissítés visszavonása előtt érdemes felderíteni a problémát a Windows 10-es gépeken.  

Az Eltávolítás használatakor vegye figyelembe a következőket:  
- A funkciófrissítések és minőségi frissítések eltávolításának lehetősége csak ahhoz a karbantartási csatornához érhető el, amelyhez az eszköz tartozik.  

- Ha a szolgáltatás vagy a minőségi frissítések eltávolítását használja, a a Windows 10-es gépek korábbi frissítésének visszaállítására szolgáló szabályzatot indít el.  

- Egy Windows 10-es eszközön a minőségi frissítés sikeres visszaállítását követően a végfelhasználók továbbra is megtekinthetik a **Windows beállításai** > **frissítések** > **frissítési előzmények**című témakörben felsorolt frissítést.  

- A szolgáltatások frissítéseinek kimondottan a szolgáltatás frissítésének elindításához szükséges idő 2-60 nap, a frissítési körök frissítési beállításának beállítása a **szolgáltatás frissítésének eltávolítási időtartama (2 – 60 nap)** . Az eszközre telepített szolgáltatás frissítése nem állítható vissza, ha a szolgáltatás frissítése a beállított eltávolítási időtartamnál hosszabb ideig van telepítve.  

  Tegyük fel például, hogy egy frissítési gyűrű egy 20 napos szolgáltatás-frissítési eltávolítási időszakmal rendelkezik. 25 nap elteltével állítsa vissza a legújabb funkció frissítését, és használja az Eltávolítás lehetőséget.  Azok az eszközök, amelyek több mint 20 nappal ezelőtt telepítették a szolgáltatást, nem tudják eltávolítani, mert a karbantartásuk részeként eltávolítottak a szükséges biteket. Azonban azok az eszközök, amelyek csak a 19 napos frissítést telepítették, eltávolíthatják a frissítést, ha sikeresen bejelentkeznek az eltávolítási parancs fogadására, mielőtt meghaladják a 20 napos eltávolítási időszakot.  

Windows Update házirendekkel kapcsolatos további információkért lásd: a [CSP frissítése](https://docs.microsoft.com/windows/client-management/mdm/update-csp) a Windows ügyfél-felügyeleti dokumentációjában.  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>A Windows 10 legújabb frissítésének eltávolítása  

1. Ha megtekinti a szüneteltetett frissítési kör áttekintés lapját, válassza az **Eltávolítás**lehetőséget.  
2. Válasszon az elérhető lehetőségek közül a **szolgáltatás** vagy a **minőségi** frissítések eltávolításához, majd kattintson **az OK gombra**.  
3. Miután elindította az eltávolítást egy frissítési típusra, az Eltávolítás lehetőség kiválasztásával távolítsa el a fennmaradó frissítési típust.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Frissítési beállítások áttelepítése a Azure Portalre  

A klasszikus Azure-portál néhány egyéb Windows 10-frissítési beállítást is tartalmaz az eszközkonfigurációs profilban. Ha ezen beállítások bármelyike konfigurálva van a Azure Portalra való áttelepítéskor, javasoljuk, hogy végezze el a következő műveleteket:  

1. Hozzon létre Windows 10 frissítési köröket az Azure Portalon a kívánt beállításokkal. Az **Előzetes funkciók engedélyezése** beállítást az Azure Portal nem támogatja, mert az már nem alkalmazható a legújabb Windows 10 buildekre. A frissítési körök létrehozásakor a másik három beállítást és a többi Windows 10 frissítési beállítást is konfigurálhatja.  

   > [!NOTE]  
   > A klasszikus portálon megadott Windows 10-frissítési beállítások nem jelennek meg az Azure Portalon az áttelepítés után. Ezek a beállítások azonban érvénybe lépnek. Ha a beállítások bármelyikét migrálja, majd módosítja az áttelepített szabályzatot az Azure Portalon, akkor ezek a beállítások törlődnek a szabályzatból.  

2. Törölje a frissítési beállításokat a klasszikus portálon. Az Azure Portalra történő migrálás és az azonos beállításoknak egy frissítési körben történő megadása után az esetleges szabályzat-ütközések elkerülése érdekében a beállításokat a klasszikus portálon törölni kell. Ha például ugyanaz a beállítás eltérő értékekkel van konfigurálva, ütközés van. Nem könnyű tudni, mert a klasszikus portálon konfigurált beállítás nem jelenik meg a Azure Portal.  

## <a name="next-steps"></a>További lépések

[Az Intune által támogatott Windows Update-beállítások](../windows-update-settings.md)  

[Intune-megfelelőségi jelentések a frissítésekhez](../windows-update-compliance-reports.md)

[A Windows 10 frissítési gyűrűk hibaelhárítása](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)
