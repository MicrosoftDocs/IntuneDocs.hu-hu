---
title: "Eszközök kivonása | Microsoft Intune"
description: "Az Intune a házirend és a vállalati portál szelektív és teljes törlését is támogatja az eszközök az Intune-kezelésből való eltávolításához."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7bea7ba4ef59c6b1400414b59456e19dc1c152fb
ms.openlocfilehash: ad5e9453f8132d383f8c23886e48505769c7f44b


---

# Eszközök kivonása az Intune felügyelete alól

Akár vállalati, akár saját eszközökről van szó, eljön a pillanat, amikor egy felügyelt eszközt ki kell vonni az Intune-felügyelet alól. Az eszközök kivonása viszonylag egyszerű feladat. A mobileszközként felügyelt eszközökön szelektív vagy teljes törlést hajthat végre. Ezen kívül kivonhatja az Intune ügyfélszoftver által felügyelt számítógépeket is.

## Adatok és alkalmazások törlése az eszközökről
Mind a szelektív, mind a teljes törlés eltávolítja az eszközt az Intune-ból a szabályzat és a Vállalati portál törlésével, vagyis az eszköz a továbbiakban nem fog rendelkezni a vállalati erőforrásokba, például a Microsoft SharePoint vagy az Office 365 szolgáltatásba, illetve a levelezőrendszerbe való bejelentkezéshez szükséges hitelesítő adatokkal.

A [szelektív törlés](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) művelet olyan alkalmazottak esetében ajánlott, akik a saját eszközüket regisztrálták az Intune-ban, mert az eszközön lévő személyes adatokra nincs hatással. Csak a vállalati adatok törlődnek.

Az olyan eszközök esetében, amelyek újrafelhasználásra kerülnek, [teljes törlést](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) is alkalmazhat, amely visszaállítja az eszköz gyári beállításait.

## Eszközök törlése az Azure Active Directory portálon

1.  Jelentkezzen be szervezeti hitelesítő adataival a [http://aka.ms/accessaad](http://aka.ms/accessaad) vagy a [https://portal.office.com](https://portal.office.com) webhelyre, majd válassza a **Rendszergazdai központok** &gt; **Azure AD** lehetőséget.

2.  Ha még nem rendelkezik Azure-előfizetéssel, hozzon létre egyet. Ha díjköteles fiókkal rendelkezik, ennek elvégzéséhez nem szükséges hitelkártya vagy díjrendezés (kattintson a **Register your free Azure Active Directory** előfizetési hivatkozásra).

4.  Válassza az **Active Directory** lehetőséget, és jelölje ki a szervezetét.

5.  Válassza a **Felhasználók** fület.

6.  Jelölje ki azokat a felhasználókat, akiknek az eszközeit törölni szeretné.

7.  Válassza az **Eszközök** lehetőséget.

8.  Igény szerint jelölje ki az eszközöket, majd válassza az **Eszköz törlése** lehetőséget. Az eszköz az Active Directoryval való következő szinkronizáláskor törlődik. Erre általában 4 óránként kerül sor. A szinkronizálás után a rendszer eltávolítja azt a felügyelt eszközök közül. Ezzel eggyel csökken a felhasználó eszközeinek száma a felhasználó eszközeinek maximális számához képest.

## Felügyelt számítógépek kivonása
Az Intune ügyfélszoftverrel felügyelt számítógépek az Intune felügyeleti konzolján távolíthatók el a felügyelet alól. Ez a művelet egyúttal eltávolítja az ügyfélszoftvert és törli az Intune-házirendet a számítógépről. Olvassa el az [Intune ügyfélszoftver által felügyelt számítógépek kivonásáról](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md) szóló információkat.

## Hozzáférés letiltása az eszközhöz
Elveszett eszköz esetén, vagy ha azért kell eszköz kivonni, mert egy alkalmazott a vállalati tulajdonban álló hardver visszaszolgáltatása nélkül távozott a vállalattól, [alaphelyzetbe állíthatja az eszköz PIN-kódját és távolról zárolhatja](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) az eszközt. Ezzel a vállalati információkkal és a vállalati hardverrel való visszaélés is elkerülhető, bár előfordulhat, hogy az eszközt le kell írni veszteségként.

Az alkalmazott Intune-felhasználói fiókjának licencét is érdemes visszavonni. Ezzel felszabadul a licenc, és hozzá lehet rendelni egy új felhasználói fiókhoz.

## Hardver kivonása
Egyes esetekben maga az eszköz éri el életciklusának végét. Ilyen esetekben egy teljes törléssel [a gyári beállítások visszaállíthatók](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md), az összes adat eltávolítható, és az eszköz el is távolítható az Intune-ból. Ezután a vállalati házirendnek megfelelően le lehet selejtezni a hardvereket.

### További információ
[Adatok védelme teljes vagy szelektív törléssel](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Aug16_HO2-->

