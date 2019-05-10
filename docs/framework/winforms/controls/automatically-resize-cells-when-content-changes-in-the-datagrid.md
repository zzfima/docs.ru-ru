---
title: Практическое руководство. Автоматическое изменение размера ячеек при изменении содержимого в элементе управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: 436f5d4a77a3119fe5b16afa1a4e71c55b3751dc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587632"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="00121-102">Практическое руководство. Автоматическое изменение размера ячеек при изменении содержимого в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00121-102">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="00121-103">Для элемента управления <xref:System.Windows.Forms.DataGridView> можно настроить автоматическое изменение размера строк, столбцов и заголовков при изменении содержимого так, чтобы значения ячеек могли отображаться в них без усечения.</span><span class="sxs-lookup"><span data-stu-id="00121-103">You can configure the <xref:System.Windows.Forms.DataGridView> control to resize its rows, columns, and headers automatically whenever content changes, so that cells are always large enough to display their values without clipping.</span></span>  
  
 <span data-ttu-id="00121-104">Ограничить ячейки для определения нового размера можно несколькими вариантами.</span><span class="sxs-lookup"><span data-stu-id="00121-104">You have many options to restrict which cells are used to determine the new sizes.</span></span> <span data-ttu-id="00121-105">Например, для элемента управления можно настроить автоматическое изменение ширины, исходя исключительно из значений в строках, отображаемых в данный момент.</span><span class="sxs-lookup"><span data-stu-id="00121-105">For example, you can configure the control to automatically resize the width of its columns based only on the values in rows that are currently displayed.</span></span> <span data-ttu-id="00121-106">Благодаря этому можно добиться большей эффективности при работе с большим количеством строк. Однако в этом случае может потребоваться использовать методы изменения размера <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> для контроля размера в нужный момент.</span><span class="sxs-lookup"><span data-stu-id="00121-106">With this, you can avoid inefficiency when working with large numbers of rows, although in this case, you might want to use sizing methods such as <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> to adjust sizes at times of your choosing.</span></span>  
  
 <span data-ttu-id="00121-107">Дополнительные сведения об автоматическом изменении размера см. в разделе [параметров изменения размеров элемента управления DataGridView Windows Forms в](sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="00121-107">For more information about automatic resizing, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="00121-108">В примере кода ниже показаны варианты автоматического изменения размера.</span><span class="sxs-lookup"><span data-stu-id="00121-108">The following code example demonstrates the options available for automatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00121-109">Пример</span><span class="sxs-lookup"><span data-stu-id="00121-109">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00121-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="00121-110">Compiling the Code</span></span>  
 <span data-ttu-id="00121-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="00121-111">This example requires:</span></span>  
  
- <span data-ttu-id="00121-112">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="00121-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="00121-113">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="00121-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="00121-114">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="00121-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00121-115">См. также</span><span class="sxs-lookup"><span data-stu-id="00121-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="00121-116">Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00121-116">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="00121-117">Изменение размеров управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00121-117">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="00121-118">Практическое руководство. Программное изменение размера ячеек в соответствии с размером в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00121-118">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
