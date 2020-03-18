---
ms.openlocfilehash: e7154919d6a09a04e650d5546feb2ae6c6cc912f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859197"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="73fa7-101">HttpRuntime.AppDomainAppPath создает исключение NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="73fa7-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="73fa7-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="73fa7-102">Details</span></span>|<span data-ttu-id="73fa7-103">В платформе .NET Framework 4.6.2 среда выполнения создает исключение <code>T:System.NullReferenceException</code> при получении значения <code>P:System.Web.HttpRuntime.AppDomainAppPath</code>, которое содержит нуль-символы. В .NET Framework 4.6.1 и более ранних версий среда выполнения создает исключение <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="73fa7-103">In the .NET Framework 4.6.2, the runtime throws a <code>T:System.NullReferenceException</code> when retrieving a <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an <code>T:System.ArgumentNullException</code>.</span></span>|
|<span data-ttu-id="73fa7-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="73fa7-104">Suggestion</span></span>|<span data-ttu-id="73fa7-105">В ответ на это изменение можно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="73fa7-105">You can do either of the follow to respond to this change:</span></span><ul><li><span data-ttu-id="73fa7-106">обрабатывайте <code>T:System.NullReferenceException</code>, если приложение работает на платформе .NET Framework 4.6.2;</span><span class="sxs-lookup"><span data-stu-id="73fa7-106">Handle the <code>T:System.NullReferenceException</code> if you application is running on the .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="73fa7-107">обновите систему до версии .NET Framework 4.7, в которой восстановлено прежнее поведение, то есть создается исключение <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="73fa7-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an <code>T:System.ArgumentNullException</code>.</span></span></li></ul>|
|<span data-ttu-id="73fa7-108">Область</span><span class="sxs-lookup"><span data-stu-id="73fa7-108">Scope</span></span>|<span data-ttu-id="73fa7-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="73fa7-109">Edge</span></span>|
|<span data-ttu-id="73fa7-110">Version</span><span class="sxs-lookup"><span data-stu-id="73fa7-110">Version</span></span>|<span data-ttu-id="73fa7-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="73fa7-111">4.6.2</span></span>|
|<span data-ttu-id="73fa7-112">Type</span><span class="sxs-lookup"><span data-stu-id="73fa7-112">Type</span></span>|<span data-ttu-id="73fa7-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="73fa7-113">Retargeting</span></span>|
|<span data-ttu-id="73fa7-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="73fa7-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|
