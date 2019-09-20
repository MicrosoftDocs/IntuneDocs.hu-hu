---
title: SCEP-tanúsítványok profiljainak használata az Microsoft Intune-Azure-ban | Microsoft Docs
description: Hozzon létre és rendeljen Egyszerű tanúsítványigénylési protokoll-(SCEP-) tanúsítvány-profilokat Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e553229530f826ead91be981ff446b7cb3ebbf2
ms.sourcegitcommit: 7269abaefb2857bc8b343896bb2138bdb01bf8dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70214279"
---
# <a name="create-and-assign-scep-certificate-profiles-in-intune"></a>SCEP-tanúsítványok létrehozása és társítása az Intune-ban

Miután [konfigurálta az infrastruktúrát](certificates-scep-configure.md) a egyszerű tanúsítványigénylési protokoll-(SCEP-) tanúsítványok támogatásához, létrehozhat és hozzárendelhet SCEP-tanúsítványokat a felhasználók és az eszközök számára az Intune-ban.

> [!IMPORTANT]  
> A SCEP létrehozása előtt a SCEP-tanúsítványt használó eszközöknek megbízható legfelső szintű hitelesítésszolgáltatót (CA) kell megbízniuk. Az Intune *megbízható tanúsítvány-profiljának* használatával kiépítheti a megbízható legfelső szintű hitelesítésszolgáltatói tanúsítványt a felhasználóknak és az eszközöknek a megbízható tanúsítvány profiljával kapcsolatos információkért lásd: [a megbízható legfelső szintű hitelesítésszolgáltatói tanúsítvány exportálása](certificates-configure.md#export-the-trusted-root-ca-certificate) és [megbízható tanúsítvány létrehozása a profilok](certificates-configure.md#create-trusted-certificate-profiles) a *tanúsítványok használata az Intune-ban történő hitelesítéshez*.


## <a name="create-a-scep-certificate-profile"></a>SCEP-tanúsítványprofil létrehozása

1. Jelentkezzen be az [Intune-portálra](https://aka.ms/intuneportal).
2. Válassza az **Eszközkonfiguráció** > **Profilok** > **Profil létrehozása** lehetőséget.
3. Adja meg az SCEP-tanúsítványprofil **nevét** és **leírását**.
4. A **platform** legördülő listából válassza ki a SCEP-tanúsítvány [támogatott eszköz-platformját](certificates-configure.md#supported-platforms-and-certificate-profiles) . 
5. A **Profil típusa** legördülő listában válassza az SCEP- **tanúsítvány**lehetőséget.  

   > [!NOTE]  
   > Az **Android Enterprise** platform esetében a *Profil típusa* két kategóriára oszlik: Csak az *eszköz tulajdonosa* és a *munkahelyi profil*.  A SCEP csak *munkahelyi profil*esetén támogatottak.

6. Válassza a **Beállítások**lehetőséget, majd hajtsa végre a következő konfigurációkat:

   - **Tanúsítvány típusa**:   
     *(A következőkre vonatkozik:  Android, Android Enterprise, iOS, macOS, Windows 8,1 és újabb, valamint Windows 10 és újabb verziók.)*  

      Válasszon egy típust attól függően, hogy hogyan fogja használni a tanúsítványt:
      - **Felhasználó**: A *felhasználói* tanúsítványok a tulajdonos és a tanúsítvány Tárolóhálózati felhasználói és eszköz attribútumait is tartalmazhatják.  
      - **Eszköz**:  Az *eszközök* tanúsítványainak csak a tulajdonos és a tanúsítvány Tárolóhálózati attribútumait tartalmazhatják.  
      
        **Eszköz** használata olyan forgatókönyvek esetén, mint a felhasználó nélküli eszközök, például kioszkok vagy Windows-eszközök. Windows-eszközökön a tanúsítvány a helyi számítógép tanúsítványtárolóba kerül.  

   - **Tulajdonos nevének formátuma**:  
     Válassza ki, hogy az Intune hogyan hozza létre automatikusan a tulajdonos nevét a tanúsítványkérelmet. A tulajdonos nevének formátumára vonatkozó beállítások a kiválasztott tanúsítvány típusától függenek, a **felhasználótól** vagy az **eszköztől**.  

     > [!NOTE]  
     > [Ismert hiba](#avoid-certificate-signing-requests-with-escaped-special-characters) történt a SCEP használatával a tanúsítványok lekéréséhez, ha az eredményül kapott tanúsítvány-aláírási kérelem (CSR) tulajdonos neve a következő karakterek egyikét tartalmazza Escape-karakterként (fordított perjel \\):
     > - \+
     > - ;
     > - ;
     > - =

     - **Felhasználói tanúsítványtípus**  
       A *tulajdonos nevének formátumára* vonatkozó beállítások a következők:  
       - **Nincs konfigurálva**
       - **Köznapi név**
       - **Köznapi név (e-mail is)**
       - **Köznapi név mint e-mail cím**
       - **IMEI (Nemzetközi mobilkészülék-azonosító)**
       - **Sorozatszám**
       - **Egyéni**: Ha ezt a beállítást választja, egy **Egyéni** szövegmező is megjelenik. Ezt a mezőt egyéni tulajdonosnév-formátumok megadásához használhatja, beleértve a változókat is. Az egyéni formátum két változót támogat: **Köznapi név (CN)** és **e-mail (E)** . Az **Egyszerű név (CN)** az alábbi változók bármelyikére beállítható:

         - **CN = {{username}}** : A felhasználó egyszerű felhasználóneve, például janedoe@contoso.com:.
         - **CN={{AAD_Device_ID}}** : Az eszköz Azure Active Directory (AD) szolgáltatásban való regisztrálásakor hozzárendelt azonosító. Ez az azonosító jellemzően az Azure AD-ben való hitelesítéshez használatos.
         - **CN = {{SERIALNUMBER}}** : Az egyedi sorozatszámot (SN) általában a gyártó használja az eszköz azonosítására.
         - **CN = {{IMEINumber}}** : A mobil telefon azonosítására szolgáló nemzetközi mobileszköz-azonosító (IMEI) egyedi szám.
         - **CN = {{OnPrem_Distinguished_Name}}** : Relatív megkülönböztető nevek sorozata vesszővel elválasztva, például *CN = Jane Doe, OU = UserAccounts, DC = Corp, DC = contoso, DC = com*.

           A ( *onpremisesdistinguishedname* ) *{{OnPrem_Distinguished_Name}}* változó használatához az Azure AD-vel a [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) használatával kell szinkronizálnia a felhasználói attribútumot.

         - **CN={{onPremisesSamAccountName}}** : A rendszergazdák a samAccountName attribútumot a Active Directoryról az Azure AD-be szinkronizálva az Azure AD-kapcsolat használatával egy *onPremisesSamAccountName*nevű attribútumba. Az Intune a tanúsítvány kiállításának részeként helyettesítheti be ezt a változót. A samAccountName attribútum a Windows korábbi verziójából származó ügyfelek és kiszolgálók támogatásához használt felhasználói bejelentkezési név (pre-Windows 2000). A felhasználói bejelentkezési név formátuma: *DomainName\testUser*vagy csak *tesztfelhasználó*.

            A ( *onPremisesSamAccountName* ) *{{onPremisesSamAccountName}}* változó használatához az Azure AD-vel a [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) használatával kell szinkronizálnia a felhasználói attribútumot.

         Egy vagy több változó és statikus sztringek együttes használatával létrehozhat egyéni tulajdonosnév-formátumokat, például a következőhöz hasonlót:  
         - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
            
        Ez a példa egy tulajdonos nevének formátumát tartalmazza, amely a CN és az E változókat, valamint a szervezeti egység, szervezet, hely, állam és ország értékek karakterláncait használja. A függvény leírását és a támogatott sztringeket a [CertStrToName függvény](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) című cikkben találhatja meg.

      - **Eszköz tanúsítványtípus**  
        A tulajdonos nevének formátumára vonatkozó beállítások a következő változókat tartalmazzák: 
        - **{{AAD_Device_ID}}**
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{AzureADDeviceId}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}** *(Csak Windows és tartományhoz csatlakoztatott eszközök esetén alkalmazható)*
        - **{{MEID}}**
        
        Megadhatja ezeket a változókat, majd a változó szövegét a szövegmezőben. Egy *Device1* nevű eszköz köznapi neve például a következő lehet: **CN = {{DeviceName}} Device1**.

        > [!IMPORTANT]  
        > - Ha változót ad meg, a hiba elkerüléséhez tegye a változó nevét kapcsos zárójelben ({}) a példában látható módon.  
        > - Az eszköz *tulajdonosának* vagy *San* -tanúsítványának (például **IMEI**, **serialnumber**és **FullyQualifiedDomainName**) használt tulajdonságai olyan tulajdonságok, amelyek az eszközhöz hozzáféréssel rendelkező személy által meghamisítható.
        > - Egy eszköznek támogatnia kell az adott profilhoz tartozó tanúsítvány-profilban megadott összes változót az adott eszközre való telepítéshez.  Ha például a **{{IMEI}}** egy SCEP-profil tulajdonos nevében van használatban, és olyan eszközhöz van rendelve, amely nem rendelkezik IMEI-számmal, akkor a profilt nem lehet telepíteni.  
 


   - **Tulajdonos alternatív neve**:  
     Válassza ki, hogy az Intune hogyan hozza létre automatikusan a tulajdonos alternatív nevét (SAN) a tanúsítványkérelem során. A TÁROLÓHÁLÓZATI beállítások a kiválasztott tanúsítvány típusától függenek; vagy **felhasználó** vagy **eszköz**.  

      - **Felhasználói tanúsítványtípus**  
        Válasszon az elérhető attribútumok közül:  
        - **E-mail cím**
        - **Egyszerű felhasználónév (UPN)** 

        A felhasználói tanúsítványok típusai például tartalmazhatják az egyszerű felhasználónevet (UPN) a tulajdonos alternatív neve mezőben. Ha az ügyféltanúsítványt egy hálózati házirend-kiszolgálón történő hitelesítésre használja, a tulajdonos alternatív neveként az egyszerű felhasználónevet (UPN) állítsa be.

      - **Eszköz tanúsítványtípus**  
        Használja az **attribútum** legördülő menüt, válasszon ki egy attribútumot, rendeljen hozzá egy **értéket**, és **vegye fel** azt a tanúsítvány profiljába. További attribútumok kiválasztásával több értéket is hozzáadhat.  

        Az elérhető attribútumok a következők:
        - **E-mail cím**
        - **Egyszerű felhasználónév (UPN)**
        - **DNS**

        Az *Eszköz* tanúsítványtípusnál a következő eszköztanúsítvány-változókat használhatja az értékhez:  

        - **{{AAD_Device_ID}}**
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{AzureADDeviceId}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}**
        - **{{MEID}}**

        Egy attribútum értékének megadásához adja meg a változó nevét kapcsos zárójelekkel, majd a változó szövegét. A DNS-attribútum értéke például a következő lehet: **{{AzureADDeviceId}}. domain. com** , ahol a *. domain.com* a szöveg. A *Felhasználó1* nevű felhasználóhoz tartozó e-mail-cím {{FullyQualifiedDomainName}}User1@Contoso.comnéven jelenhet meg.  

        > [!IMPORTANT]  
        > - Az eszköz tanúsítványa változó használatakor a változó neve kapcsos zárójelben {}.  
        > - Ne használjon kapcsos zárójeleket **{}** , cső szimbólumokat **|** és pontosvesszőket **, a**változót követő szövegben.  
        > - Az eszköz *tulajdonosának* vagy *San* -tanúsítványának (például **IMEI**, **serialnumber**és **FullyQualifiedDomainName**) használt tulajdonságai olyan tulajdonságok, amelyek az eszközhöz hozzáféréssel rendelkező személy által meghamisítható.  
        > - Egy eszköznek támogatnia kell az adott profilhoz tartozó tanúsítvány-profilban megadott összes változót az adott eszközre való telepítéshez.  Ha például a **{{IMEI}}** egy SCEP-profil San-ban van használatban, és olyan eszközhöz van rendelve, amely nem rendelkezik IMEI-számmal, akkor a profilt nem lehet telepíteni.

   - **Tanúsítvány érvényességi időtartama**:  
     A tanúsítványsablonban megadott érvényességi időtartamnál rövidebb értéket is beállíthat, hosszabbat azonban nem. Ha úgy konfigurálta a tanúsítványsablont, hogy [támogassa az Intune-konzolon belül beállítható egyéni értéket](certificates-scep-configure.md#modify-the-validity-period-of-the-certificate-template), ezzel a beállítással megadhatja a tanúsítvány lejárata előtt hátralévő idő mennyiségét.  

     Ha például a tanúsítványsablonban két év van meghatározva a tanúsítvány érvényességi idejeként, akkor egy évet állíthat be értékként, öt évet azonban nem. Az értéknek emellett a kiállító hitelesítésszolgáltató tanúsítványának hátralévő érvényességi időszakánál is kevesebbnek kell lennie.

   - **Kulcstároló-szolgáltató (KSP)** :  
     *(A következőkre vonatkozik:  Windows 8,1 és újabb verziók, valamint Windows 10 és újabb verziók)*  
     
     Itt adhatja meg, hogy a rendszer hol tárolja a tanúsítvány kulcsát. Válasszon a következő értékek közül:  
     - **Regisztrálás a platformmegbízhatósági modul kulcstároló-szolgáltatójába (ha van ilyen), máskülönben regisztrálás a szoftverkulcstároló-szolgáltatóba**
     - **Regisztrálás a platformmegbízhatósági modul kulcstároló-szolgáltatójába, máskülönben a művelet sikertelen**
     - **Regisztrálás a Passportba, máskülönben a művelet sikertelen (Windows 10 és újabb verzió)**
     - **Regisztrálás szoftverkulcstároló-szolgáltatóba**

   - **Kulcshasználat**:  
     Válassza ki a tanúsítvány kulcshasználat beállításait:

     - **Digitális aláírás**: Kulcscsere engedélyezése csak akkor, ha egy digitális aláírás segíti a kulcs megvédését.
     - **Kulcs titkosítási**: Kulcscsere engedélyezése csak akkor, ha a kulcs titkosítva van.  

   - **Kulcs mérete (BITS)** :  
     Válassza ki a kulcsban található bitek számát.  

   - **Kivonatoló algoritmus**:  
     *(Az Android, az Android Enterprise, a Windows Phone-telefon 8,1, a Windows 8,1 és az újabb verziók, valamint a Windows 10 és újabb verziókra vonatkozik)*  

     Jelölje ki a tanúsítvánnyal használni kívánt kivonatoló algoritmust a rendelkezésre álló típusok közül. Válassza a kapcsolódó eszközöknél használható legerősebb biztonsági szintet.

   - **Főtanúsítvány**:  
     Válassza ki a korábban konfigurált és a megfelelő felhasználókhoz és eszközökhöz hozzárendelt *megbízható tanúsítvány-profilt* ehhez a SCEP-profilhoz. A megbízható tanúsítvány profilja a felhasználók és az eszközök kiépítésére szolgál a megbízható legfelső szintű HITELESÍTÉSSZOLGÁLTATÓI tanúsítvánnyal. A megbízható tanúsítvány profiljával kapcsolatos információkért lásd: [a megbízható legfelső szintű hitelesítésszolgáltatói tanúsítvány exportálása](certificates-configure.md#export-the-trusted-root-ca-certificate) és [megbízható tanúsítvány-profilok létrehozása](certificates-configure.md#create-trusted-certificate-profiles) a *tanúsítványok használata a hitelesítéshez az Intune-ban*. Ha rendelkezik legfelső szintű hitelesítésszolgáltatóval és egy kiállító hitelesítésszolgáltatóval, válassza ki a kiállító hitelesítésszolgáltatóhoz társított megbízható főtanúsítvány-profilt.

   - **Kibővített kulcshasználat**:  
     Adja hozzá az értékeket a tanúsítvány felhasználási céljához. A legtöbb esetben a tanúsítványhoz az *ügyfél-hitelesítés* szükséges, hogy a felhasználó vagy az eszköz hitelesíthető legyen egy kiszolgálóval. Szükség szerint további kulcshasználat hozzáadására is lehetőség van.

   - **Megújítási küszöb (%)** :  
     Adja meg a tanúsítvány élettartamának azon hányadát, amely még azelőtt marad, amíg az eszköz kérelmezi a tanúsítvány megújítását. Ha például a 20 értéket adja meg, a rendszer megkísérli a tanúsítvány megújítását, ha a tanúsítvány 80%-ban lejár, és a rendszer továbbra is megkísérli a megújítás sikerességét. A megújítás új tanúsítványt hoz létre, amely új nyilvános/titkos kulcspár bevonását eredményezi.

   - **SCEP-kiszolgáló URL-címei**:  
     Adjon meg egy vagy több URL-címet azon NDES-kiszolgálók esetében, amelyek tanúsítványokat állítanak ki a SCEP használatával. Adja meg például az alábbihoz *https://ndes.contoso.com/certsrv/mscep/mscep.dll* hasonlót:. Szükség szerint további SCEP URL-címeket is hozzáadhat a terheléselosztáshoz, mivel az URL-címeket a rendszer véletlenszerűen leküldi az eszközre a profil használatával. Ha az egyik SCEP-kiszolgáló nem érhető el, a SCEP-kérelem sikertelen lesz, és lehetséges, hogy a későbbi eszköz-bejelentkezések esetében a tanúsítvány kérése ugyanarra a kiszolgálóra kerül.

7. Válassza **az OK**, majd a **Létrehozás**lehetőséget. Ekkor létrejön a profil, és megjelenik az *eszköz konfigurációja-profilok* listán.

### <a name="avoid-certificate-signing-requests-with-escaped-special-characters"></a>A tanúsítvány-aláírási kérelmek elhagyása Escape-speciális karakterekkel
Létezik egy ismert probléma a tulajdonos nevét (CN) tartalmazó SCEP, amely egy vagy több következő speciális karakterből áll Escape-karakterként. Azok a tulajdonosi nevek, amelyek a speciális karakterek egyikét tartalmazzák Escape-karakterként, helytelen tulajdonosi névvel rendelkező CSR-t eredményeznek, ami viszont az Intune SCEP-kérdés ellenőrzésének sikertelenségét eredményezi, és nem állít ki tanúsítványt.  

A speciális karakterek a következők:
- \+
- ;
- ;
- =

Ha a tulajdonos neve tartalmaz egy speciális karaktert, a következő lehetőségek közül választhat a korlátozás megkerüléséhez:  
- A speciális karaktert idézőjelekkel tartalmazó CN-érték beágyazása.  
- Távolítsa el a speciális karaktert a CN-értékből.  

**Például**van egy tulajdonos neve, amely a *test User (TestCompany, LLC)* néven jelenik meg.  A *TestCompany* és az *LLC* közötti vesszőt tartalmazó CN-t magában foglaló CSR-ben problémát jelent.  A probléma elkerülhető úgy, hogy idézőjeleket helyez a teljes CN-re, vagy eltávolítja a vesszőt a *TestCompany* és az *LLC*-ből:
- **Idézőjelek hozzáadása**: *CN =* "test User (TESTCOMPANY, LLC)", OU = USERACCOUNTS, DC = Corp, DC = contoso, DC = com *
- **Távolítsa el a vesszőt**: *CN = test User (TestCompany LLC), OU = UserAccounts, DC = Corp, DC = contoso, DC = com*

 Ha azonban a vesszőt egy fordított perjel karakterrel próbálja meg elmenekülni, a rendszer hibát jelez a CRP-naplókban:  
- **Megszökött vessző**: *CN = test User (TestCompany\\, LLC), OU = UserAccounts, DC = Corp, DC = contoso, DC = com*

A hiba a következő hibához hasonló: 

```
Subject Name in CSR CN="Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com" and challenge CN=Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com do not match  

  Exception: System.ArgumentException: Subject Name in CSR and challenge do not match

   at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

Exception:    at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

   at Microsoft.ConfigurationManager.CertRegPoint.Controllers.CertificateController.VerifyRequest(VerifyChallengeParams value
```

## <a name="assign-the-certificate-profile"></a>A tanúsítványprofil eszközökhöz rendelése
A SCEP-profilokat ugyanúgy rendelheti hozzá, mint az [eszközök profiljait](device-profile-assign.md) más célokra. A folytatás előtt azonban vegye figyelembe a következőket:

- Amikor SCEP rendel a csoportokhoz, a megbízható legfelső szintű HITELESÍTÉSSZOLGÁLTATÓI tanúsítvány fájlja (a *megbízható tanúsítvány profiljában*megadott) telepítve van az eszközön. Az eszköz a SCEP tanúsítvány-profilt használja a megbízható legfelső szintű HITELESÍTÉSSZOLGÁLTATÓI tanúsítványhoz tartozó tanúsítványkérelem létrehozásához.  

- Az SCEP-tanúsítvány profilja csak a tanúsítvány profiljának létrehozásakor megadott platformot futtató eszközökre telepíthető.

- Tanúsítványprofilokat rendelhet felhasználógyűjteményekhez és eszközgyűjteményekhez is.

- Ha azt szeretné, hogy a tanúsítványok gyorsan megjelenjenek az eszközökön a regisztráció után, a tanúsítványprofilt felhasználócsoporthoz és ne eszközcsoporthoz rendelje hozzá. Ha eszközcsoporthoz rendel hozzá, akkor teljes eszközregisztráció szükséges, mielőtt az eszköz megkaphatná a szabályzatokat.  

- Ha az Intune és a Configuration Manager együttes felügyeletét használja, akkor a Configuration Manager az **Intune** - **hoz vagy az Intune-hoz**tartozó erőforrás-hozzáférési szabályzat [munkaterhelésének csúszkáját állítsa be](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads) . Ez a beállítás lehetővé teszi, hogy a Windows 10-ügyfelek elindítsák a tanúsítvány kérelmezésének folyamatát.

- Bár a megbízható tanúsítvány profilját és a SCEP-tanúsítvány profilját külön hozza létre és rendeli hozzá, mindkettőt hozzá kell rendelni. Az SCEP-tanúsítvány házirendje nem működik együtt az eszközön. Győződjön meg arról, hogy a megbízható főtanúsítvány-profilok is ugyanarra a csoportra vannak telepítve, mint a SCEP-profil.


> [!NOTE]
> IOS-eszközökön, amikor egy SCEP-tanúsítvány profilja egy további profillal van társítva, például Wi-Fi-vagy VPN-profilhoz, az eszköz megkapja a további profilok tanúsítványát. Ez azt eredményezi, hogy az iOS-eszközön több tanúsítvány is érkezik az SCEP-tanúsítványkérelem által.  Ha egyetlen tanúsítványra van szükség, a SCEP-tanúsítványok helyett PKCS-tanúsítványokat kell használnia.  Ennek az az oka, hogy a SCEP és a PKCS-tanúsítványok eszközökre való kézbesítésének eltérései a következők:


## <a name="next-steps"></a>További lépések  

[Profilok hozzárendelése](device-profile-assign.md)  