---
title: Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: ebeca5f933eac4da2bf3d4f300866fd2ff52b32a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917674"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1a960-102">Практическое руководство. Изменение внешнего вида границ и линий сетки элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a960-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1a960-103">С помощью <xref:System.Windows.Forms.DataGridView> элемента управления можно настроить внешний вид границ и линий сетки элемента управления, чтобы улучшить взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="1a960-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="1a960-104">В дополнение к стилям границ для ячеек внутри элемента управления можно изменить цвет сетки и стиль границы элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1a960-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="1a960-105">Можно также применить различные стили границ ячеек для обычных ячеек, ячеек заголовка строки и ячеек заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="1a960-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a960-106">Цвет линий сетки используется только с <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single> <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> значениями <xref:System.Windows.Forms.DataGridViewCellBorderStyle> перечисления <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal> <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> ,, и значения перечисления. <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single></span><span class="sxs-lookup"><span data-stu-id="1a960-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="1a960-107">Другие значения этих перечислений используют цвета, заданные операционной системой.</span><span class="sxs-lookup"><span data-stu-id="1a960-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="1a960-108">Кроме того, если стили оформления включены в Windows XP и семействе Windows Server 2003 с помощью <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> метода <xref:System.Windows.Forms.DataGridView.GridColor%2A> , значение свойства не используется.</span><span class="sxs-lookup"><span data-stu-id="1a960-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="1a960-109">Изменение цвета линий сетки программными средствами</span><span class="sxs-lookup"><span data-stu-id="1a960-109">To change the gridline color programmatically</span></span>  
  
- <span data-ttu-id="1a960-110">Задайте свойство <xref:System.Windows.Forms.DataGridView.GridColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a960-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="1a960-111">Изменение стиля границы всего элемента управления DataGridView программным способом</span><span class="sxs-lookup"><span data-stu-id="1a960-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
- <span data-ttu-id="1a960-112">Присвойте свойству <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> одно из значений перечисления <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="1a960-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="1a960-113">Изменение стилей границ для ячеек DataGridView программным способом</span><span class="sxs-lookup"><span data-stu-id="1a960-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
- <span data-ttu-id="1a960-114">Задайте свойства <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>и <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> .</span><span class="sxs-lookup"><span data-stu-id="1a960-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="1a960-115">Пример</span><span class="sxs-lookup"><span data-stu-id="1a960-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1a960-116">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1a960-116">Compiling the Code</span></span>  
 <span data-ttu-id="1a960-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="1a960-117">This example requires:</span></span>  
  
- <span data-ttu-id="1a960-118">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="1a960-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="1a960-119">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a960-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a960-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1a960-120">See also</span></span>

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="1a960-121">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a960-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
