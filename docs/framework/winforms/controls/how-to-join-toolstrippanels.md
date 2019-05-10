---
title: Практическое руководство. Соединение нескольких элементов управления ToolStripPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
ms.openlocfilehash: 5ef934aa1e72b0793ca938953fe18efcbb212adb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651622"
---
# <a name="how-to-join-toolstrippanels"></a><span data-ttu-id="c9bcf-102">Практическое руководство. Соединение нескольких элементов управления ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="c9bcf-102">How to: Join ToolStripPanels</span></span>
<span data-ttu-id="c9bcf-103">Элементы управления <xref:System.Windows.Forms.ToolStrip> можно подключать к <xref:System.Windows.Forms.ToolStripPanel> во время выполнения, благодаря чему обеспечивается гибкость приложений с интерфейсом MDI.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-103">You can join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel> at run time, which provides the flexibility of multiple-document interface (MDI) applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9bcf-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c9bcf-104">Example</span></span>  
 <span data-ttu-id="c9bcf-105">В примере кода ниже показано, как подключить элементы управления <xref:System.Windows.Forms.ToolStrip> к <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-105">The following code example demonstrates how to join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c9bcf-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c9bcf-106">Compiling the Code</span></span>  
 <span data-ttu-id="c9bcf-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c9bcf-107">This example requires:</span></span>  
  
- <span data-ttu-id="c9bcf-108">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c9bcf-109">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c9bcf-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c9bcf-110">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bcf-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c9bcf-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- [<span data-ttu-id="c9bcf-112">Практическое руководство. Руководство.</span><span class="sxs-lookup"><span data-stu-id="c9bcf-112">How to: Use ToolStripPanels for MDI</span></span>](how-to-use-toolstrippanels-for-mdi.md)
