---
title: Программное изменение размеров ячеек в соответствии с содержимым элемента управления DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: df3b378a8ba358fa0bfe549a7901b3d59d53f556
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742446"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ec92f-102">Практическое руководство. Программное изменение размера ячеек элемента управления DataGridView в соответствии с размером отображаемых данных в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ec92f-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ec92f-103">С помощью методов элемента управления <xref:System.Windows.Forms.DataGridView> можно изменять размеры строк, столбцов и заголовков, с тем чтобы значения отображались полностью без усечения.</span><span class="sxs-lookup"><span data-stu-id="ec92f-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="ec92f-104">Эти методы можно использовать для изменения размеров элементов <xref:System.Windows.Forms.DataGridView> в любое удобное время.</span><span class="sxs-lookup"><span data-stu-id="ec92f-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="ec92f-105">Кроме того, элемент управления можно настроить на автоматическое изменение размеров при изменении содержимого.</span><span class="sxs-lookup"><span data-stu-id="ec92f-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="ec92f-106">Однако такой подход может быть неэффективным при работе с большими наборами данных или их частом изменении.</span><span class="sxs-lookup"><span data-stu-id="ec92f-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="ec92f-107">Дополнительные сведения см. [в разделе Параметры изменения размера в элементе управления Windows Forms DataGridView](sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="ec92f-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="ec92f-108">Как правило, программное изменение размеров элементов <xref:System.Windows.Forms.DataGridView> в соответствии с содержимым требуется только при загрузке данных из источника данных или при изменении значений пользователем.</span><span class="sxs-lookup"><span data-stu-id="ec92f-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="ec92f-109">Это позволяет оптимизировать производительность, а также предоставить пользователям возможность изменять размеры строк и столбцов вручную с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="ec92f-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="ec92f-110">В примере кода ниже показаны возможности, доступные для программного изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="ec92f-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec92f-111">Пример</span><span class="sxs-lookup"><span data-stu-id="ec92f-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ec92f-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ec92f-112">Compiling the Code</span></span>  
 <span data-ttu-id="ec92f-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ec92f-113">This example requires:</span></span>  
  
- <span data-ttu-id="ec92f-114">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ec92f-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec92f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ec92f-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="ec92f-116">Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ec92f-116">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ec92f-117">Изменение размеров управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ec92f-117">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ec92f-118">Практическое руководство. Автоматическое изменение размера ячеек при изменении содержимого в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ec92f-118">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
