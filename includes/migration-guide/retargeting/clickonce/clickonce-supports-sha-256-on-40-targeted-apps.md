---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804864"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="7ff3c-101">ClickOnce поддерживает SHA-256 в приложениях, предназначенных для версии 4.0</span><span class="sxs-lookup"><span data-stu-id="7ff3c-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7ff3c-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="7ff3c-102">Details</span></span>|<span data-ttu-id="7ff3c-103">Раньше приложению ClickOnce с сертификатом, подписанным с SHA-256, требовалась платформа .NET Framework 4.5 или более поздней версии, даже если приложение предназначено для версии 4.0.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="7ff3c-104">Теперь приложения ClickOnce, предназначенные для .NET Framework 4.0, можно запускать на .NET Framework 4.0, даже если они подписаны с помощью алгоритма SHA-256.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="7ff3c-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="7ff3c-105">Suggestion</span></span>|<span data-ttu-id="7ff3c-106">Это изменение удаляет зависимость и позволяет использовать сертификаты SHA-256 для подписи приложений ClickOnce на платформе .NET Framework 4 и более ранних версий.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="7ff3c-107">Область</span><span class="sxs-lookup"><span data-stu-id="7ff3c-107">Scope</span></span>|<span data-ttu-id="7ff3c-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="7ff3c-108">Minor</span></span>|
|<span data-ttu-id="7ff3c-109">Версия</span><span class="sxs-lookup"><span data-stu-id="7ff3c-109">Version</span></span>|<span data-ttu-id="7ff3c-110">4.6</span><span class="sxs-lookup"><span data-stu-id="7ff3c-110">4.6</span></span>|
|<span data-ttu-id="7ff3c-111">Тип</span><span class="sxs-lookup"><span data-stu-id="7ff3c-111">Type</span></span>|<span data-ttu-id="7ff3c-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="7ff3c-112">Retargeting</span></span>|
