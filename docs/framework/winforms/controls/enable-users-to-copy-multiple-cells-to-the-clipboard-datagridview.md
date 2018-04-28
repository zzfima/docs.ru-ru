---
title: Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 72f00ee548a042690ded57a4186f97de47781622
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="b7a94-102">Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7a94-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b7a94-103">При включении копирования ячеек данные в элементе управления <xref:System.Windows.Forms.DataGridView> становятся доступны для других приложений с помощью <xref:System.Windows.Forms.Clipboard>.</span><span class="sxs-lookup"><span data-stu-id="b7a94-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="b7a94-104">Значения выделенных ячеек преобразуются в строки и добавляются в буфер обмена в виде значений, разделенных символами табуляции, для вставки в такие приложения, как "Блокнот" или Excel, и в виде таблицы в формате HTML для вставки в такие приложения, как Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="b7a94-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="b7a94-105">Можно настроить копирование ячеек, чтобы копировать только значения ячеек, включить текст заголовка строки и столбца в данные буфера обмена или включать текст заголовка только в том случае, когда пользователь выбирает все строки или столбцы.</span><span class="sxs-lookup"><span data-stu-id="b7a94-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="b7a94-106">В зависимости от режима выделения пользователи могут выбрать несколько разрозненных групп ячеек.</span><span class="sxs-lookup"><span data-stu-id="b7a94-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="b7a94-107">При копировании ячеек в буфер обмена строки и столбцы, не имеющие выделенных ячеек, не копируются.</span><span class="sxs-lookup"><span data-stu-id="b7a94-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="b7a94-108">Все строки или столбцы становятся строками и столбцами в таблице данных, скопированной в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="b7a94-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="b7a94-109">Невыделенные ячейки в этих строках или столбцах копируются в буфер обмена в виде пустых заполнителей.</span><span class="sxs-lookup"><span data-stu-id="b7a94-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="b7a94-110">Разрешение копирования ячеек</span><span class="sxs-lookup"><span data-stu-id="b7a94-110">To enable cell copying</span></span>  
  
-   <span data-ttu-id="b7a94-111">Задайте свойство <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7a94-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="b7a94-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b7a94-112">Example</span></span>  
 <span data-ttu-id="b7a94-113">В следующем полном примере кода показано, как ячейки копируются в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="b7a94-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="b7a94-114">В этом примере имеется кнопка, которая копирует выбранные ячейки в буфер обмена, используя метод <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType>, и отображает содержимое буфера обмена в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="b7a94-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b7a94-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b7a94-115">Compiling the Code</span></span>  
 <span data-ttu-id="b7a94-116">Для этого примера кода требуются:</span><span class="sxs-lookup"><span data-stu-id="b7a94-116">This code requires:</span></span>  
  
-   <span data-ttu-id="b7a94-117">ссылки на сборки N:System и N:System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b7a94-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b7a94-118">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b7a94-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b7a94-119">Можно также построить этот пример, в Visual Studio, вставив код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="b7a94-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b7a94-120">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b7a94-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a94-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b7a94-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>  
 [<span data-ttu-id="b7a94-122">Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7a94-122">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
