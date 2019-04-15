---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235543"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="7edcd-101">Доступ к выделенным элементам DataGrid WPF из события UnloadingRow DataGrid может привести к исключению NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="7edcd-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7edcd-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="7edcd-102">Details</span></span>|<span data-ttu-id="7edcd-103">Из-за ошибки в .NET Framework 4.5 обработчики событий <xref:System.Windows.Controls.DataGrid>, которые выполняют удаление строки, могут привести к созданию исключения <xref:System.NullReferenceException?displayProperty=name> при попытке получить доступ к свойствам <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> или <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="7edcd-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=name> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> properties.</span></span>|
|<span data-ttu-id="7edcd-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="7edcd-104">Suggestion</span></span>|<span data-ttu-id="7edcd-105">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7edcd-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="7edcd-106">Область</span><span class="sxs-lookup"><span data-stu-id="7edcd-106">Scope</span></span>|<span data-ttu-id="7edcd-107">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="7edcd-107">Minor</span></span>|
|<span data-ttu-id="7edcd-108">Версия</span><span class="sxs-lookup"><span data-stu-id="7edcd-108">Version</span></span>|<span data-ttu-id="7edcd-109">4.5</span><span class="sxs-lookup"><span data-stu-id="7edcd-109">4.5</span></span>|
|<span data-ttu-id="7edcd-110">Тип</span><span class="sxs-lookup"><span data-stu-id="7edcd-110">Type</span></span>|<span data-ttu-id="7edcd-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="7edcd-111">Runtime</span></span>|
|<span data-ttu-id="7edcd-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7edcd-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
