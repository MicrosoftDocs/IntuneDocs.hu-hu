---
title: "Eszközmegfelelőségi szabályzatok | Microsoft Intune"
description: "Ez a témakör ismerteti azokat az elveket, amelyek segítségével megértheti, mik azok az eszközmegfelelőségi szabályzatok, és hogyan működnek."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: b17a47a2924ef36df69db2aa852f0b225471ecd1


---

# Eszközmegfelelőségi szabályzatok a Microsoft Intune-ban
## Mi a megfelelőségi szabályzat?
A vállalati adatok védelme érdekében gondoskodnia kell arról, hogy a vállalati alkalmazások és adatok elérésére használt eszközök megfeleljenek bizonyos szabályoknak, például használjanak PIN-kódot az eszközhöz való hozzáféréshez, illetve titkosítsák az eszközön tárolt adatokat. Az ilyen szabályok összességét megfelelőségi szabályzatnak nevezzük.

## Hogyan kell használni a megfelelőségi szabályzatokat?
Feltételes hozzáféréssel kiegészített megfelelőségi szabályzatokkal engedélyezheti, hogy kizárólag olyan eszközök férhessenek hozzá az e-mailekhez és egyéb szolgáltatásokhoz, amelyek eleget tesznek a megfelelőségi szabályzatnak . A két szabályzat együttes alkalmazásának megértéséhez olvassa el [Az e-mailek és az O365-szolgáltatások elérésének korlátozása](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) című témakört.

Megfelelőségi szabályzatokat feltételes hozzáféréstől függetlenül is használhat. Ilyen esetben a célzott eszközöket megfelelőségi állapotuk szerint értékeli ki és jelenti a rendszer. Előfordulhat például, hogy arról szeretne jelentést, hogy hány eszköz nincs titkosítva, vagy mely eszközök vannak függetlenítve vagy feltörve. Feltételes hozzáféréstől független alkalmazás esetén azonban nem korlátozza a rendszer a vállalati erőforrásokhoz való hozzáférést.

A megfelelőségi szabályzatokat felhasználókra lehet alkalmazni. Amikor felhasználók számára telepít megfelelőségi szabályzatot, a rendszer a felhasználói eszközök megfelelőségét ellenőrzi.

A következő táblázatban a megfelelőségi házirendek által támogatott eszköztípusok és a nem megfelelő beállítások kezelésének módja szerepel, amikor a házirendet feltételes hozzáférési házirenddel használják.

--------------

|Házirend-beállítás| Windows 8.1 és újabb| Windows Phone 8.1 és újabb verziók| iOS 6.0 és újabb verziók|Android 4.0 és újabb verziók<br/>Samsung KNOX szabvány 4.0 és újabb|
|-----|----|----|----|
|**PIN-kód vagy jelszó konfigurálása** |Kijavítva|Kijavítva|Kijavítva|Karanténba helyezve|
|**Eszköztitkosítás**|–|Kijavítva|Kijavítva (PIN-kód beállításával)|Karanténba helyezve|
|**Feltört eszköz**|–|–|Karanténba helyezve (nem beállítás)|Karanténba helyezve (nem beállítás)|
|**E-mail profil**|–|–|Karanténba helyezve|–|
|**Operációs rendszer minimális verziója**|Karanténba helyezve|Karanténba helyezve|Karanténba helyezve|Karanténba helyezve|
|**Operációs rendszer maximális verziója**|Karanténba helyezve| Karanténba helyezve| Karanténba helyezve| Karanténba helyezve|
|**Windows-állapotigazolás**|A Windows 10 és a Windows 10 Mobile karanténban van.<br /><br />A beállítás nem alkalmazható a Windows 8.1 rendszerre|–|–|–|
--------------
**Kijavítva** = Az eszköz operációs rendszere kikényszeríti a megfelelőséget (a felhasználót például PIN-kód beállítására kényszeríti).  A beállítás mindig megfelelő lesz.

**Karanténba helyezve** = Az eszköz operációs rendszere nem kényszeríti ki a megfelelőséget (az Android-eszközök például nem kényszerítik a felhasználót az eszköz titkosítására). Ha az eszköz nem megfelelő, a következő műveletekre kerül sor:

-   Az eszköz le lesz tiltva, ha a felhasználót feltételes hozzáférési házirend célozza meg.

-   A vállalati portál értesíti a felhasználót a megfelelőséggel kapcsolatos problémákról.

## További lépések
[Eszközmegfelelőségi szabályzat létrehozása](create-a-device-compliance-policy-in-microsoft-intune.md)

[Eszközmegfelelőségi szabályzat üzembe helyezése és figyelése](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### További információ
[Az e-mailek és az O365-szolgáltatások elérésének korlátozása](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->

