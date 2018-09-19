---
title: Wi-Fi-beállítások Windows 10-es eszközökhöz a Microsoft Intune-ban – Azure | Microsoft Docs
description: Wi-Fi-konfigurációs profil hozzáadása vagy létrehozása a Wi-Fi-beállítások használatával Windows 10 és újabb rendszerű eszközökön a Microsoft Intune-ban. Konfigurálhat alapszintű vagy nagyvállalati szintű beállításokat.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e15a7b034c9277fcd960e8c704f4318f0f5c1da2
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329647"
---
# <a name="wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Wi-Fi-beállítások Windows 10 és újabb rendszerű eszközökhöz az Intune-ban

A Wi-Fi-beállítások Windows 10 és újabb rendszerű eszközökre érvényes konfigurációs profilokban vannak használva. A lehetőségek a következők:

- Egyszerű
- Vállalati

## <a name="before-you-begin"></a>Előkészületek

[Eszközprofil létrehozása](device-profile-create.md).

## <a name="settings-for-basic-and-enterprise-profiles"></a>Alapszintű és vállalati profilokban használható beállítások

- **Wi-Fi neve (SSID)**: A szolgáltatáskészlet-azonosító rövidítése. Ez az érték a valódi neve a vezeték nélküli hálózatnak, amelyhez az eszközök csatlakoznak. A felhasználók azonban csak a konfigurált **kapcsolatnevet** látják, amikor kiválasztják a kapcsolatot.
- **Kapcsolat neve**: Adja meg a Wi-Fi-kapcsolat felhasználóbarát nevét. Az ide beírt szöveg a felhasználók számára megjelenő név, amikor a rendelkezésre álló kapcsolatokat böngészik az eszközeiken.
- **Hatótávolságon belül automatikus csatlakozás**: Ha **Igen** értékre van állítva, akkor az eszközök automatikusan csatlakoznak, amikor ennek a hálózatnak a hatótávolságán belül vannak. Ha a beállítás **Nem**, akkor az eszközök nem csatlakoznak automatikusan.
  - **Lehetőség szerint csatlakozás egy előnyben részesített hálózathoz**: Ha az eszközök egy előnyben részesített hálózat hatókörében vannak, akkor **Igen** beállítás mellett azt fogják használni. Válassza a **Nem** beállítást, hogy az ebben a konfigurációs profilban lévő Wi-Fi-hálózatot használják.

    Tegyük fel, hogy létrehozott egy **ContosoCorp** nevű Wi-Fi-hálózatot, és a **ContosoCorp** hálózatot használja ebben a konfigurációs profilban. Elérhető távolságban van egy **ContosoGuest** nevű Wi-Fi-hálózat is. Azt szeretné, hogy ha céges eszközei hatókörön belül vannak, automatikusan a **ContosoCorphoz** csatlakozzanak. Ebben az esetben állítsa a **Lehetőség szerint csatlakozás egy előnyben részesített hálózathoz** tulajdonságot **Nem** értékre.

  - **Csatlakozás ehhez a hálózathoz akkor is, ha nem küld SSID-t**: Válassza az **Igen** beállítást a konfigurációs profilhoz, hogy akkor is automatikusan csatlakozzon a hálózatához, amikor a hálózat rejtett (tehát nem küldi szét nyilvánosan az SSID-ját). Válassza a **Nem** beállítást, ha nem szeretné, hogy ez a konfigurációs profil a rejtett hálózathoz csatlakozzon.

- **Vállalati proxybeállítások**: Válassza ki a vállalatán belül használni kívánt proxybeállításokat. A választható lehetőségek:
  - **Nincs**: Semmilyen proxybeállítás nincs konfigurálva.
  - **Manuálisan konfigurált**: Adja meg a **proxykiszolgáló IP-címét** és **portszámát**.
  - **Automatikusan konfigurált**: Adja meg egy proxy automatikus konfigurációs (PAC) parancsprogramjának URL-címét. Például írja be a következőt: `http://proxy.contoso.com/proxy.pac`.

