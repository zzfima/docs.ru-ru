---
title: "Общие сведения об элементе управления Splitter (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 32d8829e7303ce23a22d0a01f2428a889ce4ae0f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="cde93-102">Общие сведения об элементе управления Splitter (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cde93-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="cde93-103">Несмотря на то что <xref:System.Windows.Forms.SplitContainer> заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.Splitter> управления предыдущих версий, <xref:System.Windows.Forms.Splitter> можно сохранить для обратной совместимости и использования в будущем, если выбрать.</span><span class="sxs-lookup"><span data-stu-id="cde93-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="cde93-104">Windows Forms <xref:System.Windows.Forms.Splitter> элементы управления используются для изменения размера закрепленных элементов управления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cde93-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="cde93-105"><xref:System.Windows.Forms.Splitter> Управления часто используется в формах с элементами управления, в которых представлены, например в проводнике Windows, где области данных содержат сведения о разных размеров в разное время данные переменной длины.</span><span class="sxs-lookup"><span data-stu-id="cde93-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="cde93-106">Работа с элементом управления Splitter</span><span class="sxs-lookup"><span data-stu-id="cde93-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="cde93-107">Когда пользователь наводит указатель мыши на незакрепленный край элемента управления, которые могут быть изменены при помощи разделителя, указатель в вид, показывая, что могут быть изменены размеры элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cde93-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="cde93-108">С помощью элемента управления разделителем закрепленного элемента управления, находящегося непосредственно перед могут изменять пользователи.</span><span class="sxs-lookup"><span data-stu-id="cde93-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="cde93-109">Таким образом чтобы разрешить пользователю изменять размер закрепленного элемента управления во время выполнения, закрепление элемента управления к изменению размера на край контейнера и затем закрепите элемент управления splitter к той же стороне контейнера.</span><span class="sxs-lookup"><span data-stu-id="cde93-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cde93-110">См. также</span><span class="sxs-lookup"><span data-stu-id="cde93-110">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="cde93-111">Практическое руководство. Закрепление элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cde93-111">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [<span data-ttu-id="cde93-112">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cde93-112">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
