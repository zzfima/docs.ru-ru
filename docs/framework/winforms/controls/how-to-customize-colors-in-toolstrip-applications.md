---
title: Как выполнить Настройка цветов в приложениях ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 0a7679624d375fac610f6c74f124881d7235eab8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585436"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="34852-102">Как выполнить Настройка цветов в приложениях ToolStrip</span><span class="sxs-lookup"><span data-stu-id="34852-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="34852-103">Внешний вид <xref:System.Windows.Forms.ToolStrip> можно настроить с помощью класса <xref:System.Windows.Forms.ToolStripProfessionalRenderer> для использования пользовательских цветов.</span><span class="sxs-lookup"><span data-stu-id="34852-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34852-104">Пример</span><span class="sxs-lookup"><span data-stu-id="34852-104">Example</span></span>  
 <span data-ttu-id="34852-105">В следующем примере кода показано, как использовать <xref:System.Windows.Forms.ToolStripProfessionalRenderer> для определения пользовательских цветов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="34852-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34852-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="34852-106">Compiling the Code</span></span>  
 <span data-ttu-id="34852-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="34852-107">This example requires:</span></span>  
  
-   <span data-ttu-id="34852-108">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="34852-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="34852-109">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="34852-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="34852-110">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="34852-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="34852-111">Также см. раздел [Как Компиляция и выполнение примера кода завершения Windows Forms с помощью Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="34852-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34852-112">См. также</span><span class="sxs-lookup"><span data-stu-id="34852-112">See also</span></span>
- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
