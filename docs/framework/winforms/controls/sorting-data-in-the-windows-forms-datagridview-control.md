---
title: Сортировка данных в элементе управления DataGridView
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742944"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="299f4-102">Сортировка данных в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="299f4-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="299f4-103">По умолчанию пользователи могут сортировать данные в элементе управления <xref:System.Windows.Forms.DataGridView>, щелкая заголовок столбца текстового поля (или нажав клавишу F3, когда в ячейке текстового поля нажимается .NET Framework 4.7.2 и более поздние версии).</span><span class="sxs-lookup"><span data-stu-id="299f4-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="299f4-104">Можно изменить свойство <xref:System.Windows.Forms.DataGridViewColumn.SortMode> конкретных столбцов, чтобы разрешить пользователям сортировать по другим типам столбцов, если это имеет смысл.</span><span class="sxs-lookup"><span data-stu-id="299f4-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="299f4-105">Можно также выполнять сортировку данных программным способом по любому столбцу или по нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="299f4-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="299f4-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="299f4-106">In this section</span></span>

[<span data-ttu-id="299f4-107">Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="299f4-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="299f4-108">Описывает параметры сортировки данных в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="299f4-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="299f4-109">Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="299f4-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="299f4-110">Описывает, как разрешить пользователям сортировать по столбцам, которые не поддерживают сортировку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="299f4-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="299f4-111">Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="299f4-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="299f4-112">Описывает, как программно сортировать данные и как настраивать сортировку с помощью <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType>ного события или путем реализации интерфейса <xref:System.Collections.IComparer>.</span><span class="sxs-lookup"><span data-stu-id="299f4-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="299f4-113">Справочник</span><span class="sxs-lookup"><span data-stu-id="299f4-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="299f4-114">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="299f4-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="299f4-115">Содержит справочную документацию по методу <xref:System.Windows.Forms.DataGridView.Sort%2A>.</span><span class="sxs-lookup"><span data-stu-id="299f4-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="299f4-116">Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="299f4-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="299f4-117">Содержит справочную документацию по перечислению <xref:System.Windows.Forms.DataGridViewColumnSortMode>.</span><span class="sxs-lookup"><span data-stu-id="299f4-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="299f4-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="299f4-118">See also</span></span>

- [<span data-ttu-id="299f4-119">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="299f4-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="299f4-120">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="299f4-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
