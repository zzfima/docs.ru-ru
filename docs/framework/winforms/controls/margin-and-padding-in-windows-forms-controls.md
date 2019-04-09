---
title: Поля и заполнение в элементах управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: bf1f88f6efcedd740bff92dda391470391f16ce5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094060"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="43921-102">Поля и заполнение в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="43921-102">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="43921-103">Точное расположение элементов управления на форме является важным для многих приложений.</span><span class="sxs-lookup"><span data-stu-id="43921-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="43921-104">Пространство имен <xref:System.Windows.Forms?displayProperty=nameWithType> предоставляет множество возможностей компоновки для решения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="43921-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="43921-105">Свойства <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A> — одни из наиболее важных.</span><span class="sxs-lookup"><span data-stu-id="43921-105">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="43921-106">Свойство <xref:System.Windows.Forms.Control.Margin%2A> определяет поле вокруг элемента управления, благодаря которому обеспечивается определенное расстояние между границами этого элемента и другими элементами.</span><span class="sxs-lookup"><span data-stu-id="43921-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="43921-107">Свойство <xref:System.Windows.Forms.Control.Padding%2A> определяет поле внутри элемента управления, благодаря которому обеспечивается определенное расстояние между содержимым элемента управления (например, значением свойства <xref:System.Windows.Forms.Control.Text%2A>) и его границами.</span><span class="sxs-lookup"><span data-stu-id="43921-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="43921-108">На рисунке ниже демонстрируется значение свойств <xref:System.Windows.Forms.Control.Padding%2A> и <xref:System.Windows.Forms.Control.Margin%2A> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="43921-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="43921-109">![И заполнение для Windows Forms элементы управления](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="43921-109">![Padding And Margin for Windows Forms Controls](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="43921-110">Эта возможность поддерживается во время разработки в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="43921-110">There is design-time support for this feature in Visual Studio.</span></span> <span data-ttu-id="43921-111">Также см. в разделе [Пошаговое руководство: Размещение Windows Forms элементы управления с помощью свойств Padding, Margins и свойство AutoSize](windows-forms-controls-padding-autosize.md).</span><span class="sxs-lookup"><span data-stu-id="43921-111">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43921-112">См. также</span><span class="sxs-lookup"><span data-stu-id="43921-112">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
