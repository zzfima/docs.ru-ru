---
title: Практическое руководство. Разрешение переупорядочения элементов ToolStrip во время выполнения в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: daff9d6d351db514d552225853f977775f8e3204
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220413"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="d60ce-102">Практическое руководство. Разрешение переупорядочения элементов ToolStrip во время выполнения в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d60ce-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="d60ce-103">Вы можете включить пользователя для изменения порядка <xref:System.Windows.Forms.ToolStripItem> элементов управления в <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="d60ce-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="d60ce-104">Для включения элементов ToolStripItem во время выполнения</span><span class="sxs-lookup"><span data-stu-id="d60ce-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
-   <span data-ttu-id="d60ce-105">Задайте для свойства <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d60ce-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="d60ce-106">По умолчанию <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> является `false`.</span><span class="sxs-lookup"><span data-stu-id="d60ce-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="d60ce-107">Во время выполнения пользователь удерживает клавишу ALT и левую кнопку мыши для перетаскивания <xref:System.Windows.Forms.ToolStripItem> в другое расположение на <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="d60ce-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d60ce-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d60ce-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="d60ce-109">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d60ce-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="d60ce-110">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d60ce-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="d60ce-111">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d60ce-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
