---
title: Szabályzatok a Windows rendszerű számítógépek védelméhez
titlesuffix: Microsoft Intune
description: Ezek a szabályzatok az Intune ügyfélszoftver által felügyelt Windows rendszerű számítógépek biztonságának megőrzését segítik elő.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d081f466-45dd-41d1-ab25-6d974c72a52a
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic-keep
ms.openlocfilehash: 10f19c0b9823adcd40ce38bae1c6cbaacd59c0db
ms.sourcegitcommit: 116be0eaa44fd5518ff34780d39569224ef4746b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/21/2018
ms.locfileid: "36310487"
---
# <a name="use-policies-to-help-protect-windows-pcs-that-run-the-intune-client-software"></a>Szabályzatok használata az Intune ügyfélszoftvert futtató Windows rendszerű számítógépek védelméhez

[!INCLUDE [classic-portal](includes/classic-portal.md)]

A Microsoft Intune három olyan szabályzatot kínál, amelyek az [Intune ügyfélszoftver](manage-windows-pcs-with-microsoft-intune.md) által felügyelt Windows rendszerű számítógépek biztonságát segítik elő.


## <a name="software-updates"></a>Szoftverfrissítések

Az Intune megkönnyíti [a felügyelt Windows-számítógépek naprakészen tartását](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) azáltal, hogy értesítést küld a Microsoft és más vállalatok fontos, elérhetővé vált szoftverfrissítéseiről. Ezeket a frissítéseket elfogadhatja, de el is utasíthatja. A jóváhagyott frissítéseket a rendszer automatikusan telepíti minden megfelelő számítógépre.

## <a name="windows-firewall"></a>Windows tűzfal

A Windows tűzfal segít távol tartani a támadókat és a kártevőket a Windows rendszerű számítógépektől, illetve védelmet nyújt az egyéb fenyegetésekkel szemben. Az Intune segítségével valamennyi felügyelt számítógép [Windows-tűzfalbeállításait és -funkcióit kezelheti](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

## <a name="endpoint-protection"></a>Endpoint Protection

Rendszergazdaként egyik legfontosabb feladata a [kezelt Windows rendszerű számítógépek vírusoktól és kártevő szoftverektől mentesen tartása](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md). Az Endpoint Protection Intune-ba való integrálása valós idejű védelmet biztosít a veszélyes kártevők ellen, naprakészen tartja a kártevő-definíciókat, valamint automatikus vizsgálatokat végez a számítógépen. Az Endpoint Protection olyan eszközöket is biztosít, amelyek segítenek kezelni és megfigyelni a kártékony programok támadásait.



### <a name="see-also"></a>Lásd még:
[Az eszközök beállításainak és funkcióinak kezelése a Microsoft Intune-házirendek használatával](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)