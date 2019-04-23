---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804894"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="e17a7-101">Доступ к выделенным элементам DataGrid WPF из события UnloadingRow DataGrid может привести к исключению NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="e17a7-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e17a7-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e17a7-102">Details</span></span>|<span data-ttu-id="e17a7-103">Из-за ошибки в .NET Framework 4.5 обработчики событий <xref:System.Windows.Controls.DataGrid>, которые выполняют удаление строки, могут привести к созданию исключения <xref:System.NullReferenceException?displayProperty=name> при попытке получить доступ к свойствам <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> или <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="e17a7-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=name> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> properties.</span></span>|
|<span data-ttu-id="e17a7-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="e17a7-104">Suggestion</span></span>|<span data-ttu-id="e17a7-105">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e17a7-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="e17a7-106">Область</span><span class="sxs-lookup"><span data-stu-id="e17a7-106">Scope</span></span>|<span data-ttu-id="e17a7-107">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="e17a7-107">Minor</span></span>|
|<span data-ttu-id="e17a7-108">Версия</span><span class="sxs-lookup"><span data-stu-id="e17a7-108">Version</span></span>|<span data-ttu-id="e17a7-109">4.5</span><span class="sxs-lookup"><span data-stu-id="e17a7-109">4.5</span></span>|
|<span data-ttu-id="e17a7-110">Тип</span><span class="sxs-lookup"><span data-stu-id="e17a7-110">Type</span></span>|<span data-ttu-id="e17a7-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e17a7-111">Runtime</span></span>|
|<span data-ttu-id="e17a7-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e17a7-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
