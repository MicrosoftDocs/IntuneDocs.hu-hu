---
title: "Mobileszközökre vonatkozó Exchange-hozzáférési szabályok | Microsoft Intune"
description: "Exchange ActiveSync hozzáférési szabályok EAS-eszközök kapcsolódásának engedélyezéséhez vagy letiltásához"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c49e19e8c478af252d7b59c380d5500a57b71db5
ms.openlocfilehash: 7714a338d02afedde2ac090964e4d18d4410a80e


---

# Mobileszközökre vonatkozó Exchange-hozzáférési szabályok
A mobileszközökre vonatkozó Exchange-hozzáférési szabályok határozzák meg az eszközök az Exchange ActiveSync-hez való hozzáférésnek szintjét. Ezek a beállítások minden mobileszközre hatással vannak, a Microsoft Intune-ban nem regisztrált eszközöket is beleértve. Kiindulásképpen meghatározhat egy **alapértelmezett szabályt** , amely minden olyan mobileszközre érvényes lesz, amelyre nem alkalmaztak egyéni szabályt. Az alábbi táblázat az Exchange ActiveSync által felügyelt hozzáférési szinteket tartalmazza:

|Hozzáférési szint|Leírás|
|----------------|---------------|
|**Az eszközök hozzáférhetnek az Exchange-hez**|Az *engedélyezett hozzáférés* állapotában a mobileszköz szinkronizálhat az Exchange ActiveSynckel, és kapcsolódhat az Exchange-kiszolgálóhoz az e-mailek lekérése, valamint a Naptár, a Névjegyek, a Feladatok és a Megjegyzések kezelése céljából. Ez mindaddig így marad, amíg az eszköz megfelel valamely, az Exchange-ben korábban konfigurált Exchange ActiveSync postaláda-házirendnek, kivéve, ha a felhasználót vagy az adott mobileszközt az Exchange-rendszergazda letiltotta.|
|**Az eszközök nem férhetnek hozzá az Exchange-hez**|A *letiltott hozzáférés* állapotában a mobileszközök le vannak tiltva, és az Exchange-kiszolgálóhoz való kapcsolódásuk nem engedélyezett. Az eszközök egy HTTP 403 Tiltott hibaüzenetet kapnak. A felhasználó egy e-mailt kap az Exchange-kiszolgálótól, amely értesíti, hogy a mobileszköz postaládához való hozzáférése le van tiltva. Ez az üzenet a zárolt mobileszközön nem jelenhet meg. A **Felhasználóértesítés beállítása** feladatban egyéni szöveget adhat hozzá ehhez az üzenethez, és utasításokkal láthatja el a felhasználókat, akiknek az eszközei le lettek tiltva.|
|**Az eszközök karanténba helyezése, hogy később engedélyezni vagy blokkolni lehessen őket**|Amikor egy mobileszköz karanténban van, hozzáférhet az Exchange-kiszolgálóhoz. Az adatokhoz való hozzáférése azonban korlátozott. A felhasználó hozzáadhat tartalmat a saját Naptár, Névjegyek, Feladatok és Megjegyzések mappáihoz, de a kiszolgáló nem engedélyezi, hogy az eszköz bármilyen tartalmat lekérjen a felhasználó postaládájából. A felhasználót a mobileszköz karanténba helyezéséről egy e-mail értesíti. Ez az üzenet az eszközön és a felhasználó postaládájában is megjelenik. A **Felhasználói értesítés beállítása** feladatban egyéni szöveget adhat hozzá ehhez az üzenethez, és utasításokkal láthatja el azokat a felhasználókat, akiknek az eszközei karanténba lettek helyezve.|

A hozzáférési stratégia egy **alapértelmezett szabály** és az **platformkivételek** kombinációját jelenti, amely minden, az Exchange-hez csatlakozó mobileszközre érvényes. Az alábbi táblázat felsorol néhány példát a hozzáférési stratégiákra.

|Hozzáférési stratégia|Leírás|
|-------------------|---------------|
|Engedélyezési lista|Az *engedélyezési listák* segítségével hozzáférést biztosíthat bizonyos ismert eszközöknek, míg minden más eszköz hozzáférését korlátozhatja. Ehhez egyéni szabályokat kell létrehozni, hogy a kívánt eszközplatformok hozzáférjenek a felhasználók postaládáihoz. Miután egy ilyen szabályt létrehozott, az alapértelmezett hozzáférési szabályt úgy kell beállítania, hogy az letiltson vagy karanténba helyezzen minden egyéb eszközt. Egy új eszköz engedélyezési listához való hozzáadásához hozzon létre egy új egyéni szabályt|
|Tiltólista|A *tiltólisták* segítségével alapértelmezés szerint engedélyezheti a hozzáférést minden eszköznek, de letilthatja azon eszközök hozzáférését, amelyeknél nem szeretné, hogy hozzáférjenek a szervezetéhez. Tiltólistát egyéni szabályok megalkotásával lehet létrehozni, amelyek letiltják azokat a platformokat, amelyek számára nem szeretné lehetővé tenni a szervezet postaládáival való szinkronizálást. Az alapértelmezett szabályt úgy kell beállítani, hogy engedélyezze a hozzáférést minden olyan eszköznek, amelyet a meglévő szabályok nem kifejezetten tiltanak. Új eszköz vagy eszközök tiltólistához való hozzáadásához hozzon létre egy új egyéni szabályt.|
|Vegyes engedélyezés és tiltás|Az engedélyezési és tiltólistákon felül karanténba is helyezheti az új mobileszközöket a szervezetbe való belépéskor addig, amíg értékeli őket. Ha például van egy tiltólistája azokról az eszközökről, amelyeket nem engedélyez a szervezetén belül, és van egy engedélyezési listája azokról, amelyeknek engedélyezi a hozzáférést, akkor alapértelmezett szabályként megadhatja a karantént. Minden egyéb eszköz automatikusan karanténba kerül. Ez lehetővé teszi, hogy megismerje az új eszközöket, amikor a szervezetbe belépnek, és eldöntse, hogy az engedélyezési vagy a tiltólistához adja-e őket.|
Az alábbi eljárás bemutatja egy egyéni szabály létrehozásának folyamatát.

## Alapértelmezett hozzáférési szabály létrehozása

1.  Kattintson a [Microsoft Intune felügyeleti konzol](http://manage.microsoft.com) &gt; **Házirend** &gt; **Exchange ActiveSync** elemére.

2.  Az **Alapértelmezett szabály** listában válassza ki azt az alapértelmezett szabályt, amelyet minden olyan mobileszközre alkalmazni kíván, amelyre nem vonatkozik szabály vagy személyes kivétel. Válassza a **Mentés** elemet.

Az alábbi eljárás bemutatja egy egyéni szabály létrehozásának folyamatát.

## Egyéni hozzáférési szabály létrehozása

1. Kattintson a [Microsoft Intune felügyeleti konzol](http://manage.microsoft.com) &gt; **Házirend** &gt; **Exchange ActiveSync** elemére.

2.  Kattintson a **Platformkivételek** lista **Szabály hozzáadása** elemére, majd hozzon létre egy egyéni szabályt. Válassza a **Mentés** elemet.



<!--HONumber=Aug16_HO1-->

