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
ms.openlocfilehash: bd858279a4d8a3509a91bcd1c62fb1f61d6d2bb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931793"
---
# <a name="how-to-print-a-multi-page-text-file-in-windows-forms"></a><span data-ttu-id="173fb-102">Практическое руководство. Печать многостраничных текстовых файлов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="173fb-102">How to: Print a Multi-Page Text File in Windows Forms</span></span>
<span data-ttu-id="173fb-103">В приложениях Windows очень часто используется печать текста.</span><span class="sxs-lookup"><span data-stu-id="173fb-103">It is very common for Windows-based applications to print text.</span></span> <span data-ttu-id="173fb-104">Класс <xref:System.Drawing.Graphics> предоставляет методы для рисования объектов (графических или текстовых) на таких устройствах, как экран или принтер.</span><span class="sxs-lookup"><span data-stu-id="173fb-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects (graphics or text) to a device, such as a screen or printer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="173fb-105">Методы <xref:System.Windows.Forms.TextRenderer.DrawText%2A> класса <xref:System.Windows.Forms.TextRenderer> не поддерживаются для печати.</span><span class="sxs-lookup"><span data-stu-id="173fb-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of <xref:System.Windows.Forms.TextRenderer> are not supported for printing.</span></span> <span data-ttu-id="173fb-106">Для рисования текста в целях печати следует всегда использовать методы <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics>, как показано в примере кода ниже.</span><span class="sxs-lookup"><span data-stu-id="173fb-106">You should always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of <xref:System.Drawing.Graphics>, as shown in the following code example, to draw text for printing purposes.</span></span>  
  
### <a name="to-print-text"></a><span data-ttu-id="173fb-107">Печать текста</span><span class="sxs-lookup"><span data-stu-id="173fb-107">To print text</span></span>  
  
1. <span data-ttu-id="173fb-108">Добавьте в форму компонент <xref:System.Drawing.Printing.PrintDocument> и строку.</span><span class="sxs-lookup"><span data-stu-id="173fb-108">Add a <xref:System.Drawing.Printing.PrintDocument> component and a string to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#8)]
     [!code-vb[System.Drawing.Printing.PrintExamples#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#8)]  
  
2. <span data-ttu-id="173fb-109">Для печати документа укажите его в качестве значения свойства <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>, а затем откройте и прочтите содержимое документа до добавленной ранее строки.</span><span class="sxs-lookup"><span data-stu-id="173fb-109">If printing a document, set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the documents contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintExamples#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#1)]  
  
3. <span data-ttu-id="173fb-110">Чтобы вычислить длину строки и число строк на страницу, в обработчике событий <xref:System.Drawing.Printing.PrintDocument.PrintPage> используйте свойство <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs> и содержимое документа.</span><span class="sxs-lookup"><span data-stu-id="173fb-110">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the document contents to calculate line length and lines per page.</span></span> <span data-ttu-id="173fb-111">Нарисовав очередную страницу, проверьте, является ли она последней, и установите соответствующим образом свойство <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> класса <xref:System.Drawing.Printing.PrintPageEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="173fb-111">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="173fb-112">Событие <xref:System.Drawing.Printing.PrintDocument.PrintPage> возникает до тех пор, пока значение свойства <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> не станет равно `false`.</span><span class="sxs-lookup"><span data-stu-id="173fb-112">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="173fb-113">Кроме того, убедитесь в том, что событие <xref:System.Drawing.Printing.PrintDocument.PrintPage> связано со своим методом обработки событий.</span><span class="sxs-lookup"><span data-stu-id="173fb-113">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
     <span data-ttu-id="173fb-114">В примере кода ниже обработчик событий используется для печати содержимого файла testPage.txt тем шрифтом, который используется в форме.</span><span class="sxs-lookup"><span data-stu-id="173fb-114">In the following code example, the event handler is used to print the contents of the "testPage.txt" file in the same font as is used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintExamples#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="173fb-115">Вызовите метод <xref:System.Drawing.Printing.PrintDocument.Print%2A> для инициации события <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="173fb-115">Call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to raise the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintExamples#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="173fb-116">Пример</span><span class="sxs-lookup"><span data-stu-id="173fb-116">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintExamples#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintExamples#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="173fb-117">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="173fb-117">Compiling the Code</span></span>  
 <span data-ttu-id="173fb-118">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="173fb-118">This example requires:</span></span>  
  
- <span data-ttu-id="173fb-119">текстовый файл с именем testPage.txt, содержащий текст для печати и находящийся в корне диска C:\\;</span><span class="sxs-lookup"><span data-stu-id="173fb-119">A text file named testPage.txt containing the text to print, located in the root of drive C:\\.</span></span> <span data-ttu-id="173fb-120">чтобы напечатать другой файл, измените код;</span><span class="sxs-lookup"><span data-stu-id="173fb-120">Edit the code to print a different file.</span></span>  
  
- <span data-ttu-id="173fb-121">ссылки на сборки System, System.Windows.Forms и System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="173fb-121">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
- <span data-ttu-id="173fb-122">Сведения о создании этого примера из командной строки для Visual Basic или визуального элемента C#см. в разделе [Сборка из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Сборка из командной строки с помощью csc. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="173fb-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="173fb-123">Этот пример можно также построить в Visual Studio, вставляя код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="173fb-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173fb-124">См. также</span><span class="sxs-lookup"><span data-stu-id="173fb-124">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="173fb-125">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="173fb-125">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