## <a name="settings-for-basic-profiles-only"></a>Csak alapszintű profilokban használható beállítások

- **Vezeték nélküli biztonság típusa**: Adja meg a hálózatán az eszközök hitelesítésére használt biztonsági protokollt. Az alábbi lehetőségek állnak rendelkezésére:
  - **Nyitott (nincs hitelesítés)**: Csak akkor válassza ezt a lehetőséget, ha a hálózat nem védett.
  - **WPA/WPA2-Personal**

## <a name="settings-for-enterprise-profiles-only"></a>Csak vállalati profilokban használható beállítások

- **Egyszeri bejelentkezés (SSO)**: Lehetővé teszi az egyszeri bejelentkezés (SSO) konfigurálását. Ekkor ugyanazok a hitelesítő adatok szolgálnak a számítógépre és a Wi-Fi-hálózatba való bejelentkezésre. Az alábbi lehetőségek állnak rendelkezésére:
  - **Letiltás** Letiltja az SSO viselkedést. A felhasználónak külön kell hitelesítenie magát a hálózaton.
  - **Engedélyezés mielőtt a felhasználó bejelentkezik az eszközre**: Az SSO használata a hálózaton való hitelesítésre közvetlenül a felhasználói bejelentkezés előtt.
  - **Engedélyezés miután a felhasználó bejelentkezik az eszközre**: Az SSO használata a hálózaton való hitelesítésre közvetlenül azután, hogy a felhasználói bejelentkezés befejeződik.
  - **A hitelesítésre rendelkezésre álló időkorlát**: Adja meg másodpercben a maximális várakozási időt (1 és 120 másodperc között) a hálózatban történő hitelesítés előtt.
  - **A Windows további hitelesítő adatokat kérhet a felhasználótól**: **Igen** beállítással a Windows rendszer további hitelesítő adatokat kérhet a felhasználótól, ha a hitelesítési módszer ezt megköveteli. A **Nem** beállítás elrejti ezeket a kéréseket.

- **Páros főkulcs (PMK) gyorsítótárazásának engedélyezése**: Állítsa **Igen** értékre a hitelesítéshez használt PMK gyorsítótárazásához. Ez a gyorsítótárazás általában gyorsabb hálózati hitelesítést tesz lehetővé. A **Nem** beállítással megkövetelheti a hitelesítési kézfogást a Wi-Fi-hálózathoz való minden kapcsolódáskor.

  - **PMK megőrzésének maximális időtartama a gyorsítótárban**: Adja meg a percek számát (5 és 1440 között), amíg a páros főkulcs (PMK) tárolva lesz a gyorsítótárban.
  - **A gyorsítótárban tárolt PMK-k maximális száma**: Adja meg a gyorsítótárban tárolt kulcsok számát 1 és 255 között.

- **Előhitelesítés engedélyezése**: Előhitelesítéssel a profil a hozzá tartozó hálózat összes hozzáférési pontján hitelesítheti magát csatlakozás előtt. Ha a felhasználók illetve az eszközök mozognak a hozzáférési pontok között, az előhitelesítés meggyorsítja az újracsatlakozást. **Igen** beállítással a profil a hálózat összes hatótávolságon belüli hozzáférési pontján hitelesíti magát. **Nem** beállítással a felhasználónak vagy eszköznek minden hozzáférési ponton külön kell hitelesítenie.

  - **Előhitelesítési kísérletek maximális száma**: Adja meg az előhitelesítési próbálkozások számát 1 és 16 között.

