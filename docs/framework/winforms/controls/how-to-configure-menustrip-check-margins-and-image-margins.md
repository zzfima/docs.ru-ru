---
title: Практическое руководство. Настройка полей флажков и значков для объекта MenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: fa099012fa77daacd1f428e64abd662ee1738f84
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586587"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="30c95-102">Практическое руководство. Настройка полей флажков и значков для объекта MenuStrip</span><span class="sxs-lookup"><span data-stu-id="30c95-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="30c95-103">Элемент управления <xref:System.Windows.Forms.MenuStrip> можно настраивать, устанавливая свойства <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> и <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> в различных сочетаниях. </span><span class="sxs-lookup"><span data-stu-id="30c95-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30c95-104">Пример</span><span class="sxs-lookup"><span data-stu-id="30c95-104">Example</span></span>  
 <span data-ttu-id="30c95-105">В примере кода ниже показано, как установить и настроить поля флажков и значков для элемента управления <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="30c95-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="30c95-106">Для элементов управления <xref:System.Windows.Forms.ContextMenuStrip> и <xref:System.Windows.Forms.MenuStrip> процедура одинакова.</span><span class="sxs-lookup"><span data-stu-id="30c95-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30c95-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="30c95-107">Compiling the Code</span></span>  
 <span data-ttu-id="30c95-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="30c95-108">This example requires:</span></span>  
  
- <span data-ttu-id="30c95-109">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="30c95-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c95-110">См. также</span><span class="sxs-lookup"><span data-stu-id="30c95-110">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="30c95-111">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="30c95-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="30c95-112">Практическое руководство. Включение полей флажков и значков для элементов управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="30c95-112">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
