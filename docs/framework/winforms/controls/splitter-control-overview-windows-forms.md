---
title: Общие сведения об элементе управления Splitter (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 0477f68aaf67d4b29c491052999ff7784e736669
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009712"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="278c0-102">Общие сведения об элементе управления Splitter (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="278c0-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="278c0-103">Несмотря на то что <xref:System.Windows.Forms.SplitContainer> заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.Splitter> элемента управления предыдущих версий <xref:System.Windows.Forms.Splitter> сохраняется для обратной совместимости и использования в будущем, если вы выберете.</span><span class="sxs-lookup"><span data-stu-id="278c0-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="278c0-104">Windows Forms <xref:System.Windows.Forms.Splitter> элементы управления используются для изменения размера закрепленных элементов управления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="278c0-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="278c0-105"><xref:System.Windows.Forms.Splitter> Управления часто используется в формах с помощью элементов управления, имеющих данные для представления, например в проводнике Windows, где области данных содержат сведения о разных размеров в разное время переменной длины.</span><span class="sxs-lookup"><span data-stu-id="278c0-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="278c0-106">Работа с элементом управления Splitter</span><span class="sxs-lookup"><span data-stu-id="278c0-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="278c0-107">Когда пользователь наводит указатель мыши на незакрепленный край элемента управления, для которого могут быть изменены при помощи разделителя, указатель примет вид, показывая, что может быть изменены размеры элемента управления.</span><span class="sxs-lookup"><span data-stu-id="278c0-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="278c0-108">С элементом управления разделителем, пользователь может изменять размеры пристыкованного элемента управления, которая находится непосредственно перед его.</span><span class="sxs-lookup"><span data-stu-id="278c0-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="278c0-109">Таким образом чтобы разрешить пользователю изменять размер закрепленного элемента управления во время выполнения, закрепить элемент управления, изменять размер на край контейнера и затем закрепите элемент управления разделителя к той же стороне контейнера.</span><span class="sxs-lookup"><span data-stu-id="278c0-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="278c0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="278c0-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="278c0-111">Практическое руководство. Закрепление элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="278c0-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="278c0-112">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="278c0-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
