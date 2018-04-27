---
title: Практическое руководство. Настройка полей флажков и значков для объекта MenuStrip
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
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f138d3a145e5cbbcff23d531970b5d5d71864dc2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="9d91c-102">Практическое руководство. Настройка полей флажков и значков для объекта MenuStrip</span><span class="sxs-lookup"><span data-stu-id="9d91c-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="9d91c-103">Элемент управления <xref:System.Windows.Forms.MenuStrip> можно настраивать, устанавливая свойства <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> и <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> в различных сочетаниях. </span><span class="sxs-lookup"><span data-stu-id="9d91c-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d91c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9d91c-104">Example</span></span>  
 <span data-ttu-id="9d91c-105">В примере кода ниже показано, как установить и настроить поля флажков и значков для элемента управления <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="9d91c-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="9d91c-106">Для элементов управления <xref:System.Windows.Forms.ContextMenuStrip> и <xref:System.Windows.Forms.MenuStrip> процедура одинакова.</span><span class="sxs-lookup"><span data-stu-id="9d91c-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9d91c-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9d91c-107">Compiling the Code</span></span>  
 <span data-ttu-id="9d91c-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="9d91c-108">This example requires:</span></span>  
  
-   <span data-ttu-id="9d91c-109">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9d91c-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9d91c-110">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9d91c-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9d91c-111">Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] , можно также вставить код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="9d91c-111">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="9d91c-112">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9d91c-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d91c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9d91c-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [<span data-ttu-id="9d91c-114">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9d91c-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="9d91c-115">Практическое руководство. Включение полей флажков и значков для элементов управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="9d91c-115">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
