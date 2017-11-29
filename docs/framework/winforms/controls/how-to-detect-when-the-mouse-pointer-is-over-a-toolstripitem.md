---
title: "Практическое руководство. Отслеживание наведения указателя мыши на элемент ToolStripItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 633b92bf6da837b3727001c621548fa58b230102
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="db24b-102">Практическое руководство. Отслеживание наведения указателя мыши на элемент ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="db24b-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="db24b-103">Используйте следующую процедуру, чтобы обнаружить, когда указатель мыши находится над <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="db24b-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="db24b-104">Чтобы обнаружить, когда указатель находится над ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="db24b-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="db24b-105">Используйте <xref:System.Windows.Forms.ToolStripItem.Selected%2A> свойство для элементов, в котором <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> — `true`.</span><span class="sxs-lookup"><span data-stu-id="db24b-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="db24b-106">Это избавит вас от необходимости синхронизации <xref:System.Windows.Forms.ToolStripItem.MouseEnter> и <xref:System.Windows.Forms.ToolStripItem.MouseLeave> события.</span><span class="sxs-lookup"><span data-stu-id="db24b-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db24b-107">См. также</span><span class="sxs-lookup"><span data-stu-id="db24b-107">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [<span data-ttu-id="db24b-108">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="db24b-108">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
