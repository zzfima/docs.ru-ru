---
title: Практическое руководство. Настройка цветов в приложениях, в которых используется элемент управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 971fc8478e6ff2b5745a950daa2f04bfc8d00322
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666393"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="64b34-102">Практическое руководство. Настройка цветов в приложениях, в которых используется элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="64b34-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="64b34-103">Внешний вид <xref:System.Windows.Forms.ToolStrip> можно настроить с помощью класса <xref:System.Windows.Forms.ToolStripProfessionalRenderer> для использования пользовательских цветов.</span><span class="sxs-lookup"><span data-stu-id="64b34-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64b34-104">Пример</span><span class="sxs-lookup"><span data-stu-id="64b34-104">Example</span></span>  
 <span data-ttu-id="64b34-105">В следующем примере кода показано, как использовать <xref:System.Windows.Forms.ToolStripProfessionalRenderer> для определения пользовательских цветов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="64b34-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="64b34-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="64b34-106">Compiling the Code</span></span>  
 <span data-ttu-id="64b34-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="64b34-107">This example requires:</span></span>  
  
- <span data-ttu-id="64b34-108">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="64b34-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="64b34-109">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="64b34-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="64b34-110">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="64b34-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b34-111">См. также</span><span class="sxs-lookup"><span data-stu-id="64b34-111">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
