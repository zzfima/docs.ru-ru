---
title: Практическое руководство. Настройка цветов в приложениях ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: db64ee353cc71cf39516e5ee0a08cf4b9627548c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709646"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="7d4e4-102">Практическое руководство. Настройка цветов в приложениях ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7d4e4-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="7d4e4-103">Внешний вид <xref:System.Windows.Forms.ToolStrip> можно настроить с помощью класса <xref:System.Windows.Forms.ToolStripProfessionalRenderer> для использования пользовательских цветов.</span><span class="sxs-lookup"><span data-stu-id="7d4e4-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d4e4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7d4e4-104">Example</span></span>  
 <span data-ttu-id="7d4e4-105">В следующем примере кода показано, как использовать <xref:System.Windows.Forms.ToolStripProfessionalRenderer> для определения пользовательских цветов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7d4e4-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d4e4-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7d4e4-106">Compiling the Code</span></span>  
 <span data-ttu-id="7d4e4-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7d4e4-107">This example requires:</span></span>  
  
-   <span data-ttu-id="7d4e4-108">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="7d4e4-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7d4e4-109">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="7d4e4-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7d4e4-110">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="7d4e4-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d4e4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7d4e4-111">See also</span></span>
- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
