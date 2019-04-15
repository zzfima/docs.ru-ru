---
ms.openlocfilehash: 958a89015420ce5632d596688963d576c40b4cb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235579"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="ff467-101">Для совместного доступа к состоянию сеанса с Asp.Net StateServer все серверы на веб-ферме должны использовать одинаковую версию .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ff467-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ff467-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ff467-102">Details</span></span>|<span data-ttu-id="ff467-103">При включении состояния сеанса <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> все серверы на данной веб-ферме должны использовать одинаковую версию платформы .NET Framework, чтобы состояние передавалось должным образом.</span><span class="sxs-lookup"><span data-stu-id="ff467-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>|
|<span data-ttu-id="ff467-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="ff467-104">Suggestion</span></span>|<span data-ttu-id="ff467-105">Обновите версии платформы .NET Framework на веб-серверах, которые совместно и одновременно используют состояние.</span><span class="sxs-lookup"><span data-stu-id="ff467-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>|
|<span data-ttu-id="ff467-106">Область</span><span class="sxs-lookup"><span data-stu-id="ff467-106">Scope</span></span>|<span data-ttu-id="ff467-107">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="ff467-107">Edge</span></span>|
|<span data-ttu-id="ff467-108">Версия</span><span class="sxs-lookup"><span data-stu-id="ff467-108">Version</span></span>|<span data-ttu-id="ff467-109">4.5</span><span class="sxs-lookup"><span data-stu-id="ff467-109">4.5</span></span>|
|<span data-ttu-id="ff467-110">Тип</span><span class="sxs-lookup"><span data-stu-id="ff467-110">Type</span></span>|<span data-ttu-id="ff467-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ff467-111">Runtime</span></span>|
|<span data-ttu-id="ff467-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ff467-112">Affected APIs</span></span>|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
