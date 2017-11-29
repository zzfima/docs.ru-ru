---
title: "События изменения свойств"
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
- custom controls [Windows Forms], property changes (using code)
- properties [Windows Forms], changes
ms.assetid: 268039ec-5aaa-4d76-b902-acccb036c850
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7685891e99f1dcb2ca9e515c7dc6d7730ff0b2e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="property-changed-events"></a><span data-ttu-id="ddcaf-102">События изменения свойств</span><span class="sxs-lookup"><span data-stu-id="ddcaf-102">Property-Changed Events</span></span>
<span data-ttu-id="ddcaf-103">Если требуется, чтобы элемент управления для отправки уведомлений, когда свойство с именем *PropertyName* изменения, определите событие с именем *PropertyName* `Changed` и метод с именем `On` *PropertyName* `Changed` , вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="ddcaf-103">If you want your control to send notifications when a property named *PropertyName* changes, define an event named *PropertyName*`Changed` and a method named `On`*PropertyName*`Changed` that raises the event.</span></span> <span data-ttu-id="ddcaf-104">Соглашение об именовании в Windows Forms — добавить слово *Changed* к имени свойства.</span><span class="sxs-lookup"><span data-stu-id="ddcaf-104">The naming convention in Windows Forms is to append the word *Changed* to the name of the property.</span></span> <span data-ttu-id="ddcaf-105">Связанный тип делегата события для события изменения свойств является <xref:System.EventHandler>, и тип данных события является <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ddcaf-105">The associated event delegate type for property-changed events is <xref:System.EventHandler>, and the event data type is <xref:System.EventArgs>.</span></span> <span data-ttu-id="ddcaf-106">Базовый класс <xref:System.Windows.Forms.Control> определяет многие события изменения свойства, такие как <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>и др.</span><span class="sxs-lookup"><span data-stu-id="ddcaf-106">The base class <xref:System.Windows.Forms.Control> defines many property-changed events, such as <xref:System.Windows.Forms.Control.BackColorChanged>, <xref:System.Windows.Forms.Control.BackgroundImageChanged>, <xref:System.Windows.Forms.Control.FontChanged>, <xref:System.Windows.Forms.Control.LocationChanged>, and others.</span></span> <span data-ttu-id="ddcaf-107">Дополнительные сведения о событиях см. в разделе [событий](../../../../docs/standard/events/index.md) и [события элементов управления Windows Forms](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ddcaf-107">For background information about events, see [Events](../../../../docs/standard/events/index.md) and [Events in Windows Forms Controls](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="ddcaf-108">События изменения свойств полезны, потому что они позволяют пользователям элемента управления присоединять обработчики событий, реагирующие на изменения.</span><span class="sxs-lookup"><span data-stu-id="ddcaf-108">Property-changed events are useful because they allow consumers of a control to attach event handlers that respond to the change.</span></span> <span data-ttu-id="ddcaf-109">Если элемент управления должен реагировать на событие изменения свойства, которое его вызывает, переопределите соответствующий `On` *PropertyName* `Changed` вместо присоединения делегата к событию.</span><span class="sxs-lookup"><span data-stu-id="ddcaf-109">If your control needs to respond to a property-changed event that it raises, override the corresponding `On`*PropertyName*`Changed` method instead of attaching a delegate to the event.</span></span> <span data-ttu-id="ddcaf-110">Элемент управления обычно отвечает на событие изменения свойства, обновляя другие свойства, либо все или некоторые из его поверхности.</span><span class="sxs-lookup"><span data-stu-id="ddcaf-110">A control typically responds to a property-changed event by updating other properties or by redrawing some or all of its drawing surface.</span></span>  
  
 <span data-ttu-id="ddcaf-111">В следующем примере показан способ `FlashTrackBar` пользовательский элемент управления отвечает на некоторые события изменения свойств, которые он наследует от <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="ddcaf-111">The following example shows how the `FlashTrackBar` custom control responds to some of the property-changed events that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="ddcaf-112">Полный пример см. в разделе [как: создание Windows Forms элемента управления, показывает ход выполнения](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="ddcaf-112">For the complete sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#2)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ddcaf-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ddcaf-113">See Also</span></span>  
 [<span data-ttu-id="ddcaf-114">События</span><span class="sxs-lookup"><span data-stu-id="ddcaf-114">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="ddcaf-115">События элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ddcaf-115">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="ddcaf-116">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ddcaf-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
