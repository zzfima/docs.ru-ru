---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804402"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="09318-101">ClickOnce поддерживает SHA-256 в приложениях, предназначенных для версии 4.0</span><span class="sxs-lookup"><span data-stu-id="09318-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="09318-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="09318-102">Details</span></span>|<span data-ttu-id="09318-103">Раньше приложению ClickOnce с сертификатом, подписанным с SHA-256, требовалась платформа .NET Framework 4.5 или более поздней версии, даже если приложение предназначено для версии 4.0.</span><span class="sxs-lookup"><span data-stu-id="09318-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="09318-104">Теперь приложения ClickOnce, предназначенные для .NET Framework 4.0, можно запускать на .NET Framework 4.0, даже если они подписаны с помощью алгоритма SHA-256.</span><span class="sxs-lookup"><span data-stu-id="09318-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="09318-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="09318-105">Suggestion</span></span>|<span data-ttu-id="09318-106">Это изменение удаляет зависимость и позволяет использовать сертификаты SHA-256 для подписи приложений ClickOnce на платформе .NET Framework 4 и более ранних версий.</span><span class="sxs-lookup"><span data-stu-id="09318-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="09318-107">Область</span><span class="sxs-lookup"><span data-stu-id="09318-107">Scope</span></span>|<span data-ttu-id="09318-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="09318-108">Minor</span></span>|
|<span data-ttu-id="09318-109">Version</span><span class="sxs-lookup"><span data-stu-id="09318-109">Version</span></span>|<span data-ttu-id="09318-110">4.6</span><span class="sxs-lookup"><span data-stu-id="09318-110">4.6</span></span>|
|<span data-ttu-id="09318-111">Type</span><span class="sxs-lookup"><span data-stu-id="09318-111">Type</span></span>|<span data-ttu-id="09318-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="09318-112">Retargeting</span></span>|
