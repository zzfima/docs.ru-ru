---
title: Общие сведения об элементе управления Splitter
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 3d6da8daf9bb0e8df4f69554a87725a7ddb65acb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742900"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="4c2b6-102">Общие сведения об элементе управления Splitter (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4c2b6-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="4c2b6-103">Хотя элемент управления <xref:System.Windows.Forms.SplitContainer> заменяет элемент управления <xref:System.Windows.Forms.Splitter> предыдущих версий и расширяет его функциональные возможности, однако при необходимости элемент управления <xref:System.Windows.Forms.Splitter> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="4c2b6-104">Windows Forms элементы управления <xref:System.Windows.Forms.Splitter> используются для изменения размеров закрепленных элементов управления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="4c2b6-105">Элемент управления <xref:System.Windows.Forms.Splitter> часто используется в формах с элементами управления, имеющими разную длину данных, например в проводнике Windows, области данных которых содержат сведения различной ширины в разное время.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="4c2b6-106">Работа с элементом управления Splitter</span><span class="sxs-lookup"><span data-stu-id="4c2b6-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="4c2b6-107">Когда пользователь наводит указатель мыши на незакрепленную границу элемента управления, размер которого может быть изменен с помощью элемента управления Splitter, указатель изменяет свой внешний вид, чтобы показать, что размер элемента управления может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="4c2b6-108">С помощью элемента управления Splitter пользователь может изменить размер закрепленного элемента управления, который находится непосредственно перед ним.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="4c2b6-109">Таким образом, чтобы позволить пользователю изменять размер закрепленного элемента управления во время выполнения, закрепите элемент управления для изменения его размера до края контейнера, а затем закрепите элемент управления Splitter на той же стороне контейнера.</span><span class="sxs-lookup"><span data-stu-id="4c2b6-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c2b6-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4c2b6-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="4c2b6-111">Практическое руководство. Закрепление элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c2b6-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="4c2b6-112">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4c2b6-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
