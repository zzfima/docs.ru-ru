---
title: Практическое руководство. Отслеживание наведения указателя мыши на элемент ToolStripItem
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 09fd9f2f9b8cc44b6c04b829bf2854bea4aa8cf7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220050"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="69ec7-102">Практическое руководство. Отслеживание наведения указателя мыши на элемент ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="69ec7-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="69ec7-103">Используйте следующую процедуру, чтобы определить, когда указатель мыши находится над <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="69ec7-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="69ec7-104">Чтобы определить, когда указатель наведен на элемент ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="69ec7-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="69ec7-105">Используйте <xref:System.Windows.Forms.ToolStripItem.Selected%2A> свойства для элементов, в котором <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> является `true`.</span><span class="sxs-lookup"><span data-stu-id="69ec7-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="69ec7-106">Это избавит вас от необходимости синхронизации <xref:System.Windows.Forms.ToolStripItem.MouseEnter> и <xref:System.Windows.Forms.ToolStripItem.MouseLeave> события.</span><span class="sxs-lookup"><span data-stu-id="69ec7-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ec7-107">См. также</span><span class="sxs-lookup"><span data-stu-id="69ec7-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="69ec7-108">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="69ec7-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
