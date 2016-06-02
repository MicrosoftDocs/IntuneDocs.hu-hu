---
# required metadata

title: Mi történik, ha alaphelyzetbe állít egy saját eszközt a Vállalati portálon? | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1ee6e275-d1ec-4da3-bbef-d5da2c61a02a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Mi történik, ha alaphelyzetbe állít egy saját eszközt a Vállalati portálon?

Ha a Vállalati portál alkalmazás vagy webhely segítségével alaphelyzetbe állítja windowsos eszközét, az eszközön található beállítások és alkalmazások egy része törlődhet, köztük egyes személyes adatok is. Az, hogy az adott eszközön mi történik, az eszköz típusától és használati módjától függ – erről részletes információk az alábbi táblázatban láthatók. Az elveszett vagy ellopott eszköz alaphelyzetbe állításával kapcsolatos útmutatásokért lásd: [Elveszett vagy ellopott eszköz alaphelyzetbe állítása (tartalmának végleges törlése)](reset-erase-your-lost-or-stolen-device-windows.md)..

|Eszközök konfigurálása és felügyelete|Eszköz típusa|
|---------------------------------------|---------------|
|A rendszergazda felügyeli a mobileszközt|**Windows 10, Windows Phone 8.1 és Windows Phone 8**</br>Az eszköz nem jelenik meg többé a vállalati portálon, és a vállalati portál megpróbálja visszaállítani az eszközt a gyári alapértékekre. Eltávolításra kerülnek a személyes adatok, alkalmazások és beállítások.<br /><br />**Windows RT**<br />Windows RT-alapú eszköz nem állítható alaphelyzetbe, kivéve, ha kizárólag az e-mailek elérésére használják.|
|Az eszköz csak a vállalati e-mailekhez férhet hozzá.|**Windows Phone 8.1 és Windows Phone 8**<br />Az eszköz nem jelenik meg többé a vállalati portálon, és a vállalati e-mail-fiókja és a nem mentett e-mailek törlődnek.<br /><br />**Windows RT**<br />Az eszköz nem jelenik meg többé a vállalati portálon, és a vállalati e-mail-fiókja és a nem mentett e-mailek törlődnek.<br /><br />**Windows 7 vagy Windows Vista rendszerű számítógépek**<br />Kizárólag az e-mailek elérésére használt, Windows 7 vagy korábbi operációs rendszert futtató számítógép nem állítható alaphelyzetbe.<br /><br />**Windows 8.1 és Windows 8 rendszerű számítógépek**<br />Az eszköz nem jelenik meg többé a vállalati portálon, és a vállalati e-mail-fiókja és a nem mentett e-mailek törlődnek.|
|Számítógépek és laptopok|**Windows 8.1 és Windows 8 rendszerű számítógépek**<br />Windows 8 vagy Windows 8.1 rendszert futtató számítógép nem állítható alaphelyzetbe, kivéve, ha kizárólag az e-mailek elérésére használják.<br /><br />**Windows 7 vagy Windows Vista rendszerű számítógépek**<br />Windows 7 vagy korábbi operációs rendszert futtató számítógép nem állítható alaphelyzetbe.|

### További információ
[Windows-eszköz használata az Intune-nal](using-your-windows-device-with-intune.md)

<!--HONumber=May16_HO1-->

