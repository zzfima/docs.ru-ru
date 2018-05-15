---
title: Практическое руководство. Управление полосами в элементе управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], manipulating bands
- bands [Windows Forms], manipulating in Windows Forms
- DataGridView control [Windows Forms], manipulating bands
ms.assetid: 1ea3470e-480f-4edc-bcbd-51373eca3856
ms.openlocfilehash: cf06e213a014a91c9738123f9d799be1669620d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-manipulate-bands-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="cd187-102">Практическое руководство. Управление полосами в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd187-102">How to: Manipulate Bands in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cd187-103">В примерах кода ниже показаны различные способы работы со строками и столбцами <xref:System.Windows.Forms.DataGridView> с помощью свойств класса <xref:System.Windows.Forms.DataGridViewBand>, от которого наследуются классы <xref:System.Windows.Forms.DataGridViewRow> и <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="cd187-103">The following code example shows various ways to manipulate <xref:System.Windows.Forms.DataGridView> rows and columns using properties of the <xref:System.Windows.Forms.DataGridViewBand> class from which the <xref:System.Windows.Forms.DataGridViewRow> and <xref:System.Windows.Forms.DataGridViewColumn> classes derive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd187-104">Пример</span><span class="sxs-lookup"><span data-stu-id="cd187-104">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewBandDemo.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewBandDemo.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewbanddemo.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cd187-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="cd187-105">Compiling the Code</span></span>  
 <span data-ttu-id="cd187-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="cd187-106">This example requires:</span></span>  
  
-   <span data-ttu-id="cd187-107">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="cd187-107">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="cd187-108">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="cd187-108">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="cd187-109">Можно также построить этот пример, в Visual Studio, вставив код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="cd187-109">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="cd187-110">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="cd187-110">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd187-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cd187-111">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewBand>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="cd187-112">Программирование с использованием ячеек, строк и столбцов в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cd187-112">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
