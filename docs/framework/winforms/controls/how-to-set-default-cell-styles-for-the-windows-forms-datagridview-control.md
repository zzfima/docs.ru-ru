---
title: Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: e52729a4ff5b95cd45a970068f1874ad77f8ce35
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319200"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="4110d-102">Практическое руководство. Установка стилей ячейки по умолчанию для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4110d-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4110d-103">С помощью элемента управления <xref:System.Windows.Forms.DataGridView> можно задавать стили ячеек по умолчанию для всего элемента управления или для определенных столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="4110d-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="4110d-104">Эти стили по умолчанию отфильтровываются на уровне элемента управления, затем на уровне столбца, строки и, наконец, на уровне ячейки.</span><span class="sxs-lookup"><span data-stu-id="4110d-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="4110d-105">Если определенное свойство <xref:System.Windows.Forms.DataGridViewCellStyle> не задано на уровне ячейки, то на уровне строки используется свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4110d-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="4110d-106">Если свойство не задано и на уровне строки, то используется значение столбца по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4110d-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="4110d-107">Наконец, если свойство не задано на уровне столбца, то по умолчанию используется значение <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="4110d-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="4110d-108">Использование этой настройки позволит избежать дублирования значений свойств на нескольких уровнях.</span><span class="sxs-lookup"><span data-stu-id="4110d-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="4110d-109">На каждом уровне нужно просто указывать стили, отличающиеся от вышестоящих уровней.</span><span class="sxs-lookup"><span data-stu-id="4110d-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="4110d-110">Дополнительные сведения см. в разделе [стили ячеек элемента управления DataGridView Windows Forms в](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4110d-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="4110d-111">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="4110d-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="4110d-112">Также см. раздел [Как Установка стилей ячейки по умолчанию и форматов данных, для Windows Forms с помощью конструктора элемента управления DataGridView](default-cell-styles-datagridview.md).</span><span class="sxs-lookup"><span data-stu-id="4110d-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="4110d-113">Программная установка стилей ячейки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4110d-113">To set the default cell styles programmatically</span></span>  
  
1. <span data-ttu-id="4110d-114">Задайте свойства <xref:System.Windows.Forms.DataGridViewCellStyle>, извлеченные с помощью свойства <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4110d-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2. <span data-ttu-id="4110d-115">Создайте и инициализируйте новые объекты <xref:System.Windows.Forms.DataGridViewCellStyle> для использования несколькими строками и столбцами.</span><span class="sxs-lookup"><span data-stu-id="4110d-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3. <span data-ttu-id="4110d-116">Задайте свойство `DefaultCellStyle` определенных строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="4110d-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="4110d-117">Пример</span><span class="sxs-lookup"><span data-stu-id="4110d-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4110d-118">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4110d-118">Compiling the Code</span></span>  
 <span data-ttu-id="4110d-119">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="4110d-119">This example requires:</span></span>  
  
-   <span data-ttu-id="4110d-120">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="4110d-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="4110d-121">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4110d-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4110d-122">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="4110d-122">Robust Programming</span></span>  
 <span data-ttu-id="4110d-123">Для максимальной масштабируемости при работе с большими наборами данных объекты <xref:System.Windows.Forms.DataGridViewCellStyle> следует распределить по нескольким строкам, столбцам или ячейкам с одинаковыми стилями, чтобы не задавать свойства стилей для каждого элемента в отдельности.</span><span class="sxs-lookup"><span data-stu-id="4110d-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="4110d-124">Кроме того, следует создать общие строки и обращаться к ним с помощью свойства <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4110d-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="4110d-125">Дополнительные сведения см. в разделе [масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="4110d-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4110d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4110d-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4110d-127">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4110d-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4110d-128">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4110d-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4110d-129">Масштабирование элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4110d-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="4110d-130">Практическое руководство. Установка стилей чередующихся строк для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4110d-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
