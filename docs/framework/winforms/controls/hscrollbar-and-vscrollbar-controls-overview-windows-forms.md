---
title: "Общие сведения об элементах управления HScrollBar и VScrollBar (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7a6f1d569234f7cee4b5eedc81fcc68a41fcf0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="a62b5-102">Общие сведения об элементах управления HScrollBar и VScrollBar (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a62b5-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="a62b5-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> элементы управления используются для обеспечения удобного просмотра длинных списков элементов или данные большого объема с либо горизонтальной или вертикальной прокрутки окна приложения или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a62b5-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="a62b5-104">Полосы прокрутки — это распространенный элемент интерфейса Windows, поэтому <xref:System.Windows.Forms.ScrollBar> управления часто используется с элементами управления, которые не являются производными от <xref:System.Windows.Forms.ScrollableControl> класса.</span><span class="sxs-lookup"><span data-stu-id="a62b5-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="a62b5-105">Аналогично, многие разработчики выберите для включения <xref:System.Windows.Forms.ScrollBar> управления своих собственных пользовательских элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a62b5-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="a62b5-106"><xref:System.Windows.Forms.HScrollBar> (Горизонтально) и <xref:System.Windows.Forms.VScrollBar> (по вертикали) элементы управления работают независимо от других элементов управления и имеют свой собственный набор событий, свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="a62b5-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <span data-ttu-id="a62b5-107"><xref:System.Windows.Forms.ScrollBar>элементы управления не совпадает с встроенными полосами прокрутки, вложенные в текстовые поля, списки, поля со списком или MDI-форм ( <xref:System.Windows.Forms.TextBox> управления имеет <xref:System.Windows.Forms.TextBox.ScrollBars%2A> свойство для отображения или скрытия полос прокрутки, прикрепленных к элементу управления).</span><span class="sxs-lookup"><span data-stu-id="a62b5-107"><xref:System.Windows.Forms.ScrollBar> controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="a62b5-108"><xref:System.Windows.Forms.ScrollBar> Элементы управления используют <xref:System.Windows.Forms.ScrollBar.Scroll> событий для отслеживания перемещения ползунка (иногда называется бегунком) по полосе прокрутки.</span><span class="sxs-lookup"><span data-stu-id="a62b5-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="a62b5-109">С помощью <xref:System.Windows.Forms.ScrollBar.Scroll> событие предоставляет доступ к значению панель прокрутки при его перетаскивании.</span><span class="sxs-lookup"><span data-stu-id="a62b5-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="a62b5-110">Свойство Value</span><span class="sxs-lookup"><span data-stu-id="a62b5-110">Value Property</span></span>  
 <span data-ttu-id="a62b5-111"><xref:System.Windows.Forms.ScrollBar.Value%2A> (Который по умолчанию равно 0) задано `integer` значение, соответствующее положение ползунка полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="a62b5-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="a62b5-112">Когда положения ползунка минимальное значение, он перемещает позицию слева (на горизонтальной полосе прокрутки) или верхней позиции (на вертикальной полосе прокрутки).</span><span class="sxs-lookup"><span data-stu-id="a62b5-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="a62b5-113">Когда поле находится в максимальное значение, ползунка справа или нижнюю позицию.</span><span class="sxs-lookup"><span data-stu-id="a62b5-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="a62b5-114">Аналогично значение в середине диапазона между минимальным и максимальным пределами помещает переднего края ползунка в середине полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="a62b5-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="a62b5-115">Помимо использования щелчки мышью для изменения значения панель прокрутки, пользователь также можно перетаскивать полосы прокрутки в любой момент на полосе.</span><span class="sxs-lookup"><span data-stu-id="a62b5-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="a62b5-116">Результирующее значение зависит от положения ползунка, но он всегда находится в диапазоне от <xref:System.Windows.Forms.ScrollBar.Minimum%2A> для <xref:System.Windows.Forms.ScrollBar.Maximum%2A> свойства, установленные пользователем.</span><span class="sxs-lookup"><span data-stu-id="a62b5-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="a62b5-117">LargeChange и свойства SmallChange</span><span class="sxs-lookup"><span data-stu-id="a62b5-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="a62b5-118">Когда пользователь нажимает клавишу PAGE UP или PAGE DOWN или щелкает в полосы прокрутки с обеих сторон ползунка, <xref:System.Windows.Forms.ScrollBar.Value%2A> изменяется в соответствии со значением <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="a62b5-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="a62b5-119">Когда пользователь щелкает стрелку ключей или нажимает одну из кнопок полосы прокрутки, <xref:System.Windows.Forms.ScrollBar.Value%2A> изменяется в соответствии со значением <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="a62b5-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62b5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a62b5-120">See Also</span></span>  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [<span data-ttu-id="a62b5-121">Дополнения в Windows Forms для платформы .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="a62b5-121">Additions to Windows Forms for the .NET Framework 2.0</span></span>](http://msdn.microsoft.com/en-us/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [<span data-ttu-id="a62b5-122">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a62b5-122">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
