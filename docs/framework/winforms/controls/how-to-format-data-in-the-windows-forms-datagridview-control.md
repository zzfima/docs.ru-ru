---
title: Форматирование данных в элементе управления DataGridView
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
ms.openlocfilehash: 9ee2869cf4085b5acfdf1f8c440151be506dbe3e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736788"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="57daa-102">Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57daa-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="57daa-103">Следующие процедуры демонстрируют базовое форматирование значений ячеек с помощью свойства <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> элемента управления <xref:System.Windows.Forms.DataGridView> и конкретных столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="57daa-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="57daa-104">Дополнительные сведения о расширенном форматировании данных см. в разделе [инструкции. Настройка форматирования данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="57daa-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="57daa-105">Форматирование значений денежной единицы и даты</span><span class="sxs-lookup"><span data-stu-id="57daa-105">To format currency and date values</span></span>  
  
- <span data-ttu-id="57daa-106">Задайте свойство <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="57daa-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="57daa-107">В следующем примере кода задается формат для конкретных столбцов с помощью свойства <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> столбцов.</span><span class="sxs-lookup"><span data-stu-id="57daa-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="57daa-108">Значения в столбце `UnitPrice` отображаются в текущем формате валюты, зависящем от языка и региональных параметров, с отрицательными значениями, заключенными в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="57daa-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="57daa-109">Значения в столбце `ShipDate` отображаются в кратком формате даты, соответствующем языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="57daa-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="57daa-110">Дополнительные сведения о <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> значениях см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="57daa-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="57daa-111">Настройка вывода значений NULL для базы данных</span><span class="sxs-lookup"><span data-stu-id="57daa-111">To customize the display of null database values</span></span>  
  
- <span data-ttu-id="57daa-112">Задайте свойство <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> элемента <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="57daa-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="57daa-113">В следующем примере кода используется свойство <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> для вывода строки без записи в ячейках, содержащих значения, равные <xref:System.DBNull.Value?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57daa-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="57daa-114">Включение переноса слов в текстовых ячейках</span><span class="sxs-lookup"><span data-stu-id="57daa-114">To enable wordwrap in text-based cells</span></span>  
  
- <span data-ttu-id="57daa-115">Задайте для свойства <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> <xref:System.Windows.Forms.DataGridViewCellStyle> одно из значений перечисления <xref:System.Windows.Forms.DataGridViewTriState>.</span><span class="sxs-lookup"><span data-stu-id="57daa-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="57daa-116">В следующем примере кода используется свойство <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> для задания режима переноса для всего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="57daa-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="57daa-117">Указание выравнивания текста для ячеек DataGridView</span><span class="sxs-lookup"><span data-stu-id="57daa-117">To specify the text alignment of DataGridView cells</span></span>  
  
- <span data-ttu-id="57daa-118">Задайте для свойства <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> <xref:System.Windows.Forms.DataGridViewCellStyle> одно из значений перечисления <xref:System.Windows.Forms.DataGridViewContentAlignment>.</span><span class="sxs-lookup"><span data-stu-id="57daa-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="57daa-119">В следующем примере кода устанавливается выравнивание для определенного столбца с помощью свойства <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> столбца.</span><span class="sxs-lookup"><span data-stu-id="57daa-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="57daa-120">Пример</span><span class="sxs-lookup"><span data-stu-id="57daa-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57daa-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="57daa-121">Compiling the Code</span></span>  
 <span data-ttu-id="57daa-122">Для этих примеров требуются:</span><span class="sxs-lookup"><span data-stu-id="57daa-122">These examples require:</span></span>  
  
- <span data-ttu-id="57daa-123">Элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`, содержащий столбец с именем `UnitPrice`, столбец с именем `ShipDate`и столбец с именем `CustomerName`.</span><span class="sxs-lookup"><span data-stu-id="57daa-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
- <span data-ttu-id="57daa-124">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57daa-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="57daa-125">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="57daa-125">Robust Programming</span></span>  
 <span data-ttu-id="57daa-126">Для обеспечения максимальной масштабируемости следует совместно использовать объекты <xref:System.Windows.Forms.DataGridViewCellStyle> в нескольких строках, столбцах или ячейках, использующих одни и те же стили, а не задавать свойства стиля для каждого элемента отдельно.</span><span class="sxs-lookup"><span data-stu-id="57daa-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="57daa-127">Подробнее см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="57daa-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57daa-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="57daa-128">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="57daa-129">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57daa-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="57daa-130">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57daa-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="57daa-131">Форматирование данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57daa-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="57daa-132">Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="57daa-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="57daa-133">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="57daa-133">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
