---
title: Практическое руководство. Использование элементов управления ToolStripPanel при создании форм MDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], using ToolStripPanels [Windows Forms]
- ToolStripPanel control [Windows Forms], using for MDI
- toolbars [Windows Forms], using for MDI
ms.assetid: d6b884fc-0846-465f-83c3-5dc0fe93b00f
ms.openlocfilehash: 42d4ed23f477f545c4ff2be53c36d8ea86d3b4f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785766"
---
# <a name="how-to-use-toolstrippanels-for-mdi"></a><span data-ttu-id="d7a79-102">Практическое руководство. Использование элементов управления ToolStripPanel при создании форм MDI</span><span class="sxs-lookup"><span data-stu-id="d7a79-102">How to: Use ToolStripPanels for MDI</span></span>
<span data-ttu-id="d7a79-103"><xref:System.Windows.Forms.ToolStripPanel> обеспечивает гибкость для приложений многодокументного интерфейса (MDI) с помощью метода <xref:System.Windows.Forms.ToolStripPanel.Join%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7a79-103">The <xref:System.Windows.Forms.ToolStripPanel> provides flexibility for multiple-document interface (MDI) applications by using the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7a79-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d7a79-104">Example</span></span>  
 <span data-ttu-id="d7a79-105">В примере кода ниже показано использование элементов управления <xref:System.Windows.Forms.ToolStripPanel> с формой MDI.</span><span class="sxs-lookup"><span data-stu-id="d7a79-105">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls for MDI.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7a79-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d7a79-106">Compiling the Code</span></span>  
 <span data-ttu-id="d7a79-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="d7a79-107">This example requires:</span></span>  
  
- <span data-ttu-id="d7a79-108">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d7a79-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d7a79-109">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d7a79-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d7a79-110">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="d7a79-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a79-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d7a79-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripPanel>
- [<span data-ttu-id="d7a79-112">Практическое руководство. Соединение нескольких ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="d7a79-112">How to: Join ToolStripPanels</span></span>](how-to-join-toolstrippanels.md)
