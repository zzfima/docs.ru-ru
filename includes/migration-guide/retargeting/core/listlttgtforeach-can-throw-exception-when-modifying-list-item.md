---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774405"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="bc536-101">List\<T>.ForEach может создавать исключение при изменении элемента списка</span><span class="sxs-lookup"><span data-stu-id="bc536-101">List\<T>.ForEach can throw exception when modifying list item</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bc536-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="bc536-102">Details</span></span>|<span data-ttu-id="bc536-103">Начиная с .NET Framework 4.5 перечислитель <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> будет создавать исключение <xref:System.InvalidOperationException?displayProperty=name> при изменении элемента в вызывающей коллекции.</span><span class="sxs-lookup"><span data-stu-id="bc536-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=name> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="bc536-104">Ранее исключение не создавалось, но могли возникать конфликты.</span><span class="sxs-lookup"><span data-stu-id="bc536-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>|
|<span data-ttu-id="bc536-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="bc536-105">Suggestion</span></span>|<span data-ttu-id="bc536-106">В идеальном случае следует исправить код, чтобы он не изменял списки при перечислении их элементов, поскольку эта операция небезопасна.</span><span class="sxs-lookup"><span data-stu-id="bc536-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="bc536-107">Чтобы вернуться к предыдущему поведению, приложение должно быть предназначено для платформы .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="bc536-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>|
|<span data-ttu-id="bc536-108">Область</span><span class="sxs-lookup"><span data-stu-id="bc536-108">Scope</span></span>|<span data-ttu-id="bc536-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="bc536-109">Edge</span></span>|
|<span data-ttu-id="bc536-110">Версия</span><span class="sxs-lookup"><span data-stu-id="bc536-110">Version</span></span>|<span data-ttu-id="bc536-111">4.5</span><span class="sxs-lookup"><span data-stu-id="bc536-111">4.5</span></span>|
|<span data-ttu-id="bc536-112">Тип</span><span class="sxs-lookup"><span data-stu-id="bc536-112">Type</span></span>|<span data-ttu-id="bc536-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="bc536-113">Retargeting</span></span>|
|<span data-ttu-id="bc536-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="bc536-114">Affected APIs</span></span>|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
