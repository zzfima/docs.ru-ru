---
ms.openlocfilehash: e2d63d85adce64db6e00b62ec17f55ae71ce3052
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804927"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="c6501-101">Вызов метода DataGrid.CommitEdit из обработчика CellEditEnding удаляет фокус</span><span class="sxs-lookup"><span data-stu-id="c6501-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c6501-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="c6501-102">Details</span></span>|<span data-ttu-id="c6501-103">Вызов метода <xref:System.Windows.Controls.DataGrid.CommitEdit> из одного из обработчиков событий <xref:System.Windows.Controls.DataGrid?displayProperty=name> <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> приводит к потере фокуса для <xref:System.Windows.Controls.DataGrid?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="c6501-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=name>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=name> to lose focus.</span></span>|
|<span data-ttu-id="c6501-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="c6501-104">Suggestion</span></span>|<span data-ttu-id="c6501-105">Это ошибка исправлена в .NET Framework 4.5.2, поэтому ее можно избежать путем обновления .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6501-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="c6501-106">Кроме того, ее можно избежать, явным образом повторно выбрав <xref:System.Windows.Controls.DataGrid?displayProperty=name> после вызова <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="c6501-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=name> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.</span></span>|
|<span data-ttu-id="c6501-107">Область</span><span class="sxs-lookup"><span data-stu-id="c6501-107">Scope</span></span>|<span data-ttu-id="c6501-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="c6501-108">Edge</span></span>|
|<span data-ttu-id="c6501-109">Версия</span><span class="sxs-lookup"><span data-stu-id="c6501-109">Version</span></span>|<span data-ttu-id="c6501-110">4.5</span><span class="sxs-lookup"><span data-stu-id="c6501-110">4.5</span></span>|
|<span data-ttu-id="c6501-111">Тип</span><span class="sxs-lookup"><span data-stu-id="c6501-111">Type</span></span>|<span data-ttu-id="c6501-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="c6501-112">Runtime</span></span>|
|<span data-ttu-id="c6501-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c6501-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
