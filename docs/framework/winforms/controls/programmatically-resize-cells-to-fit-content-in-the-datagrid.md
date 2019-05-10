---
title: Практическое руководство. Программное изменение размера ячеек элемента управления DataGridView в соответствии с размером отображаемых данных в Windows Forms
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
ms.openlocfilehash: 8c95d60ba36275ec4d0e263f97bc28a559c1f38e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64654458"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5a166-102">Практическое руководство. Программное изменение размера ячеек элемента управления DataGridView в соответствии с размером отображаемых данных в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a166-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5a166-103">С помощью методов элемента управления <xref:System.Windows.Forms.DataGridView> можно изменять размеры строк, столбцов и заголовков, с тем чтобы значения отображались полностью без усечения.</span><span class="sxs-lookup"><span data-stu-id="5a166-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="5a166-104">Эти методы можно использовать для изменения размеров элементов <xref:System.Windows.Forms.DataGridView> в любое удобное время.</span><span class="sxs-lookup"><span data-stu-id="5a166-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="5a166-105">Кроме того, элемент управления можно настроить на автоматическое изменение размеров при изменении содержимого.</span><span class="sxs-lookup"><span data-stu-id="5a166-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="5a166-106">Однако такой подход может быть неэффективным при работе с большими наборами данных или их частом изменении.</span><span class="sxs-lookup"><span data-stu-id="5a166-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="5a166-107">Дополнительные сведения см. в разделе [параметров изменения размеров элемента управления DataGridView Windows Forms в](sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="5a166-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="5a166-108">Как правило, программное изменение размеров элементов <xref:System.Windows.Forms.DataGridView> в соответствии с содержимым требуется только при загрузке данных из источника данных или при изменении значений пользователем.</span><span class="sxs-lookup"><span data-stu-id="5a166-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="5a166-109">Это позволяет оптимизировать производительность, а также предоставить пользователям возможность изменять размеры строк и столбцов вручную с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="5a166-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="5a166-110">В примере кода ниже показаны возможности, доступные для программного изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="5a166-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a166-111">Пример</span><span class="sxs-lookup"><span data-stu-id="5a166-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5a166-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5a166-112">Compiling the Code</span></span>  
 <span data-ttu-id="5a166-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="5a166-113">This example requires:</span></span>  
  
- <span data-ttu-id="5a166-114">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="5a166-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="5a166-115">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5a166-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="5a166-116">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="5a166-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a166-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5a166-117">See also</span></span>

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
- [<span data-ttu-id="5a166-118">Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a166-118">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5a166-119">Изменение размеров управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a166-119">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5a166-120">Практическое руководство. Автоматическое изменение размера ячеек при изменении содержимого в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a166-120">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
