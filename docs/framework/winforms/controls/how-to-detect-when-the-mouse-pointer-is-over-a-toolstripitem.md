---
title: Как выполнить Обнаружить, когда указатель мыши находится над ToolStripItem
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 20fbc91773f431fc68f606f8aa9f24f4c0cc06bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539601"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="d9b42-102">Как выполнить Обнаружить, когда указатель мыши находится над ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="d9b42-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="d9b42-103">Используйте следующую процедуру, чтобы определить, когда указатель мыши находится над <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="d9b42-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="d9b42-104">Чтобы определить, когда указатель наведен на элемент ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="d9b42-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="d9b42-105">Используйте <xref:System.Windows.Forms.ToolStripItem.Selected%2A> свойства для элементов, в котором <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> является `true`.</span><span class="sxs-lookup"><span data-stu-id="d9b42-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="d9b42-106">Это избавит вас от необходимости синхронизации <xref:System.Windows.Forms.ToolStripItem.MouseEnter> и <xref:System.Windows.Forms.ToolStripItem.MouseLeave> события.</span><span class="sxs-lookup"><span data-stu-id="d9b42-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b42-107">См. также</span><span class="sxs-lookup"><span data-stu-id="d9b42-107">See also</span></span>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="d9b42-108">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d9b42-108">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