- **EAP típusa**: Válassza ki az EAP protokoll biztonságos vezeték nélküli kapcsolatok hitelesítéséhez használni kívánt típusát. A választható lehetőségek:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Védett EAP** (PEAP)

    **EAP-TLS, EAP-TTLS és PEAP további beállításai**:
    
    > [!NOTE]
    > EAP-típusok használata esetén jelenleg csak az SCEP-tanúsítványprofilok támogatottak. A PKCS-tanúsítványprofilok nem támogatottak. Amikor egy felhasználótól tanúsítvány megadását kérik, mindenképpen SCEP-tanúsítványt kell választani.

      - **Kiszolgáló megbízhatósága**  

        **Tanúsítvány-kiszolgálók nevei**: **EAP-TLS**, **EAP-TTLS** vagy **PEAP** EAP-típusokkal használható. Adjon meg egy vagy több, a megbízható hitelesítésszolgáltató (CA) által kiállított tanúsítványban használt köznapi nevet. Ha megadja ezt az információt, elkerülheti a dinamikus megbízhatósági párbeszédpanelt, amely megjelenik a felhasználók eszközein, amikor ehhez a Wi-Fi-hálózathoz csatlakoznak.  

        **Gyökértanúsítvány kiszolgálóhitelesítéshez**: **EAP-TLS**, **EAP-TTLS** vagy **PEAP** EAP-típusokkal használható. Válassza ki a kapcsolat hitelesítéséhez használni kívánt megbízható főtanúsítvány-profilt.  

        **Identitásadatok védelme (külső identitás)**: **PEAP** EAP-típussal használható. Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.  

      - **Ügyfél-hitelesítés**

        **Ügyfél-hitelesítéshez használandó ügyféltanúsítvány (identitástanúsítvány)**: **EAP-TLS** EAP-típussal használható. Válassza ki a kapcsolat hitelesítéséhez használni kívánt tanúsítványprofilt.

        **Hitelesítési módszer**: **EAP-TTLS** EAP-típussal használható. Válassza ki a kapcsolat hitelesítési módszerét:  

          - **Tanúsítványok**: Válassza ki a kiszolgálónak az identitás tanúsítványaként benyújtott ügyféltanúsítványt.
          - **Felhasználónév és jelszó**: Adjon meg egy **nem-EAP módszert (belső identitás)** a hitelesítéshez. A választható lehetőségek:

            - **Titkosítatlan jelszó (PAP)**
            - **Kérdés-kézfogás (CHAP)**
            - **Microsoft CHAP (MS-CHAP)**
            - **Microsoft CHAP 2-es verzió (MS-CHAP v2)**

        **Identitásadatok védelme (külső identitás)**: **EAP-TTLS** EAP-típussal használható. Adja meg az EAP-identitásra irányuló kérelemre adott válasz szövegét. Ez a szöveg tetszőleges érték lehet. A hitelesítés során a rendszer először a névtelen identitást küldi el, majd később egy biztonságos csatornán küldi el a valódi azonosítót.

- **A Wi-Fi-profil Federal Information Processing Standard (FIPS) szabványnak való megfelelésének a kényszerítése**: Válassza az **Igen** lehetőséget, ha a FIPS 140-2 szabvány szerinti érvényességet ellenőrzi. Ennek a szabványnak a betartása kötelező az összes Egyesült Államokbeli Szövetségi kormányzati szerv részére, ahol titkosításon alapuló biztonsági rendszereket használnak a digitálisan tárolt bizalmas, de nem titkos minősítésű információk tárolására. Válassza a **Nem** lehetőséget, ha nem szeretne FIPS-megfelelőséget.

## <a name="use-an-imported-settings-file"></a>Importált beállításfájl használata

Az Intune-ban nem elérhető összes beállításhoz exportálhatja a Wi-Fi-beállításokat egy másik windowsos eszközből. Az exportálás az összes beállítást tartalmazó XML-fájlt hoz létre. Ez után importálja ezt a fájlt az Intune-ba, és használja Wi-Fi-profilként. Lásd: [Wi-Fi-beállítások exportálása és importálása Windows rendszerű eszközökhöz](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>További lépések
[Wi-Fi-beállítások konfigurálása az Intune-ban](wi-fi-settings-configure.md)