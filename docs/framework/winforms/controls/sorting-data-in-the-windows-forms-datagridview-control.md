---
title: Сортировка данных в элементе управления Windows Forms DataGridView
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 606ffc7bd6136b775adaaaa79cf5042cf1e2dd70
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724925"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4b99c-102">Сортировка данных в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="4b99c-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="4b99c-103">По умолчанию пользователи могут сортировать данные в <xref:System.Windows.Forms.DataGridView> элемента управления, щелкнув заголовок столбца текстового поля (и, нажав клавишу F3, при получении фокуса ввода ячейке текстового поля на .NET Framework 4.7.2 и более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="4b99c-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="4b99c-104">Вы можете изменить <xref:System.Windows.Forms.DataGridViewColumn.SortMode> определенные столбцы, чтобы разрешить пользователям сортировать по другим типам столбцов, когда имеет смысл для этого свойства.</span><span class="sxs-lookup"><span data-stu-id="4b99c-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="4b99c-105">Можно также сортировать данные программными средствами по любому столбцу или нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="4b99c-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4b99c-106">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="4b99c-106">In this section</span></span>

[<span data-ttu-id="4b99c-107">Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b99c-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="4b99c-108">Описание параметров сортировки данных в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="4b99c-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="4b99c-109">Практическое руководство. Определение режимов сортировки для столбцов в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b99c-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="4b99c-110">Описывает, как разрешить пользователям сортировать по столбцам, которые не поддерживает сортировку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b99c-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="4b99c-111">Практическое руководство. Настройка сортировки в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b99c-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="4b99c-112">Описывает способ сортировки данных программным образом и настройки сортировки с помощью <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> событий либо путем реализации <xref:System.Collections.IComparer> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4b99c-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="4b99c-113">Ссылка</span><span class="sxs-lookup"><span data-stu-id="4b99c-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="4b99c-114">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="4b99c-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="4b99c-115">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.Sort%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="4b99c-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="4b99c-116">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4b99c-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="4b99c-117">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewColumnSortMode> перечисления.</span><span class="sxs-lookup"><span data-stu-id="4b99c-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b99c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4b99c-118">See also</span></span>

- [<span data-ttu-id="4b99c-119">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="4b99c-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="4b99c-120">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b99c-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
