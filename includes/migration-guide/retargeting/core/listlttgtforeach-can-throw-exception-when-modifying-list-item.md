---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234840"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="110ec-101">List\<T>.ForEach может создавать исключение при изменении элемента списка</span><span class="sxs-lookup"><span data-stu-id="110ec-101">List\<T>.ForEach can throw exception when modifying list item</span></span>

|   |   |
|---|---|
|<span data-ttu-id="110ec-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="110ec-102">Details</span></span>|<span data-ttu-id="110ec-103">Начиная с .NET Framework 4.5 перечислитель <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> будет создавать исключение <xref:System.InvalidOperationException?displayProperty=name> при изменении элемента в вызывающей коллекции.</span><span class="sxs-lookup"><span data-stu-id="110ec-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=name> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="110ec-104">Ранее исключение не создавалось, но могли возникать конфликты.</span><span class="sxs-lookup"><span data-stu-id="110ec-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>|
|<span data-ttu-id="110ec-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="110ec-105">Suggestion</span></span>|<span data-ttu-id="110ec-106">В идеальном случае следует исправить код, чтобы он не изменял списки при перечислении их элементов, поскольку эта операция небезопасна.</span><span class="sxs-lookup"><span data-stu-id="110ec-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="110ec-107">Чтобы вернуться к предыдущему поведению, приложение должно быть предназначено для платформы .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="110ec-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>|
|<span data-ttu-id="110ec-108">Область</span><span class="sxs-lookup"><span data-stu-id="110ec-108">Scope</span></span>|<span data-ttu-id="110ec-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="110ec-109">Edge</span></span>|
|<span data-ttu-id="110ec-110">Версия</span><span class="sxs-lookup"><span data-stu-id="110ec-110">Version</span></span>|<span data-ttu-id="110ec-111">4.5</span><span class="sxs-lookup"><span data-stu-id="110ec-111">4.5</span></span>|
|<span data-ttu-id="110ec-112">Тип</span><span class="sxs-lookup"><span data-stu-id="110ec-112">Type</span></span>|<span data-ttu-id="110ec-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="110ec-113">Retargeting</span></span>|
|<span data-ttu-id="110ec-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="110ec-114">Affected APIs</span></span>|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
