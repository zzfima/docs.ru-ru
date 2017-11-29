---
title: "Сортировка данных в элементе управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b4027f3ae604f2a3ff4996855fa6dd34d4de8ea2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="192d9-102">Сортировка данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="192d9-102">Sorting Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="192d9-103">По умолчанию пользователи могут сортировать данные в `DataGridView` управления, щелкнув заголовок столбца текстового поля.</span><span class="sxs-lookup"><span data-stu-id="192d9-103">By default, users can sort the data in a `DataGridView` control by clicking the header of a text box column.</span></span> <span data-ttu-id="192d9-104">Вы можете изменить `SortMode` определенных столбцов, чтобы пользователи могли сортировать по другим типам столбцов, когда имеет смысл для этого свойства.</span><span class="sxs-lookup"><span data-stu-id="192d9-104">You can modify the `SortMode` property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="192d9-105">Данные можно также сортировать программным путем, по любому столбцу или нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="192d9-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="192d9-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="192d9-106">In This Section</span></span>  
 [<span data-ttu-id="192d9-107">Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="192d9-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="192d9-108">Описание параметров сортировки данных в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="192d9-108">Describes the options for sorting data in the control.</span></span>  
  
 [<span data-ttu-id="192d9-109">Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="192d9-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
 <span data-ttu-id="192d9-110">Описывает, как разрешить пользователям сортировать по столбцам, которые не сортируются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="192d9-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>  
  
 [<span data-ttu-id="192d9-111">Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="192d9-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="192d9-112">Описывается порядок сортировки данных программным образом и настройки сортировки с помощью <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> событий либо путем реализации <xref:System.Collections.IComparer> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="192d9-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="192d9-113">Ссылка</span><span class="sxs-lookup"><span data-stu-id="192d9-113">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="192d9-114">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="192d9-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
 <span data-ttu-id="192d9-115">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.Sort%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="192d9-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="192d9-116">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="192d9-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumnSortMode>  
 <span data-ttu-id="192d9-117">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewColumnSortMode> перечисления.</span><span class="sxs-lookup"><span data-stu-id="192d9-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="192d9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="192d9-118">See Also</span></span>  
 [<span data-ttu-id="192d9-119">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="192d9-119">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="192d9-120">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="192d9-120">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
