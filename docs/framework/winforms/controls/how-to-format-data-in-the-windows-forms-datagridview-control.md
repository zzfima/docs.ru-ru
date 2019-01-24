---
title: Как выполнить Форматирование данных в Windows Forms элемента управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: fa029a46f1553d8d371fd574c21e7a016e7b5500
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598125"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="07e30-102">Как выполнить Форматирование данных в Windows Forms элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="07e30-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="07e30-103">Следующие процедуры демонстрируют основные элементы форматирования значений ячеек с помощью <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> свойство <xref:System.Windows.Forms.DataGridView> управления и для определенных столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="07e30-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="07e30-104">Сведения о форматировании данных см. в разделе [как: Настройка форматирования данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="07e30-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="07e30-105">Для форматирования валюты и значения дат</span><span class="sxs-lookup"><span data-stu-id="07e30-105">To format currency and date values</span></span>  
  
-   <span data-ttu-id="07e30-106">Задайте свойство <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="07e30-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="07e30-107">В следующем примере кода задает формат для определенных столбцов с помощью <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> свойств столбцов.</span><span class="sxs-lookup"><span data-stu-id="07e30-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="07e30-108">Значения в `UnitPrice` столбец отображается в текущем формате валюты с отрицательными значениями, заключенных в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="07e30-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="07e30-109">Значения в `ShipDate` столбец отображается в текущей культуре короткого формата даты.</span><span class="sxs-lookup"><span data-stu-id="07e30-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="07e30-110">Дополнительные сведения о <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> значения, см. в разделе [типы форматирования](../../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="07e30-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="07e30-111">Для настройки отображения значений null базы данных</span><span class="sxs-lookup"><span data-stu-id="07e30-111">To customize the display of null database values</span></span>  
  
-   <span data-ttu-id="07e30-112">Задайте свойство <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="07e30-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="07e30-113">В следующем примере кода используется <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> свойство для отображения во всех ячейках, имеющих значение «Нет записи» <xref:System.DBNull.Value?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="07e30-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="07e30-114">Включение переноса слов в ячейках, основанные на тексте</span><span class="sxs-lookup"><span data-stu-id="07e30-114">To enable wordwrap in text-based cells</span></span>  
  
-   <span data-ttu-id="07e30-115">Задайте <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> свойство <xref:System.Windows.Forms.DataGridViewCellStyle> к одному из <xref:System.Windows.Forms.DataGridViewTriState> значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="07e30-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="07e30-116">В следующем примере кода используется <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> свойство, чтобы задать режим переноса для всего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="07e30-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="07e30-117">Чтобы указать выравнивание текста для ячеек элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="07e30-117">To specify the text alignment of DataGridView cells</span></span>  
  
-   <span data-ttu-id="07e30-118">Задайте <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> свойство <xref:System.Windows.Forms.DataGridViewCellStyle> к одному из <xref:System.Windows.Forms.DataGridViewContentAlignment> значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="07e30-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="07e30-119">В следующем примере кода задает выравнивание для определенного столбца с помощью <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> свойства столбца.</span><span class="sxs-lookup"><span data-stu-id="07e30-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="07e30-120">Пример</span><span class="sxs-lookup"><span data-stu-id="07e30-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="07e30-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="07e30-121">Compiling the Code</span></span>  
 <span data-ttu-id="07e30-122">Для этих примеров требуются:</span><span class="sxs-lookup"><span data-stu-id="07e30-122">These examples require:</span></span>  
  
-   <span data-ttu-id="07e30-123">Объект <xref:System.Windows.Forms.DataGridView> управления с именем `dataGridView1` , содержащий столбец с именем `UnitPrice`, столбец с именем `ShipDate`и столбец с именем `CustomerName`.</span><span class="sxs-lookup"><span data-stu-id="07e30-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
-   <span data-ttu-id="07e30-124">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="07e30-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="07e30-125">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="07e30-125">Robust Programming</span></span>  
 <span data-ttu-id="07e30-126">Для максимальной масштабируемости следует распределить <xref:System.Windows.Forms.DataGridViewCellStyle> объекты в нескольких строк, столбцов или ячейкам одинаковыми стилями, а не отдельно задавать свойства стилей для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="07e30-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="07e30-127">Дополнительные сведения см. в разделе [масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="07e30-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e30-128">См. также</span><span class="sxs-lookup"><span data-stu-id="07e30-128">See also</span></span>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="07e30-129">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07e30-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="07e30-130">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07e30-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="07e30-131">Форматирование данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07e30-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="07e30-132">Практическое руководство. Настройка форматирования данных в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="07e30-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="07e30-133">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="07e30-133">Formatting Types</span></span>](../../../../docs/standard/base-types/formatting-types.md)
