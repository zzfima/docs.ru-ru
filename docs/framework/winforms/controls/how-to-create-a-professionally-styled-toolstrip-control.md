---
title: Практическое руководство. Создание профессионально оформленного элемента управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 6da6e113867efed79dfcd02f3b89ee1f9ae13c4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104596"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="78b5e-102">Практическое руководство. Создание профессионально оформленного элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="78b5e-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="78b5e-103">Вы можете придать элементам управления <xref:System.Windows.Forms.ToolStrip> своего приложения профессиональный внешний вид и поведение, создав собственный класс, производный от типа <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="78b5e-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="78b5e-104">Имеется широкая поддержка этой возможности в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="78b5e-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="78b5e-105">См. [Пошаговое руководство: Создание профессионально оформленного элемента управления ToolStrip](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="78b5e-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="78b5e-106">Пример</span><span class="sxs-lookup"><span data-stu-id="78b5e-106">Example</span></span>  
 <span data-ttu-id="78b5e-107">В следующем примере кода демонстрируется использование <xref:System.Windows.Forms.ToolStrip> элементы управления для создания составного элемента управления, напоминающего **редактируемую** в Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="78b5e-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="78b5e-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="78b5e-108">Compiling the Code</span></span>  
 <span data-ttu-id="78b5e-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="78b5e-109">This example requires:</span></span>  
  
-   <span data-ttu-id="78b5e-110">ссылки на сборки System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="78b5e-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="78b5e-111">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="78b5e-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="78b5e-112">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="78b5e-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="78b5e-113">Также см. в разделе [Пошаговое руководство: Создание профессионально оформленного элемента управления ToolStrip](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="78b5e-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b5e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="78b5e-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="78b5e-115">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="78b5e-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="78b5e-116">Практическое руководство. Связывание с формой стандартных элементов меню</span><span class="sxs-lookup"><span data-stu-id="78b5e-116">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
