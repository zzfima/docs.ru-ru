---
ms.openlocfilehash: edd194fef27d97976f1ff45daec1cd56382bbb55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235470"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="7cbed-101">Новые значения перечисления в перечислении PageRangeSelection WPF</span><span class="sxs-lookup"><span data-stu-id="7cbed-101">New enum values in WPF's PageRangeSelection</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7cbed-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="7cbed-102">Details</span></span>|<span data-ttu-id="7cbed-103">Было добавлено два новых члена (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> и <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>) в перечисление <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="7cbed-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> enum.</span></span>|
|<span data-ttu-id="7cbed-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="7cbed-104">Suggestion</span></span>|<span data-ttu-id="7cbed-105">В большинстве случаев эти изменения не влияют на код пользователя.</span><span class="sxs-lookup"><span data-stu-id="7cbed-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="7cbed-106">Однако следует изменить код, зависящий от конкретного числа элементов, существующих в вызовах <xref:System.Enum.GetNames(System.Type)> или <xref:System.Enum.GetValues(System.Type)> к типу <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="7cbed-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> type should be modified, though.</span></span>|
|<span data-ttu-id="7cbed-107">Область</span><span class="sxs-lookup"><span data-stu-id="7cbed-107">Scope</span></span>|<span data-ttu-id="7cbed-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="7cbed-108">Edge</span></span>|
|<span data-ttu-id="7cbed-109">Версия</span><span class="sxs-lookup"><span data-stu-id="7cbed-109">Version</span></span>|<span data-ttu-id="7cbed-110">4.5</span><span class="sxs-lookup"><span data-stu-id="7cbed-110">4.5</span></span>|
|<span data-ttu-id="7cbed-111">Тип</span><span class="sxs-lookup"><span data-stu-id="7cbed-111">Type</span></span>|<span data-ttu-id="7cbed-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="7cbed-112">Runtime</span></span>|
|<span data-ttu-id="7cbed-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7cbed-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
