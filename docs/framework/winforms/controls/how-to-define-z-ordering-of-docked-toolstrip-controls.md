---
title: Практическое руководство. Определение z-порядка закрепленных элементов управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 34d600454a7fa63c7ba59bebded6365cd5401cb4
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45520416"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="19799-102">Практическое руководство. Определение z-порядка закрепленных элементов управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="19799-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="19799-103">Чтобы правильно расположить закрепленный элемент управления <xref:System.Windows.Forms.ToolStrip>, следует правильно выбрать положение этого элемента управления в z-порядке формы.</span><span class="sxs-lookup"><span data-stu-id="19799-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19799-104">Пример</span><span class="sxs-lookup"><span data-stu-id="19799-104">Example</span></span>  
 <span data-ttu-id="19799-105">В примере кода ниже показано, как разместить элемент управления <xref:System.Windows.Forms.ToolStrip> и закрепленный элемент управления <xref:System.Windows.Forms.MenuStrip> путем указания z-порядка.</span><span class="sxs-lookup"><span data-stu-id="19799-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="19799-106">z-порядок определяется порядком, в котором элементы управления <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="19799-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="19799-107">добавляются в коллекцию <xref:System.Windows.Forms.Control.Controls%2A> формы.</span><span class="sxs-lookup"><span data-stu-id="19799-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="19799-108">Измените очередность вызовов метода <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> на обратную и посмотрите, как это отразится на макете.</span><span class="sxs-lookup"><span data-stu-id="19799-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="19799-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="19799-109">Compiling the Code</span></span>  
 <span data-ttu-id="19799-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="19799-110">This example requires:</span></span>  
  
-   <span data-ttu-id="19799-111">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="19799-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="19799-112">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="19799-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="19799-113">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="19799-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="19799-114">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="19799-114">Also se [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19799-115">См. также</span><span class="sxs-lookup"><span data-stu-id="19799-115">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>  
 <xref:System.Windows.Forms.Control.Controls%2A>  
 <xref:System.Windows.Forms.Control.Dock%2A>  
 [<span data-ttu-id="19799-116">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="19799-116">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
