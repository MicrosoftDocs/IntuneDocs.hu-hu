---
# required metadata

title: A vállalati erőforrások hozzáférésének engedélyezése a Microsoft Intune-nal | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# A vállalati erőforrások hozzáférésének engedélyezése a Microsoft Intune-nal
A Microsoft Intune Wi-Fi-, VPN- és e-mail-profilokkal hozzáférést biztosíthat a felhasználóknak a munkájuk sikeres elvégzéséhez szükséges fájlokhoz és erőforrásokhoz, bárhol legyenek is. A hozzáférés védelmét tanúsítványprofilok segítik.

## A [Wi-Fi-profilok](wi-fi-connections-in-microsoft-intune.md) és a támogatott platformok

Vezeték nélküli hálózati beállításokat telepíthet a felhasználók számára. Ezen beállítások telepítésével lecsökkentheti a vállalati hálózat hozzáféréséhez szükséges végfelhasználói beavatkozást.
#### Támogatott platformok

|Windows 8.1 és újabb|Windows Phone 8.1 és újabb verziók|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Igen (importálhat Windows Wi-Fi profilt)|Igen (konfigurálhat OMA-URI-beállítást) |Igen|Igen|Igen|

## A [VPN-profilok](vpn-connections-in-microsoft-intune.md) és a támogatott platformok
Alkalmazzon virtuális magánhálózati (VPN) beállításokat a felhasználókra. Ezen beállítások telepítésével lecsökkentheti a vállalati hálózaton lévő erőforrások eléréséhez szükséges végfelhasználói beavatkozást.

|Windows 8.1 és újabb|Windows Phone 8.1 és újabb verziók|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Igen|Igen|Igen|Igen|Igen|

## Az [e-mail-profilok](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) és a támogatott platformok
Segítségükkel létrehozhatja, telepítheti és megfigyelheti a natív e-mail-ügyfélprogram beállításait a szervezetben lévő eszközökön.

|Windows 8.1 és újabb|Windows Phone 8.1 és újabb verziók|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Nem|Igen|Igen|Nem|Igen|
> [!NOTE]
> [Ez az Intune csapata által írt blogbejegyzés](http://blogs.technet.com/b/microsoftintune/archive/2015/02/23/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1.aspx) tájékoztatást nyújt a Windows Phone 8.1 Wi-Fi-profilnak az OMA-URI-beállításokkal történő konfigurálásáról.

## A [tanúsítványprofilok](secure-resource-access-with-certificate-profiles.md) és a támogatott platformok
Segít a vállalati erőforrások elérésének biztonságossá tételében, beleértve a vezeték nélküli hálózatokat és a VPN-kapcsolatokat.

|Windows 8.1 és újabb|Windows Phone 8.1 és újabb verziók|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Igen|Igen|Igen|Igen|Igen|


<!--HONumber=May16_HO1-->

