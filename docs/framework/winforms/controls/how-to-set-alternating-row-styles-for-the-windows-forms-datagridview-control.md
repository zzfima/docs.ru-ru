---
title: Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
ms.openlocfilehash: d113c45469f6a78c94b9489bd82f9e55b5b96bba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962276"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="6832e-102">Практическое руководство. Настройка формата отображения четных строк для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6832e-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6832e-103">Данные в таблицах часто представлены в формате, подобном бухгалтерским книгам: в чередующихся строках используется разный цвет фона.</span><span class="sxs-lookup"><span data-stu-id="6832e-103">Tabular data is often presented to users in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="6832e-104">Такой формат позволяет проще определять, какие ячейки находятся в какой строке, что особенно удобно в широких таблицах со множеством столбцов.</span><span class="sxs-lookup"><span data-stu-id="6832e-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="6832e-105">С помощью элемента управления <xref:System.Windows.Forms.DataGridView> можно указать полные сведения о стиле для чередующихся строк.</span><span class="sxs-lookup"><span data-stu-id="6832e-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="6832e-106">Таким образом для различения чередующихся строк можно использовать такие характеристики стиля, как цвет фона, цвет текста и начертание шрифта.</span><span class="sxs-lookup"><span data-stu-id="6832e-106">This enables you use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span>  
  
 <span data-ttu-id="6832e-107">Эта задача поддерживается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6832e-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="6832e-108">Также см. раздел [Как Установите чередующиеся стили строк для элемента управления Windows Forms DataGridView с помощью конструктора](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="6832e-108">Also see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-set-alternating-row-styles-programmatically"></a><span data-ttu-id="6832e-109">Задание стилей чередующихся строк программными средствами</span><span class="sxs-lookup"><span data-stu-id="6832e-109">To set alternating row styles programmatically</span></span>  
  
- <span data-ttu-id="6832e-110">Задайте свойства объектов <xref:System.Windows.Forms.DataGridViewCellStyle>, возвращаемых свойствами <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="6832e-110">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> objects returned by the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties of the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    > <span data-ttu-id="6832e-111">Стили, заданные с помощью свойств <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>, переопределяют стили, заданные на уровне столбцов и элемента управления <xref:System.Windows.Forms.DataGridView>. Однако они, в свою очередь, переопределяются стилями, заданными на уровне отдельных строк и ячеек.</span><span class="sxs-lookup"><span data-stu-id="6832e-111">The styles specified using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties override the styles specified on the column and <xref:System.Windows.Forms.DataGridView> level, but are overridden by the styles set on the individual row and cell level.</span></span> <span data-ttu-id="6832e-112">Дополнительные сведения см. [в разделе Стили ячеек в элементе управления Windows Forms DataGridView](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="6832e-112">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6832e-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="6832e-113">Compiling the Code</span></span>  
 <span data-ttu-id="6832e-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="6832e-114">This example requires:</span></span>  
  
- <span data-ttu-id="6832e-115">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="6832e-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="6832e-116">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6832e-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6832e-117">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="6832e-117">Robust Programming</span></span>  
 <span data-ttu-id="6832e-118">Для максимальной масштабируемости объекты <xref:System.Windows.Forms.DataGridViewCellStyle> следует распределить по нескольким строкам, столбцам или ячейкам с одинаковыми стилями, чтобы не задавать свойства стилей для каждого элемента в отдельности.</span><span class="sxs-lookup"><span data-stu-id="6832e-118">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="6832e-119">Дополнительные сведения см. в разделе рекомендации [по масштабированию элемента управления Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="6832e-119">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6832e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6832e-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="6832e-121">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6832e-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6832e-122">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6832e-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6832e-123">Масштабирование элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6832e-123">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6832e-124">Практическое руководство. Установка стилей шрифтов и цветов в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="6832e-124">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
