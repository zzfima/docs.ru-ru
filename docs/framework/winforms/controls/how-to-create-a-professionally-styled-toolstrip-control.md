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
ms.openlocfilehash: 4e4e899d583eb87b3ced7161f1fd274c0bcc591c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586552"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="e4799-102">Практическое руководство. Создание профессионально оформленного элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e4799-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="e4799-103">Вы можете придать элементам управления <xref:System.Windows.Forms.ToolStrip> своего приложения профессиональный внешний вид и поведение, создав собственный класс, производный от типа <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="e4799-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="e4799-104">Имеется широкая поддержка этой возможности в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e4799-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="e4799-105">См. [Пошаговое руководство: Создание профессионально оформленного элемента управления ToolStrip](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="e4799-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4799-106">Пример</span><span class="sxs-lookup"><span data-stu-id="e4799-106">Example</span></span>  
 <span data-ttu-id="e4799-107">В следующем примере кода демонстрируется использование <xref:System.Windows.Forms.ToolStrip> элементы управления для создания составного элемента управления, напоминающего **редактируемую** в Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="e4799-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4799-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e4799-108">Compiling the Code</span></span>  
 <span data-ttu-id="e4799-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="e4799-109">This example requires:</span></span>  
  
- <span data-ttu-id="e4799-110">ссылки на сборки System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e4799-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4799-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e4799-111">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="e4799-112">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e4799-112">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="e4799-113">Практическое руководство. Обеспечивают стандартные пункты меню в форму</span><span class="sxs-lookup"><span data-stu-id="e4799-113">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
