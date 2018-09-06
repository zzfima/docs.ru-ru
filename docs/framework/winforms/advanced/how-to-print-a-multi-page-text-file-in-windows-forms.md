---
title: Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], printing multiple pages
- text [Windows Forms], printing Windows Forms
- Windows Forms, printing text
- printing [Windows Forms], text
ms.assetid: 362427f8-03d4-4826-b49f-60ab066ad322
ms.openlocfilehash: b8cfba338bb318139bedf5595df8bad666c201bd
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43866910"
---
# <a name="how-to-print-a-multi-page-text-file-in-windows-forms"></a><span data-ttu-id="7681e-102">Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7681e-102">How to: Print a Multi-Page Text File in Windows Forms</span></span>
<span data-ttu-id="7681e-103">В приложениях Windows очень часто используется печать текста.</span><span class="sxs-lookup"><span data-stu-id="7681e-103">It is very common for Windows-based applications to print text.</span></span> <span data-ttu-id="7681e-104">Класс <xref:System.Drawing.Graphics> предоставляет методы для рисования объектов (графических или текстовых) на таких устройствах, как экран или принтер.</span><span class="sxs-lookup"><span data-stu-id="7681e-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects (graphics or text) to a device, such as a screen or printer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7681e-105">Методы <xref:System.Windows.Forms.TextRenderer.DrawText%2A> класса <xref:System.Windows.Forms.TextRenderer> не поддерживаются для печати.</span><span class="sxs-lookup"><span data-stu-id="7681e-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of <xref:System.Windows.Forms.TextRenderer> are not supported for printing.</span></span> <span data-ttu-id="7681e-106">Для рисования текста в целях печати следует всегда использовать методы <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics>, как показано в примере кода ниже.</span><span class="sxs-lookup"><span data-stu-id="7681e-106">You should always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of <xref:System.Drawing.Graphics>, as shown in the following code example, to draw text for printing purposes.</span></span>  
  
### <a name="to-print-text"></a><span data-ttu-id="7681e-107">Печать текста</span><span class="sxs-lookup"><span data-stu-id="7681e-107">To print text</span></span>  
  
1.  <span data-ttu-id="7681e-108">Добавьте в форму компонент <xref:System.Drawing.Printing.PrintDocument> и строку.</span><span class="sxs-lookup"><span data-stu-id="7681e-108">Add a <xref:System.Drawing.Printing.PrintDocument> component and a string to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#8)]
     [!code-vb[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#8)]  
  
2.  <span data-ttu-id="7681e-109">Для печати документа укажите его в качестве значения свойства <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>, а затем откройте и прочтите содержимое документа до добавленной ранее строки.</span><span class="sxs-lookup"><span data-stu-id="7681e-109">If printing a document, set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the documents contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#1)]  
  
3.  <span data-ttu-id="7681e-110">Чтобы вычислить длину строки и число строк на страницу, в обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage> используйте свойство <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs> и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="7681e-110">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the document contents to calculate line length and lines per page.</span></span> <span data-ttu-id="7681e-111">Нарисовав очередную страницу, проверьте, является ли она последней, и установите соответствующим образом свойство <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="7681e-111">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="7681e-112">Событие <xref:System.Drawing.Printing.PrintDocument.PrintPage> возникает до тех пор, пока значение свойства <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> не станет равно `false`.</span><span class="sxs-lookup"><span data-stu-id="7681e-112">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="7681e-113">Кроме того, убедитесь в том, что событие <xref:System.Drawing.Printing.PrintDocument.PrintPage> связано со своим методом обработки событий.</span><span class="sxs-lookup"><span data-stu-id="7681e-113">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
     <span data-ttu-id="7681e-114">В примере кода ниже обработчик событий используется для печати содержимого файла testPage.txt тем шрифтом, который используется в форме.</span><span class="sxs-lookup"><span data-stu-id="7681e-114">In the following code example, the event handler is used to print the contents of the "testPage.txt" file in the same font as is used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="7681e-115">Вызовите метод <xref:System.Drawing.Printing.PrintDocument.Print%2A> для инициации события <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="7681e-115">Call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to raise the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="7681e-116">Пример</span><span class="sxs-lookup"><span data-stu-id="7681e-116">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7681e-117">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7681e-117">Compiling the Code</span></span>  
 <span data-ttu-id="7681e-118">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7681e-118">This example requires:</span></span>  
  
-   <span data-ttu-id="7681e-119">текстовый файл с именем testPage.txt, содержащий текст для печати и находящийся в корне диска C:\\;</span><span class="sxs-lookup"><span data-stu-id="7681e-119">A text file named testPage.txt containing the text to print, located in the root of drive C:\\.</span></span> <span data-ttu-id="7681e-120">чтобы напечатать другой файл, измените код;</span><span class="sxs-lookup"><span data-stu-id="7681e-120">Edit the code to print a different file.</span></span>  
  
-   <span data-ttu-id="7681e-121">ссылки на сборки System, System.Windows.Forms и System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="7681e-121">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
-   <span data-ttu-id="7681e-122">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="7681e-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7681e-123">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="7681e-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="7681e-124">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="7681e-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7681e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7681e-125">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [<span data-ttu-id="7681e-126">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7681e-126">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
