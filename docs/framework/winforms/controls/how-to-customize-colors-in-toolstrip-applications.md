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
ms.openlocfilehash: 6719156d0ab6d1e53cd0bd8f16f306577589fb40
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592841"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="b6d8d-102">Практическое руководство. Настройка цветов в приложениях, в которых используется элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b6d8d-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="b6d8d-103">Внешний вид <xref:System.Windows.Forms.ToolStrip> можно настроить с помощью класса <xref:System.Windows.Forms.ToolStripProfessionalRenderer> для использования пользовательских цветов.</span><span class="sxs-lookup"><span data-stu-id="b6d8d-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6d8d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b6d8d-104">Example</span></span>  
 <span data-ttu-id="b6d8d-105">В следующем примере кода показано, как использовать <xref:System.Windows.Forms.ToolStripProfessionalRenderer> для определения пользовательских цветов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6d8d-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b6d8d-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b6d8d-106">Compiling the Code</span></span>  
 <span data-ttu-id="b6d8d-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b6d8d-107">This example requires:</span></span>  
  
- <span data-ttu-id="b6d8d-108">ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b6d8d-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d8d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b6d8d-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
