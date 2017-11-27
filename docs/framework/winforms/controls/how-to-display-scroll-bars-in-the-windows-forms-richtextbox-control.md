---
title: "Практическое руководство. Отображение полос прокрутки в элементе управления RichTextBox в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b20c526b27eb185bf79eaf0ace47e5a9fded42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="f282d-102">Практическое руководство. Отображение полос прокрутки в элементе управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f282d-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="f282d-103">По умолчанию в Windows Forms <xref:System.Windows.Forms.RichTextBox> элемент управления отображает горизонтальные и вертикальные полосы прокрутки при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f282d-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="f282d-104">Существует семь возможных значений для <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> свойства <xref:System.Windows.Forms.RichTextBox> элемента управления, которые описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f282d-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="f282d-105">Для отображения полос прокрутки в элементе управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="f282d-105">To display scroll bars in a RichTextBox control</span></span>  
  
1.  <span data-ttu-id="f282d-106">Задайте для свойства <xref:System.Windows.Forms.RichTextBox.Multiline%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f282d-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="f282d-107">Нет типа полосы прокрутки, включая горизонтальной, отображается в том случае, если <xref:System.Windows.Forms.RichTextBox.Multiline%2A> свойству `false`.</span><span class="sxs-lookup"><span data-stu-id="f282d-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2.  <span data-ttu-id="f282d-108">Задать <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> соответствующее значение свойства <xref:System.Windows.Forms.RichTextBoxScrollBars> перечисления.</span><span class="sxs-lookup"><span data-stu-id="f282d-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="f282d-109">Значение</span><span class="sxs-lookup"><span data-stu-id="f282d-109">Value</span></span>|<span data-ttu-id="f282d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f282d-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="f282d-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f282d-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="f282d-112">Отображение полос прокрутки по горизонтальной или вертикальной (или оба) только в том случае, если длина текста превышает ширину или длина элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f282d-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="f282d-113">Не отображаются ни полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="f282d-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="f282d-114">Отображает полосу только если длина текста превышает ширину элемента управления горизонтальной прокрутки.</span><span class="sxs-lookup"><span data-stu-id="f282d-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="f282d-115">(Чтобы это происходило, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> свойству необходимо присвоить значение `false`.)</span><span class="sxs-lookup"><span data-stu-id="f282d-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="f282d-116">Вертикальная полоса прокрутки отображается только при текст выходит высоту элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f282d-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="f282d-117">Отображение горизонтальной полосы наблюдают прокрутки <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> свойству `false`.</span><span class="sxs-lookup"><span data-stu-id="f282d-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="f282d-118">Полоса прокрутки отображается серым цветом, если текст не превышает ширину элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f282d-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="f282d-119">Вертикальная полоса прокрутки отображается всегда.</span><span class="sxs-lookup"><span data-stu-id="f282d-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="f282d-120">Полоса прокрутки отображается серым цветом, если текст не превышает длину элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f282d-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="f282d-121">Вертикальная полоса прокрутки отображается всегда.</span><span class="sxs-lookup"><span data-stu-id="f282d-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="f282d-122">Отображение горизонтальной полосы наблюдают прокрутки <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> свойству `false`.</span><span class="sxs-lookup"><span data-stu-id="f282d-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="f282d-123">Полосы прокрутки отображаются выделена серым цветом, если текст не должна превышать пределы элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f282d-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3.  <span data-ttu-id="f282d-124">Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="f282d-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="f282d-125">Значение</span><span class="sxs-lookup"><span data-stu-id="f282d-125">Value</span></span>|<span data-ttu-id="f282d-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f282d-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="f282d-127">Текст в элементе управления не настраивается автоматически по ширине элемента управления, поэтому будет прокрутите окно вправо до достижения конца строки.</span><span class="sxs-lookup"><span data-stu-id="f282d-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="f282d-128">Это значение используется при выборе горизонтальные полосы прокрутки, или в оба выше.</span><span class="sxs-lookup"><span data-stu-id="f282d-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="f282d-129">`true` (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f282d-129">`true` (default)</span></span>|<span data-ttu-id="f282d-130">Текст в элементе управления автоматически корректируется по ширине элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f282d-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="f282d-131">Горизонтальная полоса прокрутки отображаться не будут.</span><span class="sxs-lookup"><span data-stu-id="f282d-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="f282d-132">Это значение используется в том случае, если вы выбрали вертикальных полос прокрутки или нет, выше, для отображения один или несколько абзацев.</span><span class="sxs-lookup"><span data-stu-id="f282d-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f282d-133">См. также</span><span class="sxs-lookup"><span data-stu-id="f282d-133">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="f282d-134">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="f282d-134">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="f282d-135">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f282d-135">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
