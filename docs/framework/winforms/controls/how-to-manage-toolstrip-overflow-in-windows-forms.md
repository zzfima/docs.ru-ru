---
title: "Практическое руководство. Определение действий, выполняемых в случае переполнения элемента управления ToolStrip, в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 619c4832626693a56280c70af3ade5dbb9e9d4de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="b65c1-102">Практическое руководство. Определение действий, выполняемых в случае переполнения элемента управления ToolStrip, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b65c1-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>
<span data-ttu-id="b65c1-103">Если все элементы на <xref:System.Windows.Forms.ToolStrip> управления не помещаются в отведенное место, можно разрешить возможность переполнения для <xref:System.Windows.Forms.ToolStrip> и определить поведение о конкретных <xref:System.Windows.Forms.ToolStripItem>s.</span><span class="sxs-lookup"><span data-stu-id="b65c1-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>  
  
 <span data-ttu-id="b65c1-104">При добавлении <xref:System.Windows.Forms.ToolStripItem>, которые требуют больше места, чем должно быть <xref:System.Windows.Forms.ToolStrip> получает текущий размер формы, <xref:System.Windows.Forms.ToolStripOverflowButton> автоматически отображается на <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="b65c1-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="b65c1-105"><xref:System.Windows.Forms.ToolStripOverflowButton> Появляется, и поддержкой переполнения элементы перемещаются в меню переполнения раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="b65c1-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="b65c1-106">Это позволяет настроить и определять их приоритеты как ваш <xref:System.Windows.Forms.ToolStrip> элементы соответствии с изменением размеров формы.</span><span class="sxs-lookup"><span data-stu-id="b65c1-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="b65c1-107">Можно также изменить внешний вид элементов, переносимых в меню переполнения с помощью <xref:System.Windows.Forms.ToolStripItem.Placement%2A> и <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> свойства и <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> событий.</span><span class="sxs-lookup"><span data-stu-id="b65c1-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="b65c1-108">Увеличение размеров формы во время разработки или во время выполнения более <xref:System.Windows.Forms.ToolStripItem>s могут отображаться в главной <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.ToolStripOverflowButton> может даже исчезнуть до уменьшения размера формы.</span><span class="sxs-lookup"><span data-stu-id="b65c1-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="b65c1-109">Включение переполнения для элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b65c1-109">To enable overflow on a ToolStrip control</span></span>  
  
-   <span data-ttu-id="b65c1-110">Убедитесь, что <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> не задано значение `false` для <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="b65c1-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="b65c1-111">Значение по умолчанию — `True`.</span><span class="sxs-lookup"><span data-stu-id="b65c1-111">The default is `True`.</span></span>  
  
     <span data-ttu-id="b65c1-112">При <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> — `True` (по умолчанию), <xref:System.Windows.Forms.ToolStripItem> отправляется в меню переполнения раскрывающегося списка при содержимое <xref:System.Windows.Forms.ToolStripItem> превышает ширину горизонтального <xref:System.Windows.Forms.ToolStrip> или высоту вертикального <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="b65c1-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="b65c1-113">Чтобы указать поведение при переполнении отдельного элемента ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="b65c1-113">To specify overflow behavior of a specific ToolStripItem</span></span>  
  
-   <span data-ttu-id="b65c1-114">Задать <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> свойство <xref:System.Windows.Forms.ToolStripItem> нужное значение.</span><span class="sxs-lookup"><span data-stu-id="b65c1-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="b65c1-115">Возможные значения — `Always`, `Never`, и `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="b65c1-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="b65c1-116">Defaultis `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="b65c1-116">The defaultis `AsNeeded`.</span></span>  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b65c1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b65c1-117">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripOverflowButton>  
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [<span data-ttu-id="b65c1-118">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b65c1-118">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="b65c1-119">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b65c1-119">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="b65c1-120">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b65c1-120">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
