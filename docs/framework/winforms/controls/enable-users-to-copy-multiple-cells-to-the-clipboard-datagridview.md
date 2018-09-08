---
title: Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: 47ccd88ed30341e609b0569aaebc2db4dda3e40e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197829"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="10063-102">Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10063-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="10063-103">При включении копирования ячеек данные в элементе управления <xref:System.Windows.Forms.DataGridView> становятся доступны для других приложений с помощью <xref:System.Windows.Forms.Clipboard>.</span><span class="sxs-lookup"><span data-stu-id="10063-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="10063-104">Значения выделенных ячеек преобразуются в строки и добавляются в буфер обмена в виде значений, разделенных символами табуляции, для вставки в такие приложения, как "Блокнот" или Excel, и в виде таблицы в формате HTML для вставки в такие приложения, как Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="10063-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="10063-105">Можно настроить копирование ячеек, чтобы копировать только значения ячеек, включить текст заголовка строки и столбца в данные буфера обмена или включать текст заголовка только в том случае, когда пользователь выбирает все строки или столбцы.</span><span class="sxs-lookup"><span data-stu-id="10063-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="10063-106">В зависимости от режима выделения пользователи могут выбрать несколько разрозненных групп ячеек.</span><span class="sxs-lookup"><span data-stu-id="10063-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="10063-107">При копировании ячеек в буфер обмена строки и столбцы, не имеющие выделенных ячеек, не копируются.</span><span class="sxs-lookup"><span data-stu-id="10063-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="10063-108">Все строки или столбцы становятся строками и столбцами в таблице данных, скопированной в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="10063-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="10063-109">Невыделенные ячейки в этих строках или столбцах копируются в буфер обмена в виде пустых заполнителей.</span><span class="sxs-lookup"><span data-stu-id="10063-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="10063-110">Разрешение копирования ячеек</span><span class="sxs-lookup"><span data-stu-id="10063-110">To enable cell copying</span></span>  
  
-   <span data-ttu-id="10063-111">Задайте свойство <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="10063-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="10063-112">Пример</span><span class="sxs-lookup"><span data-stu-id="10063-112">Example</span></span>  
 <span data-ttu-id="10063-113">В следующем полном примере кода показано, как ячейки копируются в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="10063-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="10063-114">В этом примере имеется кнопка, которая копирует выбранные ячейки в буфер обмена, используя метод <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType>, и отображает содержимое буфера обмена в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="10063-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10063-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="10063-115">Compiling the Code</span></span>  
 <span data-ttu-id="10063-116">Для этого примера кода требуются:</span><span class="sxs-lookup"><span data-stu-id="10063-116">This code requires:</span></span>  
  
-   <span data-ttu-id="10063-117">ссылки на сборки N:System и N:System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="10063-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="10063-118">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="10063-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="10063-119">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="10063-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="10063-120">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="10063-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10063-121">См. также</span><span class="sxs-lookup"><span data-stu-id="10063-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>  
 [<span data-ttu-id="10063-122">Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10063-122">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
