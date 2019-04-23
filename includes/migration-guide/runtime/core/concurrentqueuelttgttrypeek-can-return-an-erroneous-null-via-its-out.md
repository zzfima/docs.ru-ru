---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236715"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="0c168-101">ConcurrentQueue\<T>.TryPeek может возвращать ошибочные значения NULL в выходном параметре</span><span class="sxs-lookup"><span data-stu-id="0c168-101">ConcurrentQueue\<T>.TryPeek can return an erroneous null via its out parameter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0c168-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0c168-102">Details</span></span>|<span data-ttu-id="0c168-103">В некоторых сценариях с несколькими потоками <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> может возвращать значение true, но заполнять выходной параметр значением NULL (вместо правильного значения).</span><span class="sxs-lookup"><span data-stu-id="0c168-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>|
|<span data-ttu-id="0c168-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="0c168-104">Suggestion</span></span>|<span data-ttu-id="0c168-105">Эта проблема решена в EntityFramework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="0c168-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="0c168-106">Чтобы устранить проблему, выполните обновление до этой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="0c168-106">Upgrading to that Framework will solve the issue.</span></span>|
|<span data-ttu-id="0c168-107">Область</span><span class="sxs-lookup"><span data-stu-id="0c168-107">Scope</span></span>|<span data-ttu-id="0c168-108">Значительно</span><span class="sxs-lookup"><span data-stu-id="0c168-108">Major</span></span>|
|<span data-ttu-id="0c168-109">Версия</span><span class="sxs-lookup"><span data-stu-id="0c168-109">Version</span></span>|<span data-ttu-id="0c168-110">4.5</span><span class="sxs-lookup"><span data-stu-id="0c168-110">4.5</span></span>|
|<span data-ttu-id="0c168-111">Тип</span><span class="sxs-lookup"><span data-stu-id="0c168-111">Type</span></span>|<span data-ttu-id="0c168-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0c168-112">Runtime</span></span>|
|<span data-ttu-id="0c168-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0c168-113">Affected APIs</span></span>|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
