---
ms.openlocfilehash: efa0efaf40e2e432d477f1659d7bde3abc98241d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857520"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="64d89-101">Теперь поддерживаются категории стандартной версии Юникода 8.0</span><span class="sxs-lookup"><span data-stu-id="64d89-101">Unicode standard version 8.0 categories now supported</span></span>

|   |   |
|---|---|
|<span data-ttu-id="64d89-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="64d89-102">Details</span></span>|<span data-ttu-id="64d89-103">В .NET Framework 4.6.2 данные Юникода были обновлены со стандартной версии 6.3 до версии 8.0.</span><span class="sxs-lookup"><span data-stu-id="64d89-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="64d89-104">При запросе категорий символов Юникода в .NET Framework 4.6.2 некоторые результаты могут не соответствовать результатам в предыдущих версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64d89-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="64d89-105">Это изменение в первую очередь влияет на слоги языка чероки, а также знаки гласных и обозначения тонов в новой письменности Тай-Лю.</span><span class="sxs-lookup"><span data-stu-id="64d89-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>|
|<span data-ttu-id="64d89-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="64d89-106">Suggestion</span></span>|<span data-ttu-id="64d89-107">Просмотрите код и удалите или измените логику, зависящую от жестко заданных категорий символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="64d89-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>|
|<span data-ttu-id="64d89-108">Область</span><span class="sxs-lookup"><span data-stu-id="64d89-108">Scope</span></span>|<span data-ttu-id="64d89-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="64d89-109">Minor</span></span>|
|<span data-ttu-id="64d89-110">Version</span><span class="sxs-lookup"><span data-stu-id="64d89-110">Version</span></span>|<span data-ttu-id="64d89-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="64d89-111">4.6.2</span></span>|
|<span data-ttu-id="64d89-112">Type</span><span class="sxs-lookup"><span data-stu-id="64d89-112">Type</span></span>|<span data-ttu-id="64d89-113">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="64d89-113">Runtime</span></span>|
|<span data-ttu-id="64d89-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="64d89-114">Affected APIs</span></span>|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
